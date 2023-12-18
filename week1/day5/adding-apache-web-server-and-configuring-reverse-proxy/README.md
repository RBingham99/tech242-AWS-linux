## Adding apache webserver and configuring reverse proxy

A reverse proxy is basically a redirect so when someone visits your site on the standard port of 80 it redirects them to the port you want them to go to.

# Adding apache webserver
1) Update: `sudo apt update`
2) Install: `sudo apt install apache2`
3) Start: `sudo systemctl start apache2`
4) Enable: `sudo systemctl enable apache2`
5) Check status: `sudo systemctl status apache2`

# Configure reverse proxy
1) Ensure necessary modules are installed: `sudo a2enmod proxy` and `sudo a2enmod proxy_http` 
2) Open config file: `sudo nano /etc/apache2/sites-available/000-default.conf`
3) In config file just above `ErrorLog ${APACHE_LOG_DIR}/error.log` paste:
```
ServerName yourdomain.com

    ProxyPass / http://localhost:5000/
    ProxyPassReverse / http://localhost:5000/
```
But change `yourdomain.com` to your public IP and both `5000`'s to whatever port you want<br>
![apache-config-file](../../readme-images/apache-config-file.png)<br>
4) Restart apache with: `sudo systemctl restart apache2`

Your Reverse proxy is now set up, you can check by going to your IP and seeing if you are redirected.

# My script for deploying an app with apache set up is here:
[y script for deploying an app with apache](../script-to-deploy-app-with-apache/README.md)

# Note
When I automated this proccess I ran into an issue because I was re-writing the config file not just adding to it, this method does work but you have to make sure you dont remove anything important, so whent your type what you want to put in the file you need to include the important things that are already there.