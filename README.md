##Setting up code-deploy agent on ec2 machine

Install ruby
```bash
sudo apt update
sudo apt install ruby wget -y
```

Download and install CodeDeploy agent
```bash
cd /tmp
wget https://aws-codedeploy-us-east-1.s3.us-east-1.amazonaws.com/latest/install
chmod +x ./install
sudo ./install auto
```

Start the service
```bash
sudo service codedeploy-agent start
sudo systemctl enable codedeploy-agent
```

Verify installation
```bash
sudo service codedeploy-agent status
```

#Attach ec2-codedeployrole to your instance
The code must container the permission of ec2, s3 and CodeDeploy access and restart your codedeploy-agent
