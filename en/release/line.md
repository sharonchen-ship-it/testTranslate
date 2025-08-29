---
icon: line
---

# Chat Chat Platform: line

## <mark style="color:blue;">Confirm before connecting:</mark>

已經在 [Line Developers](https://developers.line.biz/zh-hant/) 的 console 平台建立好一個 「Provider」 以及 「LINE Login」 的 channel

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午4.47.49.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午4.51.10.png" alt=""><figcaption></figcaption></figure>

## <mark style="color:blue;">Start cascading</mark>

### 1. Go to [https://manager.line.biz/] (https://manager.line.biz/) and select the channel you want to connect to

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午5.01.45.png" alt=""><figcaption></figcaption></figure>

### 2. Tap Settings in the top right corner, tap Messaging API and enable to get <mark style="color:blue;">* * channel ID, channel secret * *</mark>

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午5.05.59.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午5.27.04.png" alt=""><figcaption></figcaption></figure>

### 3. Go to the Messaging API channel you just created at [https://developers.line.biz/console/] (https://developers.line.biz/console/)

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午5.37.02.png" alt=""><figcaption></figcaption></figure>

### 4. Obtain a Channel Access Token

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

### 5. Go to your MaiAgent's chat platform and select line

<figure><img src="../.gitbook/assets/截圖 2025-05-07 下午2.43.54.png" alt=""><figcaption></figcaption></figure>

### 6. Fill in the name, select the assistant, and paste the * * Channel ID, Channel Secret, * * Channel Access Token you just obtained

* * * Name: * * The name of the AI assistant you expect to see on the website
* * * AI assistant: * * Select the AI assistant you want to connect with
* * * line Channel: * * Fill in your Channel ID, Channel Secret, Channel Access Token

When you're done, hit the 'Chat' button in the bottom right corner and the chat will be ready.

<figure><img src="../.gitbook/assets/截圖 2025-04-25 上午11.30.37.png" alt=""><figcaption></figcaption></figure>

### 7. Get the webhook URL

Go to the chat platform, select the line channel you just created, click on the action, and get the webhook URL in the API block

<figure><img src="../.gitbook/assets/截圖 2025-04-25 上午11.32.09.png" alt=""><figcaption></figcaption></figure>

### 8. 在 [https://manager.line.biz/](https://manager.line.biz/) 點選 「設定/Messaging API」，貼上剛取得的Webhook 網址&#x20;

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

### 9. 在 [https://developers.line.biz/console/](https://developers.line.biz/console/) 重新返回剛建立的  Messaging API 頻道，進行對話設定

於 Auto-reply messages 點選 Edit 按鈕

<figure><img src="../.gitbook/assets/image (74).png" alt=""><figcaption></figcaption></figure>

將回應設定調整如下圖

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午5.51.33.png" alt=""><figcaption></figcaption></figure>

### **10. 確認串接是否成功**

您可以試著加入您自己的 LINE 機器人帳號進行對話

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午6.34.27.png" alt=""><figcaption></figcaption></figure>

如果相關對話可在 [https://manager.line.biz/](https://manager.line.biz/) 和 MaiAgent 的所有對話中查看，就表示已成功串接！&#x20;

<figure><img src="../.gitbook/assets/截圖 2025-04-23 下午6.43.12.png" alt=""><figcaption></figcaption></figure>

{% hint style="warning" %}
請注意，因 LINE 官方限制，一個 LINE 群組僅能加入一隻 AI 助理，如果加入第二隻，則後來加入的那隻會被自動退出
{% endhint %}