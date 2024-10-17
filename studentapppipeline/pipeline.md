## DEPLOYED STUDENTAPP USING JENKINS PIPELINE


#### STEP 1 : CREATE 2 INSTANCE ON UBUNTU

1ST INST. jenkins ,security gr. 8080

2nd INST. webserver ......t2 medium & same keypair

#### STEP 2 : CONNECT INSTANCES ONE BY ONE

1ST connect,then install jenkin
    
  ```
  sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
  echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  sudo apt-get update
  sudo apt-get install jenkins
  ```

 installation of java dependancy :

  ```
  sudo apt update
  sudo apt install fontconfig openjdk-17-jre
  java -version
  ```
  ```
  sudo systemctl enable jenkins 
   ```

  ```
  sudo systemctl start jenkins
  ```

```
  sudo systemctl status jenkins
```

#### Step 3: hit the IP   publicIP:8080

copy the below path & on terminal sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```
/var/lib/jenkins/secrets/initialAdminPassword
```

#### Step 4:  the output keep in the jenkins password 

![alt text](<Screenshot (351).png>)

click on the installed suggested plugins 

click on skip and continued as admin 

click on save and start 

#### Step 5:  click on start the jenkins.

2nd INST. coonnect, install java 11 and maven

```
sudo apt update
```


```
sudo apt install openjdk-11-jre-headless -y
```
```
sudo apt install maven
```


click on Managed jenkins -> Nodes -> new node -> give the node name (EX. studentapp), click on permanent agent then create.

Remote Root Directory -> /home/ubuntu 

Labels -> any name (EX.dummy).......script label same 

Launch Method -> launch agent via SSH

Host -> 2nd inst. public IP

Credentials -> add - kind-> SSH username with private key 

![alt text](<Screenshot (352).png>)

ID -> 1 

username -> ubuntu

private key-> click enter directly then click on add then,paste the 2nd inst.private key. then ADD in credential select your username

Host key verification strategy -> Non verifying verification strategy
then save.



new items -> name (EX. pipeline) - select pipeline option ,then ok

In general -> pipeline (definition) -> Pipeline script

then, script paste

click on apply and save.

![alt text](<Screenshot (356)-2.png>)

click on build now

![alt text](<Screenshot (355)-1.png>)

then, hit  the  1st INST. ip:8080 -> then show tomcat page

1st INST. ip:8080/student -> then show the studentapp page.

![alt text](<Screenshot (353)-3.png>)

![alt text](<Screenshot (354)-1.png>)

DONE.
