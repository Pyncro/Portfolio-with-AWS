# Portfolio-with-AWS


## Intro
Already own a domain name but dont have a place to host it? You can use AWS for free hosting.


What we'll be using:

<div align=center>
    <img width="100" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ubuntu/ubuntu-plain-wordmark.svg" />
    <img width="100" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-plain-wordmark.svg" />
    <img width="100" height="100" src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/namecom.jpeg" />
    <img width="100" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/filezilla/filezilla-plain-wordmark.svg" />
    <img width="100" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ssh/ssh-original-wordmark.svg" />
    <img width="100" height="100" src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/materialize.svg">

</div>


 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/schémaniv3.svg"/>
 
## Aws EC2 setup
EC2 > Instances > Launch instances 

 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/lancerinstance.png">

Choose Ubuntu 20.04 as it's the one that has the least issues with dependancies.

 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/choose%20operating%20system.png">
 
Proceed the steps as normal and choose the t2.micro on Step 2 (which is the free tier).
 
On step 6 open the port to anywhere to allow all entrance to the IP host.Afterwards on step 7 create/or choose a key pair for ubuntu and then launch the instance.


Left click on the instance and view what security group it's attached to. (ex:wizard-x)
 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/Modify%20security.png">
 
 
Security groups > wizard-x > edit inbound rules > add new rule > http > Anywhere > Save
 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/httpanywhere.png">
 
## Aws Route 53 setup

DNS MANAGEMENT

Create hosted zone 

Type the domain name you got chose from name.com (or whichever site).
Type:Public hosted zone


 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/register.png">
 
 For the type pick A and then copy and paste the ip addresse IPv4 of your EC4
 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/o.png">
 
Name: www
Typz: CNAME
Value: name of your website
 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/CNAME.png">
 
Take note of the nameservers of your AWS
 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/nameserveraws.png">
 
## Name.com

Go to the site that has your domain name and remove their default nameservers with the one of AWS
  <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/changenameserver.png">
  

## FTP - ssh
Everything is done now with AWS , now you can connect to your ubuntu server.To do this , look into your EC2's ip address additional information , it shows you how to connect to it via ssh. (ex: ssh -i "portfolio.pem" ubuntu@ec2-xx-xxx-xxx-xxx.eu-west-3.compute.amazonaws.com)

To connect to it via FTP , you must first give chmod 400 of the permission key
 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/chmod%20perms.png">
Afterwards you must integrate permissions key to your FTP.


## Ubuntu setup
```sudo apt get update && upgrade```

```sudo apt install apache2 php libapache2-mod-php mysql-server php-mysql```

```sudo systemctl apache2 status```

![image](https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/systemctl.png)


## Finalized result
the www directory is now created , download a template from materialize and then paste it in /var/www/html (note that there's an index.html by default and that it has to be removed.)

everytime you upload/update a file in this directory , perform a ```sudo systemctl apache2 restart```

 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/my%20site.png">

## Credits

This project was able to be completed thanks to @Tricknology https://www.youtube.com/@Tricknology
