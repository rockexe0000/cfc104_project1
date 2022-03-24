



## Summary
return [Summary](#summary)
- [Summary](#summary)
- [Docker image](#docker-image)
- [Git](#git)
  - [create a new repository on the command line](#create-a-new-repository-on-the-command-line)
  - [push an existing repository from the command line](#push-an-existing-repository-from-the-command-line)
- [Note](#note)



https://hub.docker.com/_/wordpress


https://qiita.com/vc7/items/e88026c75f2280f95ed4



建立並切換目錄
```
mkdir -p my_wordpress && cd my_wordpress
```

編輯 docker-compose.yml
```
vim docker-compose.yml
```

docker-compose.yml 內容
```
version: '3.8'

services:
  wordpress:
    image: wordpress:5.9.2
    restart: always
    container_name: wordpress-web
    ports:
      - 80:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: root
      WORDPRESS_DB_PASSWORD: 123456
      WORDPRESS_DB_NAME: exampledb
    volumes:
      - ./html:/var/www/html

  db:
    image: mysql:5.7
    restart: always
    container_name: mysql-db
    environment:
      MYSQL_DATABASE: exampledb
      MYSQL_USER: user
      MYSQL_PASSWORD: 123456
      MYSQL_ROOT_PASSWORD: 123456
    volumes:
      - ./db_data:/var/lib/mysql

  phpmyadmin:
    image: phpmyadmin
    restart: always
    container_name: phpmyadmin-db-console
    ports:
      - 8080:80
    environment:
      - PMA_ARBITRARY=1
```


執行 docker compose
```
docker-compose up -d
```


關閉 docker compose
```
docker-compose down
```


管理介面 URL
http://<CentOS的IP>/wp-admin/

呈現介面 URL
http://<CentOS的IP>



http://192.168.211.142/wp-admin/


## Docker image
return [Summary](#summary)




```
// 建立映像檔
docker build --rm -t my_wordpress .

// 映像檔建立 refernece
docker tag my_wordpress rockexe0000/my_wordpress

// 映像檔推送到 docker hub
docker image push rockexe0000/my_wordpress

docker run -itd my_wordpress


docker run 

```

ec2 User data
```
Content-Type: multipart/mixed; boundary="//"
MIME-Version: 1.0

--//
Content-Type: text/cloud-config; charset="us-ascii"
MIME-Version: 1.0
Content-Transfer-Encoding: 7bit
Content-Disposition: attachment; filename="cloud-config.txt"

#cloud-config
cloud_final_modules:
- [scripts-user, always]

--//
Content-Type: text/x-shellscript; charset="us-ascii"
MIME-Version: 1.0
Content-Transfer-Encoding: 7bit
Content-Disposition: attachment; filename="userdata.txt"

#!/bin/bash
yum update -y
amazon-linux-extras install -y docker
service docker start
usermod -a -G docker ec2-user

curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose

yum install git -y
git clone https://github.com/rockexe0000/my_wordpress
git pull
cd my_wordpress 
docker-compose pull
docker-compose up -d
```

如何使用 docker-compose 更新現有圖像？
<https://stackoverflow.com/questions/49316462/how-to-update-existing-images-with-docker-compose>

如何讓 EC2 用戶數據腳本在啟動時再次運行？
<https://serverfault.com/questions/797482/how-to-make-ec2-user-data-script-run-again-on-startup>


-----

## Git
return [Summary](#summary)

git clone https://github.com/rockexe0000/my_wordpress.git



### create a new repository on the command line
return [Summary](#summary)

```
echo "# my_wordpress" >> README.md
git init
git add .
git commit -m "update"
git branch -M main
git remote add origin https://github.com/rockexe0000/my_wordpress.git
git push -u origin main
```


### push an existing repository from the command line
return [Summary](#summary)

```
git remote add origin https://github.com/rockexe0000/my_wordpress.git
git branch -M main
git push -u origin main
```


3.91.203.122


-----






## Note
return [Summary](#summary)


EFS















































































Referance:

WooCommerce 中文教學：安裝設定＋功能介紹（完整指南）
<https://frankknow.com/woocommerce-tutorial/>


WordPress 後台教學：給新手的操作教學（全指南）
<https://www.youtube.com/watch?v=oPk3jqZ7wkw>

WordPress 網頁設計教學：如何架設網站＋完整官網製作（不懂程式也做得到）
<https://www.youtube.com/watch?v=5aI53lSJLcQ>
