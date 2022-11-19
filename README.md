# Portfolio-with-AWS


## Intro
Already own a domain name but dont wanna pay for the host? Use AWS for free hosting.

<div align="center">
  
 <img width="600" height="350" src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/machineversion.png">
  
</div>


What we'll be using:

<div align=center>
    <img width="100" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ubuntu/ubuntu-plain-wordmark.svg" />
    <img width="100" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/amazonwebservices/amazonwebservices-plain-wordmark.svg" />
    <img width="100" height="100" src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/namecom.jpeg" />
    <img width="100" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/filezilla/filezilla-plain-wordmark.svg" />
    <img width="100" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/ssh/ssh-original-wordmark.svg" />

</div>

## Aws EC2 setup
EC2 > Instances > Launch instances 

 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/lancerinstance.png">

Choose Ubuntu 20.04 as it's the one that has the least issues with dependancies.

 <img src="https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/choose%20operating%20system.png">
 
Proceed the steps as normal and choose the t2.micro on Step 2 (which is the free tier).
 
On step 6 open the port to anywhere to allow all entrance to the IP host.Afterwards on step 7 create/or choose a key pair for ubuntu and then launch the instance.
 
## Aws config
## Name.com
## FTP - ssh

# Finalized results
```sudo apt install apache2 php libapache2-mod-php mysql-server php-mysql```

```sudo systemctl apache2 status```

![image](https://github.com/Pyncro/Portfolio-with-AWS/blob/main/img/systemctl.png)
