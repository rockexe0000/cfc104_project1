







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


## Dockerfile





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
cd my_wordpress 
docker-compose up -d
```




-----
git clone https://github.com/rockexe0000/my_wordpress.git



### …or create a new repository on the command line
```
echo "# my_wordpress" >> README.md
git init
git add .
git commit -m "update"
git branch -M main
git remote add origin https://github.com/rockexe0000/my_wordpress.git
git push -u origin main
```


### …or push an existing repository from the command line
```
git remote add origin https://github.com/rockexe0000/my_wordpress.git
git branch -M main
git push -u origin main
```


3.91.203.122


-----






## note



EFS















































































refer:

WooCommerce 中文教學：安裝設定＋功能介紹（完整指南）
<https://frankknow.com/woocommerce-tutorial/>


WordPress 後台教學：給新手的操作教學（全指南）
<https://www.youtube.com/watch?v=oPk3jqZ7wkw>

WordPress 網頁設計教學：如何架設網站＋完整官網製作（不懂程式也做得到）
<https://www.youtube.com/watch?v=5aI53lSJLcQ>
