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
*  Register a new domain name and configure secured connection using SSL/TLS certificates  
1. Register a new domain name with a domain name registrar \(freenom.com) in any domain zone  
![](/image7.png)  
1. Assign an Elastic IP to Nginx LB server and associate new domain name with this Elastic IP  
\# Create an elastic IP  
![](/image5.png)  
\# Assign elastic IP to nginx EC2 server  
![](/image6.png)  
\# Register a domain name on a registra  
![](/image7.png)  
\# Associate domain name with elastic IP  
![](image8.png)  
review and update details  
![](/image9.png)  
\# Check webserver on browser using domain name in http protocol  
http://joecrypt.tk  
![](/image10.png)  
1. Configure nginx to recognise domain name  
Update nginx.conf file  
![](/image11.png)  
1. Install certbot and request for an SSL/TLS certificate  
\# Make sure snapd service is active and running  
$   sudo systemctl status snapd
![](/image12.png)  
\# Install certbot  
$ sudo snap install --classic certbot  
![](/image13.png)  
\# request certificate  
$ sudo ln -s /snap/bin/certbot /usr/bin/certbot  
$ sudo certbot --nginx  
![](/image14.png)  
\# test on browser  
![](/image15.png)  
![](/image16.png)
1. Set up periodical renewal of your SSL/TLS certificate  
\# testing renewal command in dry-run mode  
$ sudo certbot renew --dry-run  
![](/image17.png)  
\#  configure a cronjob to run the command twice a day  
$ crontab -e  
![](/image19.png)  