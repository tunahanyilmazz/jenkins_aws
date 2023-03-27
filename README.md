# jenkins_aws
Part-1
create free aws account - 
create EC2 Red Hat Linux instance 

Create new key pair 

<img width="712" alt="image" src="https://user-images.githubusercontent.com/10364043/227903996-0de91137-814b-4f1a-9bca-6864f7d2e855.png">


Launch instance. 

Part-2 
Connection instance over SSH on your device.
-Open an SSH client.

-Locate your private key file. The key used to launch this instance is Ins1.pem (name what you create)

-Run this command, if necessary, to ensure your key is not publicly viewable.

 chmod 400 Ins1.pem
-ec2-16-16-70-236.eu-north-1.compute.amazonaws.com. 

example : 
 ssh -i "Ins1.pem" ec2-user@ec2-16-16-70-236.eu-north-1.compute.amazonaws.com
 
(16-16-70-236) is Public IPv4 address
You can find this 


<img width="595" alt="image" src="https://user-images.githubusercontent.com/10364043/227905371-8359c53a-925a-4318-91d4-f9489638ac8e.png">

You will see this output 

<img width="735" alt="image" src="https://user-images.githubusercontent.com/10364043/227909856-0b4f5117-ccc8-48fe-8ffa-f6a3c21f6587.png">


On terminal 

$ sudo su -
$ sudo yum install java-1.8.0-openjdk-devel
$ sudo yum install java-11-openjdk-devel

<img width="938" alt="image" src="https://user-images.githubusercontent.com/10364043/227918008-73f0d1d0-d038-4198-9ea7-d0e1a2c0d4ee.png">

$ ls -la
$ vi .bash_profile

insert 

JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-1.8.0.362.b09-2.el9_1.x86_64
PATH=$PATH:$JAVA_HOME:$HOME/bin
export PATH 

save and quit. 
logout 
login

$ echo $PATH 

<img width="865" alt="image" src="https://user-images.githubusercontent.com/10364043/227919689-c42c4333-3ce9-4619-8f08-141d39e39d4c.png">

Part-3
yum install wget -y
go to link https://pkg.jenkins.io/redhat-stable/

$ sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
$ sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
$ yum install fontconfig java-11-openjdk
$ yum install jenkins

Before start jenkins go to aws console 
edit inbounds and add custon TCP port 8080 


<img width="893" alt="image" src="https://user-images.githubusercontent.com/10364043/227921278-bdaa56c5-df25-4d56-8f31-1828a5ca518e.png">

$ service jenkins start 
 
<img width="1176" alt="image" src="https://user-images.githubusercontent.com/10364043/227921931-f35a1e09-d1e6-4f07-838d-b044ac339732.png">

cat /var/lib/jenkins/secrets/initialAdminPassword

Install plugins. 
Done. 

