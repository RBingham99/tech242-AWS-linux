## Script to change the picture on the frontpage of the jsonvoorhees app to a scary cat
```
#!/bin/bash

wget https://i.pinimg.com/736x/42/86/02/428602bfb52e50ceed87073ccfa1138e.jpg

mv 428602bfb52e50ceed87073ccfa1138e.jpg scary-cat.jpg

aws s3 cp scary-cat.jpg s3://tech242-richard-first-bucket

aws s3api put-object-acl --bucket tech242-richard-first-bucket --key scary-cat.jpg --acl public-read

sudo sed -i 's|<img src="/images/friday13th.jpg" alt="friday13thposter">|<img src="https://tech242-richard-first-bucket.s3.eu-west-1.amazonaws.com/scary-cat.jpg" alt="friday13thposter">|g' /repo/springapi/src/main/resources/templates/home.html

sudo mvn package
```