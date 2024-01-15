## Script to change the picture on the frontpage of the jsonvoorhees app to a scary cat

# Script to use if bucket already exists and has ACLs allowed

```
#!/bin/bash

echo "Downloading picture..."
wget https://i.pinimg.com/736x/42/86/02/428602bfb52e50ceed87073ccfa1138e.jpg
echo "Done!"
echo ""

echo "Renaming picture..."
mv 428602bfb52e50ceed87073ccfa1138e.jpg scary-cat.jpg
echo "Done!"
echo ""

echo "Uploading picture to s3 storage..."
aws s3 cp scary-cat.jpg s3://tech242-richard-jsonvoorhees-bucket
echo "Done!"
echo ""

echo "Deleting picture from virtual machine..."
rm scary-cat.jpg
echo "Done!"
echo ""

echo "Making picture in s3 storage public..."
aws s3api put-object-acl --bucket tech242-richard-jsonvoorhees-bucket --key scary-cat.jpg --acl public-read
echo "Done!"
echo ""

echo "Editing html file..."
sudo sed -i 's|<img src="/images/friday13th.jpg" alt="friday13thposter">|<img src="https://tech242-richard-jsonvoorhees-bucket.s3.eu-west-1.amazonaws.com/scary-cat.jpg" alt="friday13thposter">|g' /repo/springapi/src/main/resources/templates/home.html
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

```

## Script to create the bucket first
```
#!/bin/bash

echo "Creating bucket..."
aws s3 mb s3://tech242-richard-jsonvoorhees-bucket
echo "Done!"
echo ""

echo "Downloading picture..."
wget https://i.pinimg.com/736x/42/86/02/428602bfb52e50ceed87073ccfa1138e.jpg
echo "Done!"
echo ""

echo "Renaming picture..."
mv 428602bfb52e50ceed87073ccfa1138e.jpg scary-cat.jpg
echo "Done!"
echo ""

echo "Uploading picture to s3 storage..."
aws s3 cp scary-cat.jpg s3://tech242-richard-jsonvoorhees-bucket
echo "Done!"
echo ""

echo "Deleting picture from virtual machine..."
rm scary-cat.jpg
echo "Done!"
echo ""

echo "Allowing public access to bucket..."
aws s3api put-public-access-block --bucket tech242-richard-jsonvoorhees-bucket --public-access-block-configuration BlockPublicAcls=false,IgnorePublicAcls=false,BlockPublicPolicy=false,RestrictPublicBuckets=false
echo "Done!"
echo ""

echo "Editing bucket ownership settings..."
aws s3api put-bucket-ownership-controls \
 --bucket tech242-richard-jsonvoorhees-bucket \
 --ownership-controls '{
    "Rules": [
        {
            "ObjectOwnership":"BucketOwnerPreferred"
        }
    ]
 }'
echo "Done!"
echo ""

echo "Making picture in s3 storage public..."
aws s3api put-object-acl --bucket tech242-richard-jsonvoorhees-bucket --key scary-cat.jpg --acl public-read
echo "Done!"
echo ""

echo "Editing html file..."
sudo sed -i 's|<img src="/images/friday13th.jpg" alt="friday13thposter">|<img src="https://tech242-richard-jsonvoorhees-bucket.s3.eu-west-1.amazonaws.com/scary-cat.jpg" alt="friday13thposter">|g' /repo/springapi/src/main/resources/templates/home.html
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
```