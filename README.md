**Step-by-Step Guide to Deploying Your Application on AWS**
1. Set Up Infrastructure with AWS CloudFormation
Log in to AWS and go to CloudFormation.
Click Create stack > With new resources (standard).
Upload Templates in Order:
Choose Upload a template file and upload the following templates one at a time in this order: VPC, RDS, EC2, and Elastic IP.
Create the Stack by clicking Next and following the prompts until the stack is created.
**2. Connect to EC2 Instance**
After the stack is successfully created, go to the EC2 Dashboard.
Select the EC2 instance created by CloudFormation and connect to it using SSH.
**3. Configure the Server Environment**
Run these commands in the EC2 instance terminal one by one:
sudo su
sudo dnf update -y
sudo dnf install -y httpd wget php-fpm php-mysqli php-json php php-devel
sudo dnf install -y mariadb105-server

# Enable and start Apache (HTTP server)
systemctl enable httpd
systemctl start httpd

# Start MariaDB server
sudo systemctl start mariadb
**4. Download and Set Up Application Files**
Navigate to the web directory:

cd /var/www/html
Create a directory for the app:
mkdir dn
wget https://github.com/DiegoNunez1/gorgeous_cupcakes/archive/refs/heads/main.zip
unzip main.zip
cd gorgeous_cupcakes-main
**5. Configure the Database**
Connect to the MySQL database:

mysql --password=Password123 --user=admin --host=mysqldb.cncwqlzj2ooh.us-east-1.rds.amazonaws.com
**Set up the database:**
SHOW DATABASES;
CREATE DATABASE diego;
USE diego;
**6. Import SQL Data**
Navigate to the SQL file location:

cd /var/www/html/dn/gorgeous_cupcakes-main
Import the SQL file:
source gorgeous_cupcakes_v1.sql

**7. Configure Database Connection in PHP**
Navigate to the model directory:

cd model
Open the PHP database configuration file:
sudo nano database.php
Update the host, username, and password with your RDS endpoint and credentials from cf_rds.yaml.
Save the changes by pressing CTRL + X, then Y, and ENTER.
**8. Access the Application**
Go to the EC2 Dashboard on AWS.
Copy the public IPv4 address of the EC2 instance.
Paste the IP address in your browser to access the deployed website.
Application should now be live and accessible!




