## Script to revert scary cat change 

```
#!/bin/bash

echo "Editing html file..."
sudo sed -i 's|<img src="https://tech242-richard-jsonvoorhees-bucket.s3.eu-west-1.amazonaws.com/scary-cat.jpg" alt="friday13thposter">|<img src="/images/friday13th.jpg" alt="friday13thposter">|g' /repo/springapi/src/main/resources/templates/home.html
echo "Done!"
echo ""

echo "Navigating into application..."
cd /repo/springapi
echo "Done!"
echo ""

echo "Recompiling application..."
sudo mvn package spring-boot:start
echo "Done!"
echo ""

echo "Emptying bucket..."
aws s3 rm s3://tech242-richard-jsonvoorhees-bucket --recursive
echo "Done!"
echo ""

echo "Deleting bucket..."
aws s3 rb s3://tech242-richard-jsonvoorhees-bucket
echo "Done!"
echo ""
```