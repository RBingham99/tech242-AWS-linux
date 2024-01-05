## Auto scaling groups

# How auto scaling groups work
![AWS autoscaling group diagram](../../../readme-images/AWS-autoscaling-group.jpg)

# How to create an auto scaling group
1) You will first need a working and tested VM, to do this you can follow the steps here: [Setting up a vm](../../../week1/day2/setting-up-a-vm/README.md)
2) You will then need to make an AMI from that VM, to do this you can follow the steps here: [Creating AMI's](../../../week1/day5/creating-ami's/README.md)
3) You Then need to make a launch template. 
   1) To do this simply navigate to the "Launch templates" section in the AWS console, and click on "Create launch template"
   2) Give your launch template a name, select the AMI you wish to use, the instance type, the key pair, a security group and enter any user data you need to run the app.
   3) Then click "Create launch template"
4) Now test the launch template by:
   1) Going to the launch templates details
   2) Click on actions
   3) click on launch instance from template
   4) Check all the details are correct 
   5) click launch instance
   6) Go to the new instances public IP and seeing if it is working
   7) If it works you can terminate that instance
5) Now make your auto scaling group by:
   1) Go to the "Auto scaling groups section of the AWS console
   2) click create auto scaling group
   3) Give your auto scaling group a name and select the launch template we just made and click next
   4) Select the availability zones you want your VM's to be created in and click next
   5) click attach to a new load balancer
   6) select the type of load balancer (we used Application load balancer)
   7) give your new load balancer a name
   8) select a load balancer scheme
   9) select create new target group from the default routing dropdown
   10) name your new target group
   11) click the checkbox for turn on Elastic Load Balancing health checks and click next
   12) select your desired, min and max capacitys, we chose 2, 2 and 3
   13) select Target tracking scaling policy
   14) select a Instance maintenance policy and click next
   15) Set up notifications if you want to (we didn't) and click next
   16) Add a name tag and click next
   17) Check all the settings and click create
6)  Now test your auto scaling group by:
    1) going to your loadbalancer and copying the DNS name and pasting it into your search bar (it may take a minute to load)

# Deleting auto scaling groups
To delete auto scaling groups:
1) delete the load balancer
2) delete the target group
3) delete the auto scaling group
4) (optional) delete the launch template