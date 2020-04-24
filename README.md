# aws-networking

aws cli command to create a subnet

### check if the command execute successfully with --dry-run flag without creating subnet
aws ec2 create-subnet --dry-run --vpc-id vpc-0187f61 --cidr-block 192.168.2.0/23 --availability-zone us-east-2a      --profile startup

### create new subnet
aws ec2 create-subnet  --vpc-id vpc-01871361 --cidr-block 192.168.2.0/23 --availability-zone us-east-2a --profile startup

### specify a tag Name 
aws ec2 create-tags --resources subnet-063e6da9e --tags Key=Name,Value=demo-priv-a --profile startup

### create new route table
aws ec2 create-route-table --vpc-id vpc-0187ff01361 --profile startup

### associate route table with private subnet
aws ec2 associate-route-table --route-table-id rtb-0351af279f60  --subnet-id subnet-063e6dbccda9e --profile startup

### specify a tag Name 
aws ec2 create-tags --resources rtb-035af29f60 --tags Key=Name,Value=demo-priv-rt --profile startup

### creating an internet gateway attaching it to a VPC, and creating a route
aws ec2 create-internet-gateway --profile startup
aws ec2 create-tags --resources igw-03b1ccb --tags Key=Name,Value=demo-igw --profile startup
aws ec2 attach-internet-gateway --internet-gateway-id igw-031741b --vpc-id   vpc-018c1 --profile startup
aws ec2 create-route --route-table-id rtb-022ea72cf154 --destination-cidr-block 0.0.0.0/0 --gateway-id igw-03522117cb --profile startup


