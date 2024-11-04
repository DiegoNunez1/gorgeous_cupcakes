How to implement this application:

1. Go to AWS
2. Find the option called "CloudFormation"
3. On the Right hand side of the site. There will be an option called "Create stack" > Click on "With new resources standard"
4. In create Stack: We need to selected "Choose an existing Template" > "Upload a template file". Then one by one We upload in order
   VPC- RDS- EC2- ELASTIC IP.
5. After the templates has been created succesfully. We go to EC2 IN AWS and We connect to the EC2 that we created in CloudFormation.
6. We need to run the follow comannd one by one.
sudo su.
sudo dnf update -y.
sudo dnf install -y httpd wget php-fpm php-mysqli php-json php php-devel.
sudo dnf install -y mariadb105-server.
systemctl enable httpd.
systemctl start httpd.
sudo systemctl start mariadb.
cd /var/www/html.
mkdir dn.
wget 
