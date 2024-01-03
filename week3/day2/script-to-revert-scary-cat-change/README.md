## Script to revert scary cat change 

```
#!/bin/bash

sudo sed -i 's|<img src="https://tech242-richard-jsonvoorhees-bucket.s3.eu-west-1.amazonaws.com/scary-cat.jpg" alt="friday13thposter">|<img src="/images/friday13th.jpg" alt="friday13thposter">|g' /repo/springapi/src/main/resources/templates/home.html

sudo mvn package

aws s3 rm s3://tech242-richard-jsonvoorhees-bucket --recursive

aws s3 rb s3://tech242-richard-jsonvoorhees-bucket
```