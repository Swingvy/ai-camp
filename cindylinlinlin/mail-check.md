---
name: mail-check
description: 整理 cindy.lin@swingvy.com 的未回覆客戶信件，依時間分四類顯示：今天、昨天、一週內、兩週內。每封信顯示寄件人、主旨、時間與連結（HubSpot 或 Gmail）。當使用者說「整理信件」或「mail check」時啟動此技能。
---

# Mail Check — 未回覆客戶信件整理

## Instructions

### Step 1：搜尋未回覆客戶信件
連接 Gmail，搜尋 cindy.lin@swingvy.com 收件匣中符合以下條件的信件：
- **在收件匣中**（未封存）
- **寄件人不是** @swingvy.com（排除內部信件）
- **寄件人不是** hubspot 相關網域（排除 @hubspot.com、@notifications.hubspot.com、@mg.hubspot.com 等）
- **對話串中最後一封信是來自客戶的**（不是 Cindy 回覆的）
- 收件時間在**兩週內**

直接查詢，不需要先詢問使用者。

### Step 2：依時間分類
將搜尋結果依照原始信件的收件時間分為四類：

- **🔴 今天收到，尚未回覆**（今天日期）
- **🟠 昨天收到，尚未回覆**（昨天日期）
- **🟡 一週內收到，尚未回覆**（2–7 天前）
- **⚪ 兩週內收到，尚未回覆**（8–14 天前）

同一封信只出現在一個分類中。

### Step 3：查詢每封信的寄件人是否在 HubSpot
對每封信的寄件人 email，在 HubSpot 搜尋是否有對應的聯絡人（contacts）。
- 若有 → 使用 HubSpot 聯絡人連結
- 若無 → 使用 Gmail 信件原始連結

### Step 4：顯示整理結果
依分類依序列出，每封信格式如下：

**寄件人：** [Sender Name] `<email>`
**主旨：** [Subject]
**時間：** [日期 時間]
🔗 [查看信件或 HubSpot 連結]

每個分類之間加上標題和分隔線，方便閱讀。
若某個分類沒有信件，顯示「✅ 無待回覆信件」。

### Step 5：顯示摘要
最後顯示一行摘要：
> 共找到 [N] 封未回覆客戶信件（今天 [n]、昨天 [n]、一週內 [n]、兩週內 [n]）

## Examples

### Example 1：有未回覆信件
**User says:** 「整理信件」

**What to do:**
1. 搜尋 Gmail 收件匣，條件：非 @swingvy.com、非 hubspot、非封存、對話串最後一封是客戶的
2. 依時間分四類
3. 對每位寄件人查 HubSpot
4. 顯示分類清單 + 摘要

**Result:**

---
🔴 **今天收到，尚未回覆（2 封）**

**寄件人：** 王大明 `<wang@abc.com>`
**主旨：** 詢問報價
**時間：** 2026-03-25 10:23
🔗 [查看 HubSpot](https://app.hubspot.com/contacts/...)

---

🟠 **昨天收到，尚未回覆（1 封）**
...

---

### Example 2：全部已回覆
**User says:** 「mail check」

**Result:**
> 🎉 太棒了！目前沒有未回覆的客戶信件，繼續保持！

## Troubleshooting

**如果 Gmail 連線失敗：**
告知使用者：「Gmail 目前無法連線，請確認 Connector 是否已開啟，或稍後再試。」

**如果 HubSpot 查詢失敗：**
跳過 HubSpot 查詢，直接使用 Gmail 信件連結，不要中斷整個流程。

**如果信件數量超過 50 封：**
只顯示前 50 封，並在摘要中說明：「（僅顯示前 50 封，請至 Gmail 查看完整清單）」
