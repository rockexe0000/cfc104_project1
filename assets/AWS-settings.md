




## Summary
return [Summary](#summary)

- [Summary](#summary)
- [IAM](#iam)
  - [Group](#group)
  - [User](#user)
  - [Account Alias](#account-alias)
  - [Billing Alarms](#billing-alarms)
- [EC2](#ec2)
- [ECR](#ecr)
- [RDS](#rds)
- [VPC](#vpc)
  - [internet gateway](#internet-gateway)
  - [igw attach to VPC](#igw-attach-to-vpc)
  - [subnet](#subnet)
    - [public subnet](#public-subnet)
    - [private subnet](#private-subnet)
  - [NAT gateway for private subnet](#nat-gateway-for-private-subnet)
  - [route table](#route-table)
  - [route table for private subnet](#route-table-for-private-subnet)
  - [test ssh 172.16.0.10 ->172.16.101.10](#test-ssh-17216010--1721610110)
- [godaddy DNS 管理](#godaddy-dns-管理)




## IAM
return [Summary](#summary)

### Group
return [Summary](#summary)

![image20220317110912.png](./fig/image20220317110912.png)

![image20220317111338.png](./fig/image20220317111338.png)

![image20220317131848.png](./fig/image20220317131848.png)

![image20220317132007.png](./fig/image20220317132007.png)

![image20220317132037.png](./fig/image20220317132037.png)

![image20220317132106.png](./fig/image20220317132106.png)


-----

### User
return [Summary](#summary)

![image20220317132219.png](./fig/image20220317132219.png)

![image20220317132306.png](./fig/image20220317132306.png)

![image20220317132345.png](./fig/image20220317132345.png)

![image20220317132442.png](./fig/image20220317132442.png)

![image20220317132709.png](./fig/image20220317132709.png)

![image20220317132730.png](./fig/image20220317132730.png)

![image20220317132806.png](./fig/image20220317132806.png)

![image20220317132857.png](./fig/image20220317132857.png)

![image20220317133333.png](./fig/image20220317133333.png)

-----
### Account Alias
return [Summary](#summary)

cfc104-project01


![image20220317162909.png](./fig/image20220317162909.png)

![image20220317163127.png](./fig/image20220317163127.png)


-----

### Billing Alarms
return [Summary](#summary)

![image20220317163239.png](./fig/image20220317163239.png)

![image20220317163412.png](./fig/image20220317163412.png)

![image20220317163441.png](./fig/image20220317163441.png)

![image20220317163500.png](./fig/image20220317163500.png)

![image20220317163839.png](./fig/image20220317163839.png)

![image20220317163856.png](./fig/image20220317163856.png)

![image20220317163922.png](./fig/image20220317163922.png)

![image20220317164057.png](./fig/image20220317164057.png)

![image20220317183612.png](./fig/image20220317183612.png)

![image20220317183632.png](./fig/image20220317183632.png)

![image20220317183723.png](./fig/image20220317183723.png)

![image20220317183917.png](./fig/image20220317183917.png)

![image20220317183945.png](./fig/image20220317183945.png)

![image20220317184028.png](./fig/image20220317184028.png)

![image20220317184102.png](./fig/image20220317184102.png)

![image20220317184120.png](./fig/image20220317184120.png)

![image20220317184141.png](./fig/image20220317184141.png)


-----


## EC2
return [Summary](#summary)

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

## ECR
return [Summary](#summary)

![](fig/20220323090557.png)

![](fig/20220323194523.png)

![](fig/20220323194628.png)

![](fig/20220323194944.png)

![](fig/20220323195010.png)


-----

## RDS
return [Summary](#summary)

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


### NAT gateway for private subnet
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


### test ssh 172.16.0.10 ->172.16.101.10
return [Summary](#summary)

![](fig/20220331091948.png)




## godaddy DNS 管理
return [Summary](#summary)

![](fig/20220406090821.png)





































































































































