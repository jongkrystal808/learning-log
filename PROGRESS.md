# AI Agent / 自動化 / AI 基礎設施 求職學習進度

- 期間：2026/11/9 – 2027/2/14（14 週，每週約 10 小時）
- 主打專案：測試 Log 分析 Agent
- 更新方式：每週日最後 10 分鐘，勾選任務、寫三行筆記、規劃下週第一件事
- 規則：每階段檢核沒過，就用下一週補，不往下走

## 總覽

| 週 | 起始日 | 階段 | 主題 | 本週產出 | 狀態 |
|---|---|---|---|---|---|
| 1 | 11/9 | 一、基本功 | Git、GitHub、shell；AI / ML 概念 | 3 個舊專案上 GitHub；能口述訓練 / 推論 / 評估 | ☐ |
| 2 | 11/16 | 一、基本功 | scikit-learn 實驗、評估指標 | NG 資料分類 notebook，含 precision / recall | ☐ |
| 3 | 11/23 | 一、基本功 | Python 進階、FastAPI、pytest | 一個有測試的 FastAPI 服務 | ☐ |
| 4 | 11/30 | 二、Agent | Claude API、tool use | 單一工具 agent，可在終端機跑 | ☐ |
| 5 | 12/7 | 二、Agent | 手寫 agent loop、多工具、記憶 | 不靠框架的完整 agent loop | ☐ |
| 6 | 12/14 | 二、Agent | Agent SDK、MCP、subagent | 自寫 MCP server，接上 Claude | ☐ |
| 7 | 12/21 | 三、品質 | RAG：文件解析、embedding、向量庫 | 能解析 PDF / Excel 並查詢歷史 NG 的 RAG 模組 | ☐ |
| 8 | 12/28 | 三、品質 | evals、可靠性、可觀測性 | 評測腳本、分數報告、追蹤儀表板 | ☐ |
| 9 | 1/4 | 四、基礎設施 | Docker 進階、compose、registry | multi-stage 映像，推到 registry | ☐ |
| 10 | 1/11 | 四、基礎設施 | GitHub Actions、GCP 部署、安全 | CI 綠燈，服務部署上雲 | ☐ |
| 11 | 1/18 | 四、基礎設施 | SQL 建模、ETL、API 驗證 | 一條 ETL；API 有驗證、日誌與限流 | ☐ |
| 12 | 1/25 | 四、基礎設施 | TypeScript 前端、選配小專案 | 簡易前端；n8n / LineBot / Ollama + Whisper 擇二 | ☐ |
| 13 | 2/1 | 五、求職 | README、demo 影片、履歷 | 作品集與履歷完成 | ☐ |
| 14 | 2/8 | 五、求職 | 模擬面試、投遞 | 投出第一批履歷（至少 10 家） | ☐ |

春節（2/6 前後）落在第 13–14 週，這兩週預留彈性，必要時往後順延。

## 每週時段

- 平日晚上 4 天，各 1 小時：看教材、讀文件、做小練習
- 週六約 2.5 小時：動手做本週主要任務
- 週日約 2.5 小時：完成驗收、寫筆記、commit，最後 10 分鐘更新本文件

## 第 1 週（11/9）：Git 與 AI 概念入門

- [ ] 讀 Pro Git 前 3 章，用 commit、branch、pull request 管理一個專案
- [ ] 3 個舊專案整理後上傳，移除密碼、內部路徑和客戶資料
- [ ] 看 3Blue1Brown 神經網路系列
- [ ] 看 Andrej Karpathy 的 Intro to Large Language Models
- [ ] 一頁筆記：訓練、推論、評估各是什麼，各舉一個產線例子
- 驗收：GitHub 上有 3 個 repo；能不看筆記講 5 分鐘

## 第 2 週（11/16）：第一次做 ML 實驗

- [ ] 學 scikit-learn 流程：載入資料、切 train / test、fit、predict、評估
- [ ] 用去識別化的 NG 異常明細訓練簡單分類器
- [ ] 算 accuracy、precision、recall、confusion matrix，解釋 accuracy 在不平衡資料上為何會騙人
- [ ] 故意讓模型 overfit 一次，寫下差異
- [ ] 讀 Google ML Crash Course 的「分類」與「資料」兩章
- 驗收：一份 notebook 附結論；能回答「為什麼評估要用沒看過的資料」

## 第 3 週（11/23）：Python 與 FastAPI 進階

- [ ] 複習 type hints、dataclass、pydantic、async / await、context manager、例外處理
- [ ] 做一個 FastAPI 服務：3 個 endpoint、SQLite、pydantic 模型
- [ ] 寫 pytest：單元測試、fixture、mock，覆蓋率 70% 以上
- [ ] 不看 AI，重寫舊專案的一個核心函式並說明每一行
- [ ] 用 MIT The Missing Semester 練 grep、sed、jq、管線、ssh
- 驗收：repo 有 README 與測試，pytest 全綠；能解釋 async 與同步的差別

### 階段一檢核（第 3 週結束）

- [ ] 能口述訓練、推論、評估與 overfitting
- [ ] GitHub 上至少 4 個 repo
- [ ] 能不看 AI 寫出有測試的 FastAPI 服務

## 第 4 週（11/30）：Claude API 與 tool use

- [ ] 申請 API key，用環境變數存放，`.gitignore` 排除 `.env`
- [ ] 呼叫 Messages API：system prompt、多輪對話、串流輸出
- [ ] 實作 tool use：定義讀 log 檔的工具，由模型決定何時呼叫
- [ ] 記錄 token 用量與每次呼叫成本
- [ ] 練習 prompt 設計：角色、格式、範例，比較輸出差異
- 驗收：`python agent.py <log檔>` 能讀 log 並回答問題

## 第 5 週（12/7）：手寫 agent loop

- [ ] 實作迴圈：模型回應 → 執行工具 → 回傳結果 → 直到最終答案
- [ ] 至少 3 個工具：讀檔、查 SQLite、計算統計
- [ ] 加上限：最大步數、逾時、單次 token 預算
- [ ] 簡單記憶：保存對話摘要，處理 context 過長
- [ ] 處理工具錯誤：回傳錯誤訊息讓模型自行修正
- 驗收：能完成「分析這份 log 並找出 NG 原因」；能畫出 loop 流程圖

## 第 6 週（12/14）：Agent SDK 與 MCP

- [ ] 用 Claude Agent SDK 重做第 5 週的 agent，比較哪些程式碼可刪
- [ ] 自寫 MCP server，把「查測試紀錄」包成工具並接到 Claude
- [ ] 試用 subagent：拆成「分類 NG」與「撰寫報告」
- [ ] 日常改用 Claude Code，練習 CLAUDE.md、權限、hooks
- [ ] 比較筆記：手寫 loop、Agent SDK、Claude Code 各適合什麼情境
- 驗收：MCP server 在 repo 內，含 README 與安裝步驟；能說明 MCP 解決什麼問題

### 階段二檢核（第 6 週結束）

- [ ] 不靠框架手寫過 agent loop
- [ ] 有一個自己的 MCP server
- [ ] 能說明 tool use、subagent、MCP 的差別

## 第 7 週（12/21）：RAG 與文件解析

- [ ] 理解流程：切塊 → embedding → 向量庫 → 檢索 → 放進 prompt
- [ ] 用 SQLite FTS5、Chroma 或 pgvector 擇一建立向量庫
- [ ] 灌入歷史 NG 紀錄與處置方式
- [ ] 實驗 chunk 大小與檢索筆數，記錄對品質的影響
- [ ] 回答附來源紀錄編號
- [ ] 用 pypdf / pdfplumber 解析 PDF，用 pandas / openpyxl 讀 Excel
- [ ] 比較「整份直接給 Claude」與「先解析再切塊」的成本與準確度
- [ ] 讓 Claude 讀掃描圖或圖面 PDF，輸出結構化 JSON並人工核對
- 驗收：能查歷史紀錄的 RAG 模組，回答附來源

## 第 8 週（12/28）：Evals、可靠性與可觀測性

- [ ] 從 95 筆異常明細挑 30–50 筆，人工標好標準答案
- [ ] 評測腳本：輸出準確率、失敗案例清單、每題成本
- [ ] 改 prompt 或換模型後重跑，保留分數歷史
- [ ] 重試、指數退避、逾時、速率限制處理
- [ ] 結構化 logging：輸入、工具呼叫、token、耗時
- [ ] 設定成本上限
- [ ] docker compose 啟動 Grafana + Loki，做一張儀表板
- [ ] 接上 Langfuse 看 trace，找出最慢與最貴的步驟
- [ ] 模擬一次故障，寫一頁根因分析
- 驗收：評測報告含準確率、成本、前 5 個失敗案例分析

### 階段三檢核（第 8 週結束）

- [ ] 有評測集與可重跑的評測腳本
- [ ] 能說明 RAG 何時有用、何時沒用
- [ ] 能回答「你怎麼知道你的 agent 變好了」

提醒：評測集若來自公司資料，需去識別化，並先確認公司規定。

## 第 9 週（1/4）：Docker 進階

- [ ] multi-stage Dockerfile，比較前後映像大小
- [ ] 非 root 使用者、`.dockerignore`、HEALTHCHECK
- [ ] compose 組合 agent API、資料庫、向量庫，用 volume 保存資料
- [ ] 用語意化版本或 commit hash 打標籤，推到 Docker Hub 或 GHCR
- [ ] 學會用 `docker logs`、`docker exec`、`docker stats` 排查
- 驗收：一行 `docker compose up` 啟動整個系統；映像在 registry 有版本標籤

## 第 10 週（1/11）：CI/CD、雲端、安全

- [ ] GitHub Actions：push 跑 lint 與 pytest，main 自動建置並推送映像
- [ ] 部署到 GCP Cloud Run，設定環境變數與 secrets
- [ ] 理解 Kubernetes 的 Pod、Deployment、Service（能講清楚即可）
- [ ] 安全清單：API key 不進 repo、最小權限、輸入驗證、工具白名單
- [ ] 實驗 prompt injection，寫出防禦做法
- [ ] 檔案與指令工具限制在指定資料夾或 sandbox
- 驗收：CI 綠燈；有可展示的 URL；有一頁安全說明

注意：雲端會產生費用，開始前設預算警示，用完即關閉。

## 第 11 週（1/18）：SQL、ETL 與 API 驗證

- [ ] SQL：JOIN、GROUP BY、子查詢、視窗函式、索引與 EXPLAIN，各寫 10 題
- [ ] 資料建模：事實表與維度表，畫 ER 圖
- [ ] ETL：Excel / CSV 抽取、清洗、載入資料庫，並排程每日執行
- [ ] API：API key 或 JWT 驗證、速率限制、結構化日誌、健康檢查，優化一個慢查詢
- [ ] 用匯出檔模擬從 SAP 或 MES 取資料
- 驗收：一條可重跑的 ETL；慢查詢在加索引前後有耗時比較

## 第 12 週（1/25）：TypeScript 前端與選配

- [ ] 既有 React 專案改成 TypeScript，做呼叫 agent API 的簡易介面
- [ ] 選配 A：n8n 每日自動抓新 log、呼叫 agent、寄出摘要
- [ ] 選配 B：LineBot 傳 log 片段回覆分類結果
- [ ] 選配 C：Ollama 本機模型 + Whisper 轉錄，與 Claude 比較
- [ ] 用 Playwright 寫一個端對端測試
- 驗收：前端能展示完整流程；選配至少完成兩項，各有說明文字

### 階段四檢核（第 12 週結束）

- [ ] 映像在 registry、CI 自動建置
- [ ] 服務已部署上雲
- [ ] 能說明 prompt injection 與對策；已完成 ETL 與有驗證的 API；有簡易前端

## 第 13 週（2/1）：作品集與履歷

- [ ] 確認公司保密規定：只用去識別化資料與自己寫的程式
- [ ] 每個 repo 的 README：解決什麼問題、架構圖、如何執行、評測結果、已知限制
- [ ] 錄 2–3 分鐘 demo 影片或 GIF，放在 README 最上方
- [ ] 履歷改寫：測試與製造經歷寫成可量化成果
- [ ] 履歷加入「專案」區，附 GitHub 連結
- [ ] 整理 LinkedIn 與 104，關鍵字含 AI Agent、Python、Docker、MCP
- 驗收：朋友只看 README，3 分鐘內能說出專案做什麼

## 第 14 週（2/8）：面試練習與投遞

- [ ] 用概念題庫做 3 次模擬面試，錄音檢討
- [ ] 準備 3 個故事：解決難題、與人合作、失敗後改善
- [ ] 準備「為什麼從測試轉 AI 自動化」的 1 分鐘回答
- [ ] 投遞第一批履歷，至少 10 家，記錄在追蹤表
- [ ] 面試後寫復盤，更新題庫
- 驗收：10 份履歷已投出；至少完成 3 次模擬面試

## 落後時的取捨順序（從先砍到最後砍）

1. Kubernetes 概念與雲端部署：改只做 Docker 與 CI，上雲排到求職期間補
2. 加分功能與第 12 週選配小專案
3. 向量庫：改用 SQLite FTS5
4. 不砍：Git、AI 基礎概念、手寫 agent loop、MCP server、evals、README 與 demo

## 每週筆記

每週日填三行：學到什麼、卡在哪、下週第一件事。卡超過 90 分鐘就縮小問題、寫最小可重現範例再求助。

### 第 1 週（11/9）
- 學到：
- 卡在：
- 下週第一件事：

### 第 2 週（11/16）
- 學到：
- 卡在：
- 下週第一件事：

### 第 3 週（11/23）
- 學到：
- 卡在：
- 下週第一件事：

### 第 4 週（11/30）
- 學到：
- 卡在：
- 下週第一件事：

### 第 5 週（12/7）
- 學到：
- 卡在：
- 下週第一件事：

### 第 6 週（12/14）
- 學到：
- 卡在：
- 下週第一件事：

### 第 7 週（12/21）
- 學到：
- 卡在：
- 下週第一件事：

### 第 8 週（12/28）
- 學到：
- 卡在：
- 下週第一件事：

### 第 9 週（1/4）
- 學到：
- 卡在：
- 下週第一件事：

### 第 10 週（1/11）
- 學到：
- 卡在：
- 下週第一件事：

### 第 11 週（1/18）
- 學到：
- 卡在：
- 下週第一件事：

### 第 12 週（1/25）
- 學到：
- 卡在：
- 下週第一件事：

### 第 13 週（2/1）
- 學到：
- 卡在：
- 下週第一件事：

### 第 14 週（2/8）
- 學到：
- 卡在：
- 下週第一件事：
