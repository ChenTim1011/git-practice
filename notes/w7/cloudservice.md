## 雲端服務簡介

我想要更加了解 AWS 相關的雲端服務，可以如何應用。

1. IAM (Identity and Access Management)

用途：IAM 是 AWS 的身分與存取管理服務，主要用來管理誰可以存取 AWS 資源，確保正確的人員和服務擁有適當的權限。 

情境範例：公司內部使用 IAM 來管理不同開發者對 AWS 資源的存取權限，例如設定某個開發者只能對 S3 儲存桶有讀取權限，而對其他資源無法操作。

2. EC2 (Elastic Compute Cloud)

用途：EC2 提供彈性虛擬伺服器，可以根據需求動態擴展或縮減計算能力。

情境範例：啟動一個 EC2 實例來運行網站應用程式，並根據流量需求自動調整伺服器數量，減少高峰期間的延遲。

3. S3 (Simple Storage Service)

用途：S3 是物件儲存服務，提供可擴展且具備高度耐久性的儲存空間，用於存放和檔案分享。

情境範例：S3 可以用來儲存網站靜態內容如圖像、影片，並通過 CloudFront 分發到全球使用者，以提供快速的內容交付。

4. RDS (Relational Database Service)

用途：RDS 提供管理型的關聯式資料庫服務，支援 MySQL、PostgreSQL、MariaDB 等多種資料庫。 

情境範例：開發者可以在 RDS 上啟動一個 PostgreSQL 資料庫，將應用程式的使用者資料、交易記錄儲存在此，並自動備份和縮放。

5. ElastiCache

用途：ElastiCache 是管理型的記憶體快取服務，支援 Redis 和 Memcached，幫助加速應用程式的資料存取速度。

情境範例：電商網站可以利用 ElastiCache 來快取頻繁查詢的商品清單，減少每次都從資料庫取得資料的時間，提升網站回應速度。

6. Lambda

用途：Lambda 是無伺服器運算服務，允許你在不管理伺服器的情況下執行程式碼，根據需求自動擴展。 

情境範例：當使用者上傳文件到 S3 時，自動觸發 Lambda 函數來進行圖片壓縮或文件格式轉換，無需手動介入或管理伺服器。

7. API Gateway

用途：API Gateway 是管理 API 的服務，幫助開發者建立、發佈、維護和保護 API，允許使用者與後端服務互動。

情境範例：開發者使用 API Gateway 來管理一個行動應用的後端 API，將來自應用的請求轉發至 Lambda 函數或 EC2 實例。

8. Step Functions

用途：Step Functions 提供一種服務，能夠幫助開發者輕鬆編排分散式應用程式和微服務的執行流程。 

情境範例：使用 Step Functions 來管理一個文件處理流程，包含上傳、處理、驗證和儲存的每一步操作，確保每個步驟的成功完成。

9. SQS (Simple Queue Service)

用途：SQS 是一個完全管理的訊息佇列服務，用於分散式系統之間的訊息傳遞，確保應用程式的解耦和彈性。 

情境範例：在電商網站中，當顧客下訂單後，將訂單訊息發送到 SQS 佇列，後端的訂單處理系統逐一處理訂單，確保訂單不會遺漏或重複處理。

10. EKS/ECS (Elastic Kubernetes Service / Elastic Container Service)

用途：EKS 是一個完全管理的 Kubernetes 容器服務，而 ECS 是 AWS 的容器編排服務，專門用於管理和擴展 Docker 容器。 

情境範例：使用 EKS 來部署和管理多個微服務，確保應用程式的高可用性，並根據流量負載自動擴展或縮減資源。

11. VPC (Virtual Private Cloud)

用途：VPC 允許你在 AWS 上建立一個隔離的網路環境，並自訂網路設定如 IP 位址範圍、子網路和路由表。

情境範例：公司可以在 VPC 內建立一個安全的內部網路，並將 EC2 實例放置在不同的子網路中以控制內部和外部流量的路徑。

12. ELB (Elastic Load Balancing) / ASG (Auto Scaling Group)

用途：ELB 用於自動分配流量到多個 EC2 實例，ASG 則根據需求自動擴展或縮減 EC2 資源，確保應用程式在負載變動時維持穩定運行。 

情境範例：當網站流量突然增長時，ASG 自動增加 EC2 實例數量，並通過 ELB 平衡負載，確保網站不會因為過多的流量而宕機。

13. CloudFront

用途：CloudFront 是 AWS 的全球內容交付網路（CDN）服務，能夠加速靜態和動態內容的分發。 

情境範例：網站開發者使用 CloudFront 來加速全球使用者存取網站的圖片、影片和其他靜態資源，提供更快速的使用者體驗。

14. CloudWatch

用途：CloudWatch 用於監控 AWS 資源和應用程式的運行情況，並提供日誌、指標和警報。

情境範例：開發者使用 CloudWatch 來監控 EC2 實例的 CPU 使用率，當 CPU 過高時自動觸發警報以通知相關人員進行調整。

15. Logs

用途：CloudWatch Logs 提供應用程式日誌的收集和管理功能，便於監控和調試。

情境範例：當應用程式發生錯誤時，開發者可以檢視 CloudWatch Logs 中的日誌記錄，了解詳細錯誤訊息並進行問題排查。

16. Metrics

用途：CloudWatch Metrics 收集和展示 AWS 資源的性能資料，幫助使用者監控應用程式的健康狀況。 

情境範例：監控 EC2 實例的網絡流量、記憶體使用率等指標，確保伺服器運作穩定並及時調整資源。

17. Alarms

用途：CloudWatch Alarms 根據設置的指標閾值來發出警報，便於及時採取行動。 

情境範例：設定警報當 EC2 的 CPU 使用率超過 80% 時發出通知，讓系統管理員進行伺服器調整。

18. EventBridge

用途：EventBridge 是一個無伺服器的事件總線，用於處理應用程式內外的事件流，並將事件路由到合適的目標。

情境範例：當 S3 中有文件上傳時，EventBridge 可以觸發相應的 Lambda 函數來進行文件處理，實現系統間的自動化整合。
