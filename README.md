# deploySpringboot
Refer this youtube video link

https://www.youtube.com/playlist?list=PLSg8jHkYTg9FG9v5VEikhYwhT_9SdXHcU



# Create EC2 instance

1. Go to AWS Console
2. In the right corner select the region => Mumbai asia pacific
3. In the search, "EC2" => launch instances => Give name to vm 
4. Select Free AWS linux 
5. Amazon Machine Image (AMI) Free tire eligible
6. Create new key pair => this will generate "privatekey file" .pem file
7. Firewll general security group => new or existing
8. Configuration storage
9. Summary number of instances =>1
instance type t2.micro (free)

Finally created on launch instance


# Open port 8080

1. select EC2 instance => select security tab => select security group 
= > edit inbound rules => select Type => custom TCP => Port range "8080"  => Source => 0.0.0.0/0 => save rules


# Connect to Putty

# Download and install putty
Search "Puttygen" in windows search
start puttygen
Generate "ppk file" using ".pem" file generated from EC2 instance
click on save "private key" button

# Search putty in windows search
add host Name => EC2 instance => pubilc ip address => 13.232.254.239
Connection => SSH => Auth => Credentials => private key file => add ".ppk" file
open
Enter user name => ec2-user
hit cmd => ls -l

# To deploy the spring boot jar onto the AWS (Windows => AWS Ec instance) 
# We need to install WinSCP/ mobxyterm

File protocol => SFTP
Host name => 13.232.254.239
port no => 22
user name = > EC2 instance
password => ******

then Click on Adavance => SSH => Authentication => browse private key ok
Press "Login"

On the Left side "Local Folders" or the right side "/home/ec2-user"
Select jar from local that moved to "/home/ec2-user"

# Goto putty again

cmd => ls -l

Check jar file is displayed or not
Once jar file displayed

Run jar file => java -jar "jar-name"

Then => java not found

To install java => sudo yum install java
To check java version =>java -version

then execute => java -jar "jar-name" 


