# Jenkinssetup
Setting up Jenkins CICD Pipeline with Linux AMI 2023.

Launch an EC2 instance with the 2023 Linux AMI. (should be default AMI)

Include a key pair of your choice. 

Under Network settings create a new Security group (leave the existing security group rule there because you will need to SSH into this server.) add a new Inbound Security group rule. (TCP, Port range: 8080 and source: 0.0.0.0/0)()

leave everything else as default and Launch!

