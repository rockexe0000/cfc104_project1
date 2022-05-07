#  AWS set up




## Summary
return [Summary](#summary)

- [AWS set up](#aws-set-up)
  - [Summary](#summary)
  - [IAM](#iam)
    - [Group](#group)
    - [User](#user)
    - [User groups](#user-groups)
    - [Account Alias](#account-alias)
  - [CloudWatch](#cloudwatch)
    - [Billing Alarms](#billing-alarms)
      - [帳單超過 10 USD 通知](#帳單超過-10-usd-通知)
    - [EC2 Alarms](#ec2-alarms)
      - [CPU利用率超過80%通知](#cpu利用率超過80通知)
  - [EC2](#ec2)
  - [~~ECR~~](#ecr)
  - [RDS](#rds)
  - [VPC](#vpc)
    - [internet gateway](#internet-gateway)
    - [igw attach to VPC](#igw-attach-to-vpc)
    - [subnet](#subnet)
      - [public subnet](#public-subnet)
      - [private subnet](#private-subnet)
    - [~~NAT gateway for private subnet~~](#nat-gateway-for-private-subnet)
    - [route table](#route-table)
    - [route table for private subnet](#route-table-for-private-subnet)
    - [test ssh 172.16.0.10 -> 172.16.101.10](#test-ssh-17216010---1721610110)
  - [godaddy DNS 管理](#godaddy-dns-管理)
  - [Route53](#route53)
    - [Route53 private hosted zones add RDS](#route53-private-hosted-zones-add-rds)
  - [S3](#s3)
    - [Automatically uploads media to Amazon S3](#automatically-uploads-media-to-amazon-s3)
      - [Properties -> Transfer acceleration -> Enabled](#properties---transfer-acceleration---enabled)
      - [Permissions -> CORS](#permissions---cors)
      - [add media-cloud user](#add-media-cloud-user)
        - [Create policy](#create-policy)
    - [S3使用前](#s3使用前)
    - [S3使用後](#s3使用後)
  - [CloudTrail](#cloudtrail)
  - [SSM](#ssm)
    - [建立一個 IAM 角色，該角色將用於授予 Systems Manager 權限](#建立一個-iam-角色該角色將用於授予-systems-manager-權限)
    - [EC2 -> Actions -> Security -> Modify IAM role](#ec2---actions---security---modify-iam-role)
    - [Systems Manager -> Node Management -> Fleet Manager](#systems-manager---node-management---fleet-manager)
    - [為混合環境 (Linux) 安裝 SSM 代理](#為混合環境-linux-安裝-ssm-代理)
      - [打開高級實例層](#打開高級實例層)
  - [Pricing Calculator](#pricing-calculator)


-----

## IAM
return [Summary](#summary)

### Group
return [Summary](#summary)

參數
Name | Value
-|-
Group name|cfc104_project


![image20220317110912.png](fig/image20220317110912.png)

![image20220317111338.png](fig/image20220317111338.png)

![image20220317131848.png](fig/image20220317131848.png)

![image20220317132007.png](fig/image20220317132007.png)

![image20220317132037.png](fig/image20220317132037.png)

![image20220317132106.png](fig/image20220317132106.png)


-----

### User
return [Summary](#summary)

參數
Name | Value
-|-
User name|cfc104_02,cfc104_03,cfc104_06,cfc104_10

![image20220317132219.png](fig/image20220317132219.png)

![image20220317132306.png](fig/image20220317132306.png)

![image20220317132345.png](fig/image20220317132345.png)

![image20220317132442.png](fig/image20220317132442.png)

![image20220317132709.png](fig/image20220317132709.png)

![image20220317132730.png](fig/image20220317132730.png)

![image20220317132806.png](fig/image20220317132806.png)

![image20220317132857.png](fig/image20220317132857.png)

![image20220317133333.png](fig/image20220317133333.png)

-----
### User groups
return [Summary](#summary)

參數
Name | Value
-|-
Permission|AWSCodeCommitPowerUser, AWSCodeCommitFullAccess

![](fig/20220507133000.png)

![](fig/20220507133310.png)

![](fig/20220507141239.png)

-----
### Account Alias
return [Summary](#summary)

參數
Name | Value
-|-
Account Alias|cfc104-project01


![image20220317162909.png](fig/image20220317162909.png)

![image20220317163127.png](fig/image20220317163127.png)


-----



## CloudWatch
return [Summary](#summary)

使用 CloudWatch 代理從 Amazon EC2 實例和本地服務器收集指標和日誌
<https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/Install-CloudWatch-Agent.html>






### Billing Alarms
return [Summary](#summary)


#### 帳單超過 10 USD 通知
return [Summary](#summary)


![image20220317163239.png](fig/image20220317163239.png)

![image20220317163412.png](fig/image20220317163412.png)

![image20220317163441.png](fig/image20220317163441.png)

![image20220317163500.png](fig/image20220317163500.png)

![image20220317163839.png](fig/image20220317163839.png)

![image20220317163856.png](fig/image20220317163856.png)

![image20220317163922.png](fig/image20220317163922.png)

![image20220317164057.png](fig/image20220317164057.png)

![image20220317183612.png](fig/image20220317183612.png)

![image20220317183632.png](fig/image20220317183632.png)

![image20220317183723.png](fig/image20220317183723.png)

![image20220317183917.png](fig/image20220317183917.png)

![image20220317183945.png](fig/image20220317183945.png)

![image20220317184028.png](fig/image20220317184028.png)

![image20220317184102.png](fig/image20220317184102.png)

![image20220317184120.png](fig/image20220317184120.png)

![image20220317184141.png](fig/image20220317184141.png)



-----


### EC2 Alarms
return [Summary](#summary)

#### CPU利用率超過80%通知
return [Summary](#summary)

cfc104-project1-wordpress-ec2-public
cfc104-project1-wordpress-ec2-CPU-topic

![](fig/20220410095447.png)

![](fig/20220410095536.png)

![](fig/20220410095626.png)

![](fig/20220410095709.png)

![](fig/20220410110355.png)

![](fig/20220410110707.png)

![](fig/20220410110834.png)

![](fig/20220410112126.png)

![](fig/20220410113403.png)

![](fig/20220410112324.png)

![](fig/20220410113635.png)

![](fig/20220410113923.png)

![](fig/20220410114044.png)

![](fig/20220410114103.png)

![](fig/20220410114122.png)




-----


## EC2
return [Summary](#summary)

參數
Name | Value
-|-
EC2|cfc104-project1-wordpress-ec2-public
Amazon Machine Image (AMI)|Amazon Linux 2 AMI (HVM) - Kernel 5.10, SSD Volume Type
Instance Type|t2.micro
Network|cfc104-project1-wordpress-VPC
subnet|cfc104-project1-wordpress-subnet-public
Volume Type|General Purpose SSD (gp2)
Security Group|cfc104-project1-wordpress-sg-public


![](fig/image20220319082743.png)

![](fig/20220320151315.png)

![](fig/20220320151332.png)

![](fig/20220320151400.png)

![](fig/20220320151420.png)

![](fig/20220320151728.png)

![](fig/20220320151804.png)

![](fig/20220320151912.png)

![](fig/20220320152014.png)

![](fig/20220320152507.png)

![](fig/20220320152550.png)

![](fig/20220320152646.png)




-----

## ~~ECR~~
return [Summary](#summary)

![](fig/20220323090557.png)

![](fig/20220323194523.png)

![](fig/20220323194628.png)

![](fig/20220323194944.png)

![](fig/20220323195010.png)


-----

## RDS
return [Summary](#summary)

cfc104-project1-wordpress-rds


使用在 Amazon RDS 外部運行的 MariaDB 或 MySQL 實例進行複制
<https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/MySQL.Procedural.Importing.External.Repl.html>

![](fig/20220323200947.png)

![](fig/20220324135054.png)

![](fig/20220324135218.png)

![](fig/20220324140001.png)

![](fig/20220324140957.png)

![](fig/20220324141027.png)

![](fig/20220324141050.png)

![](fig/20220324141147.png)

![](fig/20220324141859.png)


-----

## VPC
return [Summary](#summary)

參考: [VPC的建立V2.pdf](VPC的建立V2.pdf)

![](fig/20220328210743.png)

![](fig/20220328211148.png)

![](fig/20220328212149.png)

![](fig/20220328212218.png)


### internet gateway
return [Summary](#summary)

![](fig/20220328212948.png)

![](fig/20220328213100.png)

![](fig/20220328213116.png)

### igw attach to VPC
return [Summary](#summary)

![](fig/20220328213446.png)

![](fig/20220328213527.png)

![](fig/20220328213706.png)

![](fig/20220328213733.png)


### subnet
return [Summary](#summary)

#### public subnet
return [Summary](#summary)

![](fig/20220329084540.png)

![](fig/20220329090351.png)

![](fig/20220329090650.png)


#### private subnet
return [Summary](#summary)

![](fig/20220329091120.png)

![](fig/20220329091046.png)

![](fig/20220329091359.png)


### ~~NAT gateway for private subnet~~
return [Summary](#summary)

![](fig/20220329093224.png)

![](fig/20220329093517.png)

![](fig/20220329093546.png)


### route table
return [Summary](#summary)

![](fig/20220329094129.png)

![](fig/20220329094826.png)

![](fig/20220329194656.png)

![](fig/20220329200008.png)

![](fig/20220329200035.png)

![](fig/20220329200831.png)

![](fig/20220329201009.png)

![](fig/20220329201150.png)

![](fig/20220329201330.png)

![](fig/20220329201420.png)

### route table for private subnet
return [Summary](#summary)

![](fig/20220329201751.png)

![](fig/20220329202031.png)

![](fig/20220329202052.png)

![](fig/20220329202209.png)

![](fig/20220329202301.png)

![](fig/20220329202340.png)



private route table 中增加 NAT gateway 的位置

![](fig/20220329203204.png)

![](fig/20220329203240.png)

![](fig/20220329204726.png)

![](fig/20220329204751.png)


### test ssh 172.16.0.10 -> 172.16.101.10
return [Summary](#summary)

![](fig/20220331091948.png)


-----

## godaddy DNS 管理
return [Summary](#summary)

![](fig/20220406090821.png)

-----

## Route53
return [Summary](#summary)

cfc104.project1.com

![](fig/20220407144505.png)

![](fig/20220407144555.png)

![](fig/20220407145144.png)

![](fig/20220407145220.png)

### Route53 private hosted zones add RDS
return [Summary](#summary)


RDS Endpoint
cfc104-project1-wordpress-rds.cn08hpayvo0z.us-east-1.rds.amazonaws.com

![](fig/20220407150138.png)

![](fig/20220407150621.png)

![](fig/20220407150653.png)

-----

## S3
return [Summary](#summary)


cfc104-project1-wordpress-s3

![](fig/20220409094354.png)

![](fig/20220409093024.png)

![](fig/20220409093809.png)

![](fig/20220409093833.png)

![](fig/20220409093849.png)

![](fig/20220409093933.png)


### Automatically uploads media to Amazon S3
return [Summary](#summary)

#### Properties -> Transfer acceleration -> Enabled
return [Summary](#summary)


![](fig/20220409095840.png)

![](fig/20220409100010.png)

![](fig/20220409100030.png)

![](fig/20220409100112.png)

![](fig/20220409100140.png)


#### Permissions -> CORS
return [Summary](#summary)

Getting Started with Amazon S3 and Media Cloud
<https://www.youtube.com/watch?v=kjFCACrPRtU>

如何在 Amazon S3 中設定 CORS 並使用 cURL 確認 CORS 規則？
<https://aws.amazon.com/tw/premiumsupport/knowledge-center/s3-configure-cors/>

```
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "GET",
            "PUT",
            "POST",
            "HEAD"
        ],
        "AllowedOrigins": [
            "*"
        ],
        "ExposeHeaders": [],
        "MaxAgeSeconds": 3000
    }
]
```

![](fig/20220409103603.png)

![](fig/20220409104344.png)

![](fig/20220409104425.png)

![](fig/20220409104446.png)

#### add media-cloud user
return [Summary](#summary)

cfc104-project1-wordpress-media-cloud


![](fig/20220409105658.png)

![](fig/20220409105732.png)

![](fig/20220409105927.png)

![](fig/20220409105959.png)

![](fig/20220409110109.png)

![](fig/20220409131726.png)

![](fig/20220409131800.png)

![](fig/20220409132002.png)

![](fig/20220409132534.png)

![](fig/20220409133203.png)

![](fig/20220409133227.png)


##### Create policy
return [Summary](#summary)


Sample IAM JSON Policy
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": [
                "s3:DeleteObjectTagging",
                "s3:ListBucketMultipartUploads",
                "s3:DeleteObjectVersion",
                "s3:ListBucket",
                "s3:DeleteObjectVersionTagging",
                "s3:GetBucketAcl",
                "s3:ListMultipartUploadParts",
                "s3:PutObject",
                "s3:GetObjectAcl",
                "s3:GetObject",
                "s3:AbortMultipartUpload",
                "s3:DeleteObject",
                "s3:GetBucketLocation",
                "s3:PutObjectAcl"
            ],
            "Resource": [
                "arn:aws:s3:::cfc104-project1-wordpress-s3/*",
                "arn:aws:s3:::cfc104-project1-wordpress-s3"
            ]
        },
        {
            "Effect": "Allow",
            "Action": "s3:HeadBucket",
            "Resource": "*"
        }
    ]
}
```

![](fig/20220409110227.png)

![](fig/20220409110735.png)

![](fig/20220409110858.png)

![](fig/20220409111109.png)

![](fig/20220409111134.png)





### S3使用前

![](fig/20220412125623.png)

### S3使用後

![](fig/20220413184022.png)








-----

## CloudTrail
return [Summary](#summary)


cfc104-project1-wordpress-CloudTrail

![](fig/20220410155050.png)

![](fig/20220410155255.png)

![](fig/20220410155745.png)

![](fig/20220410160036.png)

![](fig/20220410160129.png)

![](fig/20220410160148.png)

![](fig/20220410160219.png)


-----


## SSM
return [Summary](#summary)


AWS Systems Manager 節點管理
<https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-instances-and-nodes.html>


使用 AWS Systems Manager 在 EC2 執行個體上
<https://aws.amazon.com/tw/getting-started/hands-on/remotely-run-commands-ec2-instance-systems-manager/>




### 建立一個 IAM 角色，該角色將用於授予 Systems Manager 權限
return [Summary](#summary)


cfc104-project1-wordpress-SSM-Role

AmazonEC2RoleforSSM


![](fig/20220411184308.png)

![](fig/20220411184452.png)

![](fig/20220411184546.png)

![](fig/20220411184730.png)

![](fig/20220411184958.png)

![](fig/20220411185017.png)

![](fig/20220411185306.png)



### EC2 -> Actions -> Security -> Modify IAM role
return [Summary](#summary)


![](fig/20220411192355.png)

![](fig/20220411192601.png)

![](fig/20220412082525.png)



### Systems Manager -> Node Management -> Fleet Manager
return [Summary](#summary)


![](fig/20220412083902.png)

![](fig/20220412084217.png)

![](fig/20220412084603.png)

![](fig/20220412085301.png)


### 為混合環境 (Linux) 安裝 SSM 代理

https://docs.aws.amazon.com/systems-manager/latest/userguide/sysman-install-managed-linux.html



https://s3.ap-northeast-1.amazonaws.com/amazon-ssm-ap-northeast-1/latest/linux_amd64/amazon-ssm-agent.rpm



![](fig/20220419164202.png)

![](fig/20220419165238.png)

![](fig/20220419165339.png)

```
Activation Code   sU+5fsUX4W7cALtoAp13
Activation ID   4601fdcf-5568-4c28-8653-f7839f681323
Region   us-east-1
```


安裝 SSM 代理
Amazon Linux 2、RHEL 7.x、Oracle Linux 和 CentOS 7.x
```
mkdir /tmp/ssm
curl https://s3.amazonaws.com/ec2-downloads-windows/SSMAgent/latest/linux_amd64/amazon-ssm-agent.rpm -o /tmp/ssm/amazon-ssm-agent.rpm
sudo yum install -y /tmp/ssm/amazon-ssm-agent.rpm
sudo systemctl stop amazon-ssm-agent
sudo -E amazon-ssm-agent -register -code "sU+5fsUX4W7cALtoAp13" -id "4601fdcf-5568-4c28-8653-f7839f681323" -region "us-east-1"
sudo systemctl start amazon-ssm-agent
```

![](fig/20220419170913.png)


解決錯誤
![](fig/20220419160842.png)
```
sudo cp /etc/amazon/ssm/seelog.xml.template /etc/amazon/ssm/seelog.xml
sudo find / -name "seelog.xml.template"
ls /snap/amazon-ssm-agent/
ls /snap/amazon-ssm-agent/current/
sudo mkdir -p /etc/amazon/ssm/
sudo cp /snap/amazon-ssm-agent/current/seelog.xml.template /etc/amazon/ssm/seelog.xml

sudo /snap/amazon-ssm-agent/current/amazon-ssm-agent -register -code "GIpOr218Vx3v5G+3p6Rp" -id "164e0626-cb16-4918-aa50-947c80627e2a" -region "ap-northeast-1"


確認狀況
sudo systemctl start snap.amazon-ssm-agent.amazon-ssm-agent.service
sudo systemctl status snap.amazon-ssm-agent.amazon-ssm-agent.service
```


#### 打開高級實例層

![](fig/20220419173817.png)

![](fig/20220419174240.png)

![](fig/20220419184100.png)

![](fig/20220419184358.png)

![](fig/20220419184503.png)









## Pricing Calculator
return [Summary](#summary)

https://calculator.aws/#/estimate?id=2ccf19c71ca8cdd66a7154f3c96df1fa45153c76



![](fig/20220412211906.png)


![](fig/20220421083443.png)






