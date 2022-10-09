#!/bin/bash
set -x
ips=$( aws ec2 describe-instances --region us-east-1 --query "Reservations[*].Instances[*].PublicIpAddress" --output=text)
get=$(echo "$ips" | awk 'FNR == 2')
echo "$get"
sudo scp  /var/lib/jenkins/workspace/copy2/file.sh ec2-user@$get:/home/
sudo ssh -i crazy.pem ec2-user@$get  "
set -x
./file.sh "
pwd
