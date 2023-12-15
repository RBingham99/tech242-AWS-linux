#!/bin/bash

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
# copy the app code to this vm
echo "Clone app from github..."
sudo git clone https://github.com/RBingham99/tech242-jsonvoorhees-app.git repo
echo "Done!"
echo ""
# cd into the right folder
cd /repo/springapi
# Run the app
echo "Stopping application if running..."
mvn spring-boot:stop
echo "Done!"
echo ""
echo "Run application..."
mvn spring-boot:start
echo "Done!"
echo ""
