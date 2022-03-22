# 第一組-雲端經典架構(WordPress)

## Summary
return [Summary](#summary)

- [第一組-雲端經典架構(WordPress)](#第一組-雲端經典架構wordpress)
  - [Summary](#summary)
  - [成員](#成員)
  - [AWS console URL](#aws-console-url)
  - [AWS and GCP service mapping](#aws-and-gcp-service-mapping)
  - [資源命名規則(含Tag)](#資源命名規則含tag)
  - [AWS settings](#aws-settings)
  - [wordpress document](#wordpress-document)
  - [note](#note)
  - [工作日誌](#工作日誌)
  - [會議記錄](#會議記錄)
  - [online](#online)
  - [Referance](#referance)

-----

![各組專題架構.jpg](./assets/fig/各組專題架構.jpg)
![白板.jpg](./assets/fig/白板.jpg)

不用碰程式
全都在課程內容內
1. 呈現一個網站
2. 需要有學習文件(對象：組員、面試官)

AWS 2 人
GCP 2人

wordpress的應用程式

IAM 1.系統 2.用戶

在aws或gcp上應用經典架構
在aws或gcp上架wordpress網站

-----

## 成員
return [Summary](#summary)

> (6)柴道\*
> (3)謝宜\*
> (10)張\*富
> (2)董于\*

[new_user_credentials.csv(已變更)](./assets/new_user_credentials.csv)

-----

## AWS console URL
return [Summary](#summary)

> <https://726526211588.signin.aws.amazon.com/console><br>
> <https://cfc104-project01.signin.aws.amazon.com/console><br>

-----

## AWS and GCP service mapping
return [Summary](#summary)

功能|AWS 服務|GCP 服務
-|-|-
DNS 服務|Route 53|Cloud DNS
伺服器|EC2 (Elastic Compute Cloud)|Compute Engine
資料庫|RDS (Relational Database Service)|Cloud SQL
儲存|S3 (Simple Storage Service)|Cloud Storage
權限管理|IAM (Identity and Access Management)|IAM
人員稽核|CloudTrail|
系統監控|CloudWatch|Cloud Monitoring
程式碼儲存庫|CodeCommit|Cloud Source Repositories 
程式碼編譯、建構|CodeBuild|Cloud Build
佈署|Code Deploy|Cloud Deploy
容器儲存庫|ECR (Elastic Container Registry)|Container Registry

-----

## 資源命名規則(含Tag)
return [Summary](#summary)

> {專案名稱}-{資源名稱}-{使用人員}-{應用或用途}-{備註(非必要)}<br>
> ※例如: cfc104_project1-EC2-10-wordpress-test<br>
> 專案名稱: cfc104_project1<br>
> 資源名稱: EC2<br>
> 使用人員: 10<br>
> 應用或用途: wordpress<br>
> 備註: test<br>

-----

## AWS settings
return [Summary](#summary)

> [AWS-settings](assets/AWS-settings.md)

-----

## wordpress document
return [Summary](#summary)

> [wordpress](./assets/wordpress.md)



-----

## note
return [Summary](#summary)

SystemAdministrator


wordpress 多媒體存 S3

CDN

ELB 負載均衡










-----

## 工作日誌
return [Summary](#summary)

> [工作日誌](./assets/工作日誌.md)


-----

## 會議記錄
return [Summary](#summary)

> [會議記錄](./assets/會議記錄.md)


-----

## online
return [Summary](#summary)

[this page](https://github.com/rockexe0000/cfc104_project1)



-----

## Referance

[AWS雲端經典架構建置WordPress網站 (參考資料1)](assets/AWS雲端經典架構建置WordPress網站(參考資料1).md)

