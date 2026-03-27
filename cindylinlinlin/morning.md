---
name: morning
description: 晨間總覽技能，當使用者說「早安」、「morning」或「好早」時啟動。依序執行：(1) 整理未回覆客戶信件，(2) 列出今日 HubSpot 電話追蹤名單，(3) 在 Google Calendar 安排兩個「客戶追蹤」時段並將名單填入說明欄。
---

# Morning — 晨間工作準備總覽

## Instructions

直接依序執行 Part 1 → Part 2 → Part 3，不需詢問使用者。

> ⚠️ **日期規則：** 忽略 CLAUDE.md 的 currentDate 設定，一律以**台灣時間（Asia/Taipei）的實際今日日期**執行所有查詢與顯示。

---

### Part 1：整理未回覆客戶信件

搜尋 cindy.lin@swingvy.com 的 Gmail 收件匣，找出符合以下條件的信件：
- **在收件匣中**（未封存）
- **寄件人不是** @swingvy.com（排除內部信件）
- **寄件人不是** hubspot 相關網域（排除 @hubspot.com、@notifications.hubspot.com、@mg.hubspot.com 等）
- **對話串中最後一封信是來自客戶的**（不是 Cindy 回覆的）
- 收件時間在**兩週內**

依收件時間分為四類顯示：
- 🔴 **今天收到，尚未回覆**
- 🟠 **昨天收到，尚未回覆**
- 🟡 **一週內收到，尚未回覆**（2–7 天前）
- ⚪ **兩週內收到，尚未回覆**（8–14 天前）

每封信格式：
```
**寄件人：** [Sender Name] `<email>`
**主旨：** [Subject]
**時間：** [日期 時間]
🔗 [查看信件或 HubSpot 連結]
```

對每封信的寄件人，查詢 HubSpot 是否有對應聯絡人：
- 若有 → 使用 HubSpot 聯絡人連結
- 若無 → 使用 Gmail 信件連結

若某分類沒有信件，顯示「✅ 無待回覆信件」。
最後顯示摘要：`共找到 [N] 封未回覆客戶信件（今天 [n]、昨天 [n]、一週內 [n]、兩週內 [n]）`

若全部都已回覆，顯示：🎉 太棒了！目前沒有未回覆的客戶信件，繼續保持！

---

### Part 2：今日電話追蹤清單

連接 HubSpot，搜尋以下兩組交易並合併（去除重複）：

**第一組：Lead In 客戶**
- pipeline = `default`（Direct Sales Pipeline）
- dealstage = `appointmentscheduled`（Lead In）
- hubspot_owner_id = `59247814`（Cindy）

**第二組：其他 Stage 近期客戶**
- pipeline = `default`
- dealstage ≠ `appointmentscheduled`（排除 Lead In）
- dealstage ≠ `closedwon` 且 ≠ `closedlost`（排除已結案）
- notes_last_contacted 在 7 天內
- hubspot_owner_id = `59247814`

對每筆交易，查詢關聯聯絡人，取得姓名（firstname + lastname）與電話（phone 或 mobilephone）。

依序顯示每筆交易：
```
---
**交易名稱：** [Deal Name]
**目前 Stage：** [Deal Stage]
**聯絡人：** [Contact Name]
**電話：** [Phone Number]
**上次聯絡：** [Last Contact Date 或 （未記錄）]
**備註：** [備註內容 或 （無備註）]
```

**將此名單暫存**為以下格式，供 Part 3 使用：
```
📋 今日電話追蹤名單（[日期]）：
1. [交易名稱] ｜ [Stage] ｜ [聯絡人] ｜ [電話]
2. [交易名稱] ｜ [Stage] ｜ [聯絡人] ｜ [電話]
...
```

若查無任何客戶，顯示：「你沒有值得聯繫的客戶，去找其他客人吧！」並跳過 Part 3 的說明欄位填寫（正常建立活動但說明欄留空）。

---

### Part 3：安排行事曆電話時段

查詢今天 Google Calendar 的所有行程，依以下規則計算封鎖時段：
- 09:00 之前 → 封鎖
- 12:00–13:00 → 午休，封鎖
- 18:00 之後 → 封鎖
- 每個已有行程 → 行程開始前 15 分鐘、行程本身、行程結束後 15 分鐘，全部封鎖

在上午（09:00–12:00）找第一個連續 30 分鐘空檔（以 30 分鐘為單位對齊）。
在下午（13:00–18:00）找第一個連續 30 分鐘空檔（以 30 分鐘為單位對齊）。

對找到的每個空檔，建立 Google Calendar 活動：
- **名稱：** 客戶追蹤
- **時間：** 該空檔的開始與結束時間（30 分鐘）
- **日期：** 今天
- **說明欄位：** 填入 Part 2 暫存的客戶名單（格式同上）

回報結果：
```
已為你安排好今天的電話時段：
- 📞 上午：[HH:MM–HH:MM]
- 📞 下午：[HH:MM–HH:MM]
```

若上午或下午其中一個找不到空檔，只回報找到的那個，並說明另一個無法安排。
若兩個都找不到，顯示：「今天的行程太滿了，沒有時間打電話！記得明天補上 😅」

### 結尾

全部完成後顯示：
> 早安 Cindy！今天的準備工作完成了，出發吧！🚀

---

## Troubleshooting

**Gmail 連線失敗：** 告知「Gmail 目前無法連線，請確認 Connector 是否已開啟。」，跳過 Part 1，繼續執行 Part 2。

**HubSpot 連線失敗：** 告知「HubSpot 目前無法連線，請確認 Connector 是否已開啟。」，跳過 Part 2，Part 3 說明欄留空。

**Google Calendar 連線失敗：** 告知「Google Calendar 目前無法連線，請確認 Connector 是否已開啟。」，跳過 Part 3。

**信件數量超過 50 封：** 只顯示前 50 封，並在摘要中說明「（僅顯示前 50 封，請至 Gmail 查看完整清單）」。
