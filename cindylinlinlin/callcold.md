---
name: callcold
description: 從 HubSpot 撈取需要「重新喚醒」的客戶資料（上次聯絡距今 7–21 天），包含交易名稱、聯絡人姓名、電話、上次聯絡日期與備註。當使用者說「冷單」、「callcold」、「冷客戶」或「久沒聯絡的客戶」時啟動此技能。
---

# Call Cold — 冷單喚醒清單

## Instructions

### Step 1：同時並行查詢兩組交易（重要：兩個查詢必須同時發出，不得序列執行）

先計算時間範圍：
- **上限**（7 天前）= 今天日期 - 7 天，轉為 Unix timestamp × 1000
- **下限**（21 天前）= 今天日期 - 21 天，轉為 Unix timestamp × 1000
- 例如今天是 2026-03-25：
  - 7 天前 = 2026-03-18 00:00:00 UTC = `1773792000000`
  - 21 天前 = 2026-03-04 00:00:00 UTC = `1772582400000`

**查詢 A — Lead In 冷單：**
- pipeline = `default`
- dealstage = `appointmentscheduled`
- hubspot_owner_id = `59247814`
- notes_last_contacted BETWEEN 下限 AND 上限（即 21 天前 ～ 7 天前）
- limit: 50

**查詢 B — 其他 Stage 冷單：**
- pipeline = `default`
- dealstage NOT IN `appointmentscheduled`, `closedwon`, `closedlost`
- hubspot_owner_id = `59247814`
- notes_last_contacted BETWEEN 下限 AND 上限（即 21 天前 ～ 7 天前）
- limit: 50

兩個查詢**同時發出**，拿到結果後合併，重複的交易只保留一筆。
**依 notes_last_contacted 由舊到新排序**（最久沒聯絡的排最前面）。

### Step 2：批次並行查詢聯絡人

將所有交易的 ID 分成每批 5 筆，**所有批次同時並行發出**查詢，取得：
- 聯絡人姓名（firstname + lastname）
- 聯繫電話（phone 或 mobilephone）

若同一交易有多位聯絡人，全部列出。

### Step 3：顯示冷單喚醒清單

顯示標題：`🧊 冷單喚醒清單（上次聯絡：7–21 天前）`

依序列出每一筆交易，格式如下：

---
**交易名稱：** [Deal Name]
**目前 Stage：** [Deal Stage]
**聯絡人：** [Contact Name]
**電話：** [Phone Number]
**上次聯絡：** [Last Contact Date 或 （未記錄）]

---

每一筆交易之間用分隔線區隔。
電話號碼清楚顯示，方便直接撥打。

最後顯示摘要：`共找到 [N] 筆冷單客戶需要喚醒`

### Step 4：處理沒有客戶的情況
如果 Step 1 兩個查詢都查無資料，回覆：

> 「目前沒有冷單客戶！你的跟進速度很讚 👍」

## Examples

### Example 1：有冷單客戶
**User says:** 「callcold」

**What to do:**
1. 連接 HubSpot，查詢 Lead In 且 7–21 天前有聯絡的交易
2. 查詢其他 Stage 且 7–21 天前有聯絡的交易（排除結案）
3. 合併名單，依上次聯絡日期由遠至近排序
4. 顯示每位客戶的完整資料

**Result:**
顯示 🧊 冷單喚醒清單，最久沒聯絡的排最前面。

---

### Example 2：沒有冷單客戶
**User says:** 「久沒聯絡的客戶」

**Result:**
> 「目前沒有冷單客戶！你的跟進速度很讚 👍」

## Troubleshooting

**如果 HubSpot 連線失敗：**
告知使用者：「HubSpot 目前無法連線，請確認 Connector 是否已開啟，或稍後再試。」

**如果上次聯絡日期沒有資料：**
顯示「（未記錄）」，但仍列出此筆交易。
