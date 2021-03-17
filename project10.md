# Install Nginx Load Balancer
* Install Nginx and configure  
   $ sudo apt update  
   $ sudo apt install nginx  
\# open TCP port 80 and TCP port 443  
![](/image1.png)  
\# configure webservers IP address to domain name mapping  
![](/image2.png)  
\# Configure Nginx LB using Web Servers’ names defined in /etc/hosts  
$ sudo nano /etc/nginx/nginx.conf  
![](/image3.png)  
\# Restart Nginx and make sure the service is up and running  
$ sudo systemctl restart nginx  
![](/image4.png)  
