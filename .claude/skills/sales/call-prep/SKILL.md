---
name: call-prep
description: 從 HubSpot 撈取今日需要追蹤的客戶資料，包含公司名稱、交易名稱、聯絡人姓名、目前 Stage、上次聯絡日期與所有備註。當使用者說「今天要打給誰」、「電話準備」、「今日追蹤清單」或「call prep」時啟動此技能。
---

# Call Prep — 今日電話追蹤清單

## Instructions

### Step 1：連接 HubSpot，搜尋 Lead In 客戶
直接連到 HubSpot，搜尋所有符合以下條件的交易（deals）：
- **管道為 Direct Sales Pipeline**（pipeline = `default`）
- 目前 Stage 為 **Lead In**（stage values: `appointmentscheduled`）
- **負責人為 Cindy**（hubspot_owner_id = `59247814`）

不需要先詢問使用者，直接查詢。

### Step 2：搜尋其他 Stage 的近期客戶
搜尋所有符合以下條件的交易：
- **管道為 Direct Sales Pipeline**（pipeline = `default`）
- 目前 Stage **不是** Lead In（排除 `appointmentscheduled`）
- 目前 Stage **不是**已結案（排除 `closedwon` 和 `closedlost`）
- **上次聯絡日期在一週內**（7 天內）
- **負責人為 Cindy**（hubspot_owner_id = `59247814`）

### Step 3：合併名單，去除重複
將 Step 1 與 Step 2 的結果合併，若同一個交易出現兩次，只保留一筆。

### Step 4：查詢每筆交易的關聯聯絡人
對合併後的每一筆交易，查詢關聯的聯絡人（contacts），取得：
- 聯絡人姓名（firstname + lastname）
- 聯繫電話（phone 或 mobilephone）

不需要查詢備註欄位。

若同一交易有多位聯絡人，全部列出。

**找不到聯絡人電話時：**
電話欄位顯示「⚠️ 無電話記錄，請至 HubSpot 補填」，不要省略此欄位。

### Step 5：顯示完整追蹤清單
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

### Step 6：處理沒有客戶的情況
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
立即停止執行，告知使用者：「HubSpot 目前無法連線，請確認 Connector 是否已開啟，或稍後再試。」不要繼續執行後續步驟。

**如果上次聯絡日期沒有資料：**
顯示「（未記錄）」。

**如果找不到聯絡人電話：**
顯示「⚠️ 無電話記錄，請至 HubSpot 補填」。

**如果上次聯絡距今超過 30 天：**
在該筆交易標註 ⚠️，並顯示確切天數，例如「上次聯絡：2026-02-10（44 天前）⚠️ 久未聯繫」。

**如果查詢超時或回傳錯誤：**
顯示「HubSpot 查詢逾時，請稍後再試。若問題持續，請確認 Connector 連線狀態。」
