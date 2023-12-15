#!bin/bash

# update & upgrade
echo "Update..."
sudo apt update -y
echo "Done!"
echo ""
echo "Upgrade..."
sudo DEBIAN_FRONTEND==noninteractive apt upgrade -y
echo "Done!"
echo ""

# install maven
echo "Install maven..."
sudo DEBIAN_FRONTEND==noninteractive apt install maven -y
echo "Done!"
echo ""

# check maven is installed
echo "Check maven is installed..."
mvn -version
echo "Done!"
echo ""

# install JDK (java) 17
echo "Install java..."
sudo DEBIAN_FRONTEND==noninteractive apt install openjdk-17-jdk -y
echo "Done!"
echo ""

# check JDK is installed
echo "Check java is installed..."
java -version
echo "Done!"
echo ""

# Install apache
echo "Install apache..."
sudo DEBIAN_FRONTEND==noninteractive apt install apache2 -y
echo "Done!"
echo ""

# Start apache
echo "Starting apache..."
sudo systemctl start apache2
echo "Done!"
echo ""

# Enable apache
echo "Enabling Apache..."
sudo systemctl enable apache2
echo "Done!"
echo ""

# Check Apache
echo "Check apache is installed..."
sudo systemctl status apache2
echo "Done!"
echo ""

# Install apache modules
echo "Installing apache modules..."
sudo a2enmod proxy
sudo a2enmod proxy_http
echo "Done!"
echo ""

# Open and edit config file
echo "Editing apache config..."
VHOST_CONF="/etc/apache2/sites-available/000-default.conf"
DOMAIN_OR_IP="34.244.227.143"
cat <<EOF | sudo tee "$VHOST_CONF" > /dev/null
<VirtualHost *:80>
    ServerName $

    ProxyPass / http://localhost:5000/
    ProxyPassReverse / http://localhost:5000/

</VirtualHost>
EOF
echo "Done!"
echo ""

# Restart apache
echo "Restarting apache..."
sudo systemctl restart apache2
echo "Done!"
echo ""

# copy the app code to this vm
echo "Clone app from github..."
sudo git clone https://github.com/RBingham99/tech242-jsonvoorhees-app.git repo
echo "Done!"
echo ""

# cd into the right folder
echo "navigating into repo..."
cd /repo/springapi
echo "Done!"
echo ""

# Run the app
echo "Stopping application if running..."
mvn spring-boot:stop
echo "Done!"
echo ""
echo "Run application..."
mvn spring-boot:start
echo "Done!"
echo ""