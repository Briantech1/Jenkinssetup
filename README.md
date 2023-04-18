# Jenkinssetup
Setting up Jenkins CICD Pipeline with Linux AMI 2023.

Launch an EC2 instance with the 2023 Linux AMI. (should be default AMI)

Include a key pair of your choice. 

Under Network settings create a new Security group (leave the existing security group rule there because you will need to SSH into this server.) add a new Inbound Security group rule. (TCP, Port range: 8080 and source: 0.0.0.0/0)

leave everything else as default and Launch!

 Navigate back to your Ec2 dashboard find your "running Instances" and click on the instance you launched and click on Connect. 

 Under the SSH client option follow the listed Instructions and ssh into your instance. 

Once in your instance change from ec2user to Rootuser

[ec2-user]$ sudo su - 

Then run each command to run the jenkin repo and install java-11 and as well as the jenkins application on your instance. 

[root-user]$ sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
  
[root-user]$ sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key

 [root-user]$ yum install jenkins

 [root-user]$ sudo dnf install java-11-amazon-corretto -y

 After you have installed everything now it is time to boot up jenkins.

 run the follow command to check your jenkins status.

 [root-user]$ service jenkins status

 You will find that is inactive run the following command to activate your jenkins.

 [root-user]$ service jenkins start

 Congratulations. If done correctly jenkins would have started. To be sure run status command again.

 [root-user]$ service jenkins status

 Navigate back to your Ec2 dashboard find your "running Instances" and locate your Public IPv4 address. Copy and paste the IP into a new tab of your browser and include :8080 behind the IP. 
 
 For exp: Ip-address:8080

 Jenkins should now be prompting you to sign in. Run the following path to obtain jenkins password. 

 [root-user]$ cat /var/lib/jenkins/secrets/initialAdminPassword

 use the password generated to sign into Jenkins.

 You don't have to install packages at the moment just click the x at the top and continue. 

 Going forward remember how to access password and your username will be admin. 

 Start Jenkins.

