---
name: call-prep
description: 從 HubSpot 撈取今日需要追蹤的客戶資料，包含公司名稱、交易名稱、聯絡人姓名、目前 Stage、上次聯絡日期與所有備註。當使用者說「今天要打給誰」、「電話準備」、「今日追蹤清單」或「call prep」時啟動此技能。
---

# Call Prep — 今日電話追蹤清單

## Instructions

### Step 1：同時並行查詢兩組交易（重要：兩個查詢必須同時發出，不得序列執行）

**查詢 A — 潛客追蹤（Lead In / Prospect / Lead Contacted）：**
- pipeline = `default`
- dealstage IN `appointmentscheduled`, `166877710`, `10983508`
  （對應：Lead In、Prospect、Lead Contacted via email/call）
- hubspot_owner_id = `59247814`

**查詢 B — 近期跟進客戶：**
- pipeline = `default`
- dealstage NOT IN `appointmentscheduled`, `closedwon`, `closedlost`, `166877710`, `10983508`
- hubspot_owner_id = `59247814`
- notes_last_contacted >= 今天日期往前推 7 天的 Unix 毫秒時間戳
  （計算方式：取今天的日期，減去 7 天，轉為 Unix timestamp × 1000）
  例如今天是 2026-03-25，則 7 天前 = 2026-03-18 00:00:00 UTC = `1773792000000`
- **limit: 50**（避免回傳過多無關資料）
- **後處理過濾：** 拿到結果後，同時取得每筆交易的 `hs_lastmodifieddate`，
  移除 `hs_lastmodifieddate` >= (現在時間 - 86400000 ms) 的交易
  （即排除 24 小時內有異動過 stage 的客戶）

兩個查詢**同時發出**，拿到結果後合併，重複的交易只保留一筆。

### Step 2：批次並行查詢聯絡人

將所有交易的 ID 分成每批 5 筆，**所有批次同時並行發出**查詢，取得：
- 聯絡人姓名（firstname + lastname）
- 聯繫電話（phone 或 mobilephone）

若同一交易有多位聯絡人，全部列出。

### Step 3：顯示完整追蹤清單

依序列出每一筆交易，格式如下：

---
**交易名稱：** [Deal Name]
**目前 Stage：** [Deal Stage]
**聯絡人：** [Contact Name]
**電話：** [Phone Number]
**上次聯絡：** [Last Contact Date]

---

每一筆交易之間用分隔線區隔，方便閱讀。
電話號碼要讓使用者可以直接辨識，清楚顯示。

### Step 5：處理沒有客戶的情況
如果 Step 1 和 Step 2 都查無資料，回覆：

> 「你沒有值得聯繫的客戶，去找其他客人吧！」

## Examples

### Example 1：有客戶需要追蹤
**User says:** 「今天要打給誰？」

**What to do:**
1. 連接 HubSpot，查詢 Lead In 的交易
2. 查詢其他 Stage 且兩週內有聯繫的交易
3. 合併名單
4. 顯示每位客戶的完整資料（公司、交易、聯絡人、Stage、日期、備註）

**Result:**
顯示格式化的追蹤清單，每位客戶獨立一個區塊，清楚易讀。

---

### Example 2：使用英文觸發詞
**User says:** 「call prep」

**What to do:**
1. 同上，直接連 HubSpot 查詢，不需詢問使用者
2. 顯示結果或無客戶提示

**Result:**
同 Example 1。

---

### Example 3：今日沒有待追蹤客戶
**User says:** 「今日追蹤清單」

**What to do:**
1. 查詢 HubSpot，兩個條件都查無資料

**Result:**
回覆：「你沒有值得聯繫的客戶，去找其他客人吧！」

## Troubleshooting

**如果 HubSpot 連線失敗：**
告知使用者：「HubSpot 目前無法連線，請確認 Connector 是否已開啟，或稍後再試。」

**如果上次聯絡日期沒有資料：**
顯示「（未記錄）」。
