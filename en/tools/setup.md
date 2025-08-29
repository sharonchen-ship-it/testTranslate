---
icon: gear-complex
---

# Create Tool

本指南將引導您完成在平台中建立新工具的步驟。工具是擴展 AI 助理能力的關鍵，允許它與外部服務互動或執行特定任務。

{% hint style="info" %}
[工具製作 AI 助理](https://chat.maiagent.ai/web-chats/27934296-105a-4f3f-80f0-7e9dcdb638d3)
{% endhint %}

## 1. 進入工具管理介面

首先，請從左側導航欄進入「 <mark style="color:blue;">AI 功能</mark>」區塊，然後點擊「<mark style="color:blue;">🔧 工具</mark>」。進入工具列表頁面後，點選右上角的「<mark style="color:blue;">➕ 新增工具</mark>」按鈕。

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.04.03.png" alt="工具列表頁面與新增按鈕"><figcaption><p>點擊「➕ 新增工具」開始建立</p></figcaption></figure>

## 2. 設定顯示名稱

在「新增工具」表單中，第一個需要填寫的是「<mark style="color:blue;">顯示名稱</mark>」。

* **用途**：此名稱將會顯示在平台介面中，供所有用戶查看。
* **建議**：選擇一個能清晰表達工具主要功能的名稱，方便用戶理解。此名稱沒有嚴格的格式限制。

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.09.29.png" alt="填寫顯示名稱"><figcaption><p>為您的工具設定一個易於理解的顯示名稱</p></figcaption></figure>

## 3. 設定工具名稱

接下來是「<mark style="color:blue;">工具名稱</mark>」欄位。

* **用途**：此名稱是 AI 助理在內部呼叫和識別此工具時使用的唯一標識符。
* **命名規則 (重要)**：
  * 必須使用英文。
  * 只能包含：
    * 小寫英文字母 (a-z)
    * 大寫英文字母 (A-Z)
    * 數字 (0-9)
    * 底線 (`_`)
    * 連字符 (`-`)
  * **範例**：`get_weather_forecast`, `database-query-tool`

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.18.55.png" alt="填寫工具名稱"><figcaption><p>設定符合命名規則的工具名稱</p></figcaption></figure>

## 4. 選擇工具類型

選擇「<mark style="color:blue;">工具類型</mark>」。根據您的服務所使用的協定類型選擇工具類型。

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.19.46.png" alt="工具類型選擇介面截圖"><figcaption></figcaption></figure>

目前支援以下主要類型：

### a. 🌐 API 工具

* **最常用類型**。用於連接和呼叫外部的 HTTP/HTTPS API 服務。
* **常見應用**：獲取天氣資訊、查詢外部資料庫、觸發 webhook、與第三方服務整合等。
* **必要配置**：API 端點 URL、HTTP 方法、請求標頭 (Headers)、參數結構 (Parameters Schema)。

### b. ☁️ MCP 工具

* **模型上下文協定**（Model Context Protocol, MCP）,透過標準化協定實現伺服器、用戶端與主機的協作。
* **適用場景**：讓 AI 助理調用外部工具執行更複雜和實用的任務。
* **必要配置**：MCP 伺服器 URL、參數、環境變數等。

## 5. 撰寫工具描述

在「<mark style="color:blue;">工具描述</mark>」欄位中，用戶可以提供清晰且詳細的工具說明。

* **重要性**：良好的描述能幫助 AI 助理更準確地理解：
  * 工具的功能和目的。
  * 何時應該使用這個工具。
  * 如何解釋工具的輸出結果。
* **建議內容**：說明工具做什麼、輸入什麼、輸出什麼，以及任何使用上的注意事項。

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.25.44.png" alt="工具描述欄位截圖"><figcaption><p>撰寫清晰、詳細的工具描述</p></figcaption></figure>

## 6. API 配置詳細設定

若您選擇了「<mark style="color:blue;">🌐 API 工具</mark>」，請完成以下設定：

### a. 🔗 API URL

* 填寫目標 API 端點的完整網址 (包含 `http://` 或 `https://`)。
* **範例**：`https://api.openweathermap.org/data/2.5/weather`

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.28.12.png" alt=""><figcaption></figcaption></figure>

### b. 📮 HTTP 方法

* 從下拉選單選擇 API 服務要求的 HTTP 動詞：
  * `GET`：通常用於獲取資源。
  * `POST`：通常用於創建新資源或提交數據。
  * `PUT`：通常用於完整替換或更新資源。
  * `DELETE`：通常用於刪除資源。

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.29.09.png" alt=""><figcaption></figcaption></figure>

### c. 📰 標頭 (Headers)

* 點擊「<mark style="color:blue;">➕ 新增標頭</mark>」來定義隨請求發送的 HTTP 標頭。
* **格式**：必須是有效的 JSON 物件，其中鍵 (Key) 是標頭名稱，值 (Value) 是標頭內容 (字串)。
* **常見用途**：
  * 身份驗證 (`Authorization`, `X-API-Key`)
  * 指定內容類型 (`Content-Type`)
  * 指定接受的回應格式 (`Accept`)
*   **範例**：

```json
    {
      "Content-Type": "application/json; charset=utf-8",
      "Authorization": "Bearer {{SECRET_API_TOKEN}}",
      "Accept": "application/vnd.github.v3+json"
    }
    ```

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.32.15.png" alt="API 標頭設定截圖"><figcaption><p>設定必要的 HTTP 請求標頭</p></figcaption></figure>

### d. 🧩 參數結構 (Parameters Schema)

* **核心設定**：定義 AI 助理在呼叫此工具時，可以或必須提供哪些參數，以及這些參數的格式。
* **格式**：使用標準的 **JSON Schema** 格式。
* **關鍵元素**：
  * `type: "object"`：表示參數是一個物件。
  * `properties`: 定義每個參數的物件。
    * **參數名稱** (例如 `"search"`)：對應的物件包含該參數的細節。
      * `type`: 參數的資料類型 (`string`, `integer`, `number`, `boolean`, `array`, `object`)。
      * `description`: 對 AI 助理的說明，解釋此參數的意義。
      * `default` (可選): 參數的默認值。
      * `enum` (可選): 如果參數值只能是特定幾個選項之一，在此列出。
  * `required`: 一個包含所有**必填**參數名稱的陣列。
*   **範例** (影音搜尋工具)：

```json
    {
        "type": "object",
        "properties": {
            "limit": {
                "type": "integer",
                "minimum": 1,
                "description": "回傳結果數量上限"
            },
            "fields": {
                "type": "string",
                "description": "以逗號分隔的欄位清單"
            },
            "search": {
                "type": "string",
                "description": "搜尋關鍵字"
            }
        },
        "required": ["search"]
    }
    ```

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.42.41.png" alt="API 參數結構設定截圖"><figcaption><p>使用 JSON Schema 精確定義 API 參數</p></figcaption></figure>

## 7. MCP 配置詳細設定

若您在「4. 選擇工具類型」時選擇了「<mark style="color:blue;">☁️ MCP 工具</mark>」，則需要完成以下設定。MCP ( Model Context Protocol )  工具用於整合多雲平台服務或執行本地客戶端應用程式。

### a. ⚙️ MCP 伺服器 URL

* **用途**：MaiAgent 目前接受外部的 MCP 伺服器，透過提供 MCP 伺服器的服務位址(URL)， AI 助理就可以調用 MCP 服務連結外部應用。
* **格式**：
  * 請填寫完整的 URL (例如：`https://mcp.dev/maiagent/mcp_service`)。
* **注意**：此欄位為必填。

<figure><img src="../.gitbook/assets/截圖 2025-05-11 上午11.26.15.png" alt="MCP 客戶端 URL 或命令設定示意圖"><figcaption><p>設定 MCP 客戶端 URL 或命令</p></figcaption></figure>

### b. 🎛️ MCP 命令參數 (mcp\_args)

* **用途**：定義在執行 MCP 命令或呼叫 MCP 服務時需要傳遞的參數。
* **格式**：建議使用 JSON 陣列 (Array) 的格式，其中每個元素都是一個字串代表一個參數。
  *   **範例** (JSON 陣列)：

```json
      [
        "--user",
        "admin",
        "--config",
        "/path/to/config.yaml"
      ]
      ```
  * 如果您輸入的是一個以逗號分隔的字串 (例如：`arg1,arg2,arg3`)，系統會嘗試將其解析為參數列表。為避免歧義，推薦使用 JSON 陣列。
* **留空**：如果命令或服務不需要額外參數，此欄位可以留空。

<figure><img src="../.gitbook/assets/截圖 2025-05-11 上午11.29.42.png" alt="MCP 命令參數設定示意圖"><figcaption><p>設定 MCP 命令參數</p></figcaption></figure>

### c. 🌳 MCP 環境變數 (mcp\_env)

* **用途**：為 MCP 命令的執行環境設定必要的環境變數。
* **格式**：必須是有效的 JSON 物件，其中鍵 (Key) 是環境變數的名稱，值 (Value) 是環境變數的內容 (字串)。
  *   **範例**：

```json
      {
        "API_KEY": "{{SECRET_MCP_API_KEY}}",
        "REGION": "us-west-1",
        "DEBUG_MODE": "true"
      }
      ```
* **留空**：如果不需要設定特定的環境變數，此欄位可以留空。

<figure><img src="../.gitbook/assets/截圖 2025-05-11 上午11.28.39.png" alt="MCP 環境變數設定示意圖"><figcaption><p>設定 MCP 環境變數</p></figcaption></figure>

### d. 🔑 MCP 允許的子工具 (mcp\_allowed\_tools)

* **用途**：指定在此 MCP 客戶端下，AI 助理被授權可以使用的具體子工具列表。一個 MCP 客戶端可能提供多個不同的功能或子工具。
* **格式**：JSON 陣列 (Array) 的格式，其中每個元素都是一個字串，代表一個允許使用的子工具名稱。
  *   **範例**：

```json
      [
        "get_system_load",
        "run_backup_job",
        "query_database_status"
      ]
      ```
* **自動偵測/留空**：如果此欄位留空或未提供，系統在初次連接 MCP 客戶端時，會嘗試自動偵測所有可用的子工具，並預設允許所有偵測到的子工具。若您希望限制 AI 助理只能使用特定的子工具，請在此明確列出。

<figure><img src="../.gitbook/assets/截圖 2025-05-11 上午11.32.11.png" alt="MCP 允許的子工具設定示意圖"><figcaption><p>設定 MCP 允許使用的子工具</p></figcaption></figure>

## 8. 💾 儲存工具

確認所有設定無誤後，捲動到頁面底部，點擊「<mark style="color:blue;">確認</mark>」按鈕。您的新工具就建立完成了！

<figure><img src="../.gitbook/assets/截圖 2025-05-03 下午6.44.22.png" alt=""><figcaption></figcaption></figure>