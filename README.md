# Phaser 3 物理引擎探索 Demo

本專案旨在探索與學習 Phaser 3 遊戲框架中的 **Arcade 物理引擎**。從最初的物理碰撞研究開始，逐步發展成數個經典的遊戲 Demo，完整展示了物理引擎在 Web 遊戲開發中的核心應用。

---

## 包含的 Demo

這個專案庫包含了以下幾個從零到一建立的遊戲範例：

### 1. 瑪利歐風格平台遊戲

一個經典的橫向捲軸平台遊戲，展示了平台遊戲的核心物理機制。

**主要特色：**
* 角色移動與跳躍
* 踩踏敵人機制
* 金幣收集
* 三顆心的生命系統
* **效能測試磚塊**：可一次性產生大量敵人來觀察物理引擎的效能極限。

<p align="center">
  <em><img width="804" height="604" alt="image" src="https://github.com/user-attachments/assets/4d1ee4db-d2e4-4b7f-86da-c35080bc9750" />
</em>
</p>

### 2. 接金幣遊戲

一個快節奏的街機風格遊戲，目標是在限定時間內獲得最高分。

**主要特色：**
* 60 秒倒數計時玩法
* 掉落物（星星加分，炸彈扣分）
* 物件離開畫面後自動銷毀
* 遊戲結束計分與重新開始

<p align="center">
  <em><img width="805" height="603" alt="image" src="https://github.com/user-attachments/assets/fbb313bd-0eff-453c-8dfc-29537fcb3761" />
</em>
</p>

### 3. 太空射擊遊戲

一個頂視角的垂直捲軸射擊遊戲，模擬了經典的「雷電」或「1942」玩法。

**主要特色：**
* 可自由移動並發射子彈的玩家飛船
* 隨機產生、擁有多樣化血量的敵機
* 即時更新的敵機**血條 (Health Bar)**
* 擊中敵人與玩家死亡時的**爆炸動畫效果**

<p align="center">
  <em><img width="800" height="602" alt="image" src="https://github.com/user-attachments/assets/73dca92b-ad0f-4fe6-bf98-90278b8fec38" />
</em>
</p>

---

## 核心物理概念展示

所有 Demo 都圍繞著 Phaser 的 Arcade 物理引擎，並具體展示了以下概念：

* **物理引擎與世界設定**：如何啟用 Arcade Physics 並設定全域屬性（如重力）。
* **碰撞器 (`collider`)**：實現物件之間的固體碰撞、反彈與阻擋效果，是平台遊戲的基礎。
* **重疊器 (`overlap`)**：用於偵測物件接觸但不產生物理反應的場合，如拾取金幣、子彈擊中敵人。
* **物理群組 (`group`)**：高效能地管理大量同類型物件（如金幣、子彈、敵人）的創建、回收與集體碰撞檢測。
* **物理屬性控制**：設定單一物件的物理行為，例如 `setBounce()` (反彈)、`setVelocity()` (速度)、`allowGravity` (重力影響) 等。
* **條件式碰撞**：使用 `processCallback` 來根據特定遊戲邏輯（如玩家是否無敵）決定一次碰撞是否生效。
* **自訂類別與物理**：將物理邏輯封裝在自訂的類別中（如 `Enemy` class），實現血量、血條等複雜功能。

---

## 如何運行

由於瀏覽器的安全策略，您**不能**直接雙擊 `index.html` 檔案在瀏覽器中打開，否則將無法載入本地圖片資源。

您需要透過一個本地的 Web 伺服器來運行這些 Demo。

1.  **下載或 Clone 專案庫**
    ```bash
    git clone https://github.com/y1chu/phaser-arcade-demo
    ```

2.  **啟動本地伺服器**
    如果您安裝了 Python，最簡單的方式是在專案根目錄下運行：
    ```bash
    # Python 3.x
    python -m http.server
    ```
    或者，如果您使用 VS Code，可以安裝 [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) 擴充套件，然後右鍵點擊 `index.html` 選擇 "Open with Live Server"。

3.  **在瀏覽器中打開**
    在瀏覽器中訪問 `http://localhost:8000` (或 Live Server 提供的位址)，然後點擊您想運行的 Demo HTML 檔案。

---

## 使用技術 (Technologies Used)

* HTML5
* JavaScript (ES6)
* [Phaser 3](https://phaser.io/) (v3.55.2)
