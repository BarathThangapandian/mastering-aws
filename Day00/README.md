
![Portfolio_Thumbnail](https://github.com/saikiranpi/mastering-aws/assets/109568252/df715451-e120-4ebc-b7e0-d3eadcbbce72)



######### DONT FORGET TO CHANGE THE DOMAIN NAME WITH YOUR NAME #########

-    DEPLOY AN EC2 ISNTANCE IN AWS USE UBUNTU 20

-    sudo apt update && sudo apt install -y nginx

-    sudo apt update && sudo apt install certbot python3-certbot-nginx

-    sudo mkdir -p /var/www/barathdevops.shop/html

-    sudo chown -R $USER:$USER /var/www/barathdevops.shop/html

-    sudo chmod -R 755 /var/www/barathdevops.shop

-    nano /var/www/barathdevops.shop/html/index.html

<html>
    <head>
        <title>Welcome to barathdevops.shop!</title>
    </head>
    <body>
        <h1>Success! The barathdevops.shop server block is working!</h1>
    </body>
</html>


-    sudo nano /etc/nginx/sites-available/barathdevops.shop

server {
        listen 80;
        listen [::]:80;

        root /var/www/barathdevops.shop/html;
        index index.html index.htm index.nginx-debian.html;

        server_name barathdevops.shop www.barathdevops.shop;

        location / {
                try_files $uri $uri/ =404;
        }
}


-    sudo ln -s /etc/nginx/sites-available/barathdevops.shop /etc/nginx/sites-enabled/

-    sudo nginx -t

-    sudo systemctl restart nginx

sudo certbot certonly \
  --agree-tos \
  --email baraththangapandian27@gmail.com \
  --manual \
  --preferred-challenges=dns \
  -d *.barathdevops.shop \
  --server https://acme-v02.api.letsencrypt.org/directory
  
 
 
FOR HTTP TO HTTPS FORWARDING RUN THE BELOW COMMAND.
 
 certbot --nginx

cd /var/www/barathdevops.shop/html

sudo apt install git

git clone https://github.com/BarathThangapandian/Portfolio-raw-files.git
