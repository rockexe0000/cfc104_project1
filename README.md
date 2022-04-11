# 第一組-雲端經典架構(WordPress)

## Summary
return [Summary](#summary)

- [第一組-雲端經典架構(WordPress)](#第一組-雲端經典架構wordpress)
  - [Summary](#summary)
  - [Members](#members)
  - [AWS console URL](#aws-console-url)
  - [Resource naming rules (including tags)](#resource-naming-rules-including-tags)
  - [CI/CD](#cicd)
  - [AWS and GCP service mapping](#aws-and-gcp-service-mapping)
  - [Architecture Diagram](#architecture-diagram)
    - [AWS](#aws)
  - [Todo list](#todo-list)
  - [AWS settings](#aws-settings)
  - [Wordpress document](#wordpress-document)
  - [Note](#note)
  - [Work log](#work-log)
  - [Meeting minutes](#meeting-minutes)
  - [Online](#online)
  - [Referance](#referance)

-----

![各組專題架構.jpg](./assets/fig/各組專題架構.jpg)
![白板.jpg](./assets/fig/白板.jpg)
![簡報搞.jpg](./assets/fig/ScreenShot2022-03-30at9.49.17AM.png)

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

## Members
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

## Resource naming rules (including tags)
return [Summary](#summary)

> {專案名稱}-{資源名稱}-{使用者ID(人員/群組/其他服務)}-{應用或用途}-{備註(非必要)}<br>
> ※例如: cfc104_project1-EC2-10-wordpress-test<br>
> 專案名稱: cfc104_project1<br>
> 資源名稱: EC2<br>
> 使用者ID: 10<br>
> 應用或用途: wordpress<br>
> 備註: test<br>

-----

## CI/CD

https://dev.classmethod.jp/articles/aws-hands-on-for-beginners-cicd/

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
人員稽核|CloudTrail|Cloud Audit Logs
系統監控|CloudWatch|Cloud Monitoring
流程管理|CodePipeline|Cloud Source Repositories
程式碼儲存庫|CodeCommit|Cloud Source Repositories 
程式碼編譯、建構|CodeBuild|Cloud Build
佈署|Code Deploy|Cloud Deploy
容器儲存庫|ECR (Elastic Container Registry)|Container Registry

> https://comparecloud.in/?fbclid=IwAR3ACOiRt23TB8E7ncLsmDSDSHbTF4YxMIymT2rJWwusZfgMVYX1TPVwl0M

-----

## Architecture Diagram
return [Summary](#summary)

### AWS
> ![project-AWS-Architecture.svg](./assets/fig/project-AWS-Architecture.svg)

-----

## Todo list
return [Summary](#summary)




目標
建立 wordpress 網站並在雲端維運

流程概要

  1) 本地端建置 wordpress
  2) wordpress 網站匯出
  3) AWS 環境建構
  4) wordpress 網站匯入AWS環境
  5) GCP 環境建構
  6) wordpress 網站匯入GCP環境
  7) 測試


使用者角色

- Wordpress website editor
- AWS manager
- GCP manager
- Project manager


建置步驟




參數
Name | Value
-|-

Account Alias|cfc104-project01

Name | Value
-|-
Group name|cfc104_project
User name|cfc104_02, cfc104_03, cfc104_06, cfc104_10

Name | Value
-|-
VPC|cfc104-project1-wordpress-VPC
public subnet|cfc104-project1-wordpress-subnet-public|
private subnet|cfc104-project1-wordpress-subnet-private|



Name | Value
-|-
EC2|cfc104-project1-wordpress-ec2-public
Amazon Machine Image (AMI)|Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type
Instance Type|t2.micro
Network|cfc104-project1-wordpress-VPC
subnet|cfc104-project1-wordpress-subnet-public
Volume Type|General Purpose SSD (gp2)
Security Group|cfc104-project1-wordpress-sg-public


Domain name|cfc104.project1.com
RDS CNAME|rds.cfc104.project1.com


S3|cfc104-project1-wordpress-s3



- wordpress set up
  - [X] Docker
    - docker-compose
  - [X] web site
  - [X] plugins
    -  woocommerce
    - all-in-one-wp-migration

- AWS set up
  - [X] IAM
  - [X] VPC
  - [X] EC2
  - [X] RDS
  - [X] S3
  - [X] Route53(private route)
  - [X] CloudTrail
  - [X] CloudWatch
  - [ ] ~~SSM~~

- GCP set up
  - [X] IAM
  - [X] VPC
  - [X] GCE
  - [X] CloudSQL
  - [X] Cloud Storage
  - [X] Cloud DNS(private route)
  - [ ] Cloud Audit log
  - [X] Cloud Monitoring
  - [ ] ~~Opsagent(optional)~~




-----

## AWS settings
return [Summary](#summary)

> [AWS-settings](assets/AWS-settings.md)

-----

## Wordpress document
return [Summary](#summary)

> [wordpress](./assets/wordpress.md)



-----

## Note
return [Summary](#summary)

[test to wordpress.md#note](assets/wordpress.md#note)

SystemAdministrator


wordpress 多媒體存 S3

CDN

ELB 負載均衡

https://medium.com/tensult/configure-ftp-on-aws-ec2-85b5b56b9c94








-----

## Work log
return [Summary](#summary)

> [Work log](./assets/WorkLog.md)


-----

## Meeting minutes
return [Summary](#summary)

> [Meeting minutes](./assets/MeetingMinutes.md)


-----

## Online
return [Summary](#summary)

[this page](https://github.com/rockexe0000/cfc104_project1)



-----

## Referance
return [Summary](#summary)

[AWS雲端經典架構建置WordPress網站 (參考資料1)](assets/AWS雲端經典架構建置WordPress網站(參考資料1).md)

