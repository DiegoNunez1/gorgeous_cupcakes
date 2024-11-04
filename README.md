How to implement this application:

1. Go to AWS
2. Find the option called "CloudFormation"
3. On the Right hand side of the site. There will be an option called "Create stack" > Click on "With new resources standard"
4. In create Stack: We need to selected "Choose an existing Template" > "Upload a template file". Then one by one We upload in order
   VPC- RDS- EC2- ELASTIC IP.
5. After the templates has been created succesfully. We go to EC2 IN AWS and We connect to the EC2 that we created in CloudFormation.
6. We need to run the follow comannd one by one.
a. sudo su.
b. sudo dnf update -y.
c. sudo dnf install -y httpd wget php-fpm php-mysqli php-json php php-devel.
d. sudo dnf install -y mariadb105-server.
e. systemctl enable httpd.
f. systemctl start httpd.
h. sudo systemctl start mariadb.
i. cd /var/www/html.
j. mkdir dn.
k. wget https://github.com/DiegoNunez1/gorgeous_cupcakes/archive/refs/heads/main.zip
l. unzip main.zip
m. cd gorgeous_cupcakes-main
n. unzip gorgeous_cupcakes-main
o. cd gorgeous_cupcakes-main mysql --password=Password123 --user=admin --host=mysqldb.cncwqlzj2ooh.us-east-1.rds.amazonaws.com



7. In this step is for creating a database and changing the directory. Run the following commnads: 
a. Show databases. 
b. create diego
c. use diego.

8. This step is for installing sql into my SQL connection. Run the following command:

a. cd /var/www/html/dn
b. cd /var/www/html/dn/gorgeous_cupcakes-main
c. source /var/www/html/dn/gorgeous_cupcakes-main/gorgeous_cupcakes-main/gorgeous_cupcakes_v1.sql


10. The following step is the find the model using the next command:
cd /var/www/html/dn/gorgeous_cupcakes-main/gorgeous_cupcakes-main/model

12. Direct to PHP database and run the following command to open the dtaabase:
sudo nano database.php




