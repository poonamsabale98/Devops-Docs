### DEPLOYED STUDENTAPP USING JENKINS PIPELINE


STEP 1 : CREATE 2 INSTANCE ON UBUNTU

1ST INST. jenkins ,security gr. 8080

2nd INST. webserver ......t2 medium & same keypair

STEP 2 : CONNECT INSTANCES ONE BY ONE

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

then, hit the IP   publicIP:8080

copy the below path & on terminal sudo cat /var/lib/jenkins/secrets/initialAdminPassword

```
/var/lib/jenkins/secrets/initialAdminPassword
```

then, the output keep in the jenkins password

click on the installed suggested plugins
click on skip and continued as admin
click on save and start
then click on start the jenkins.

click on Managed jenkins -> Nodes -> new node -> give the node name (EX. studentapp), click on permanent agent then create.

Remote Root Directory -> /home/ubuntu
Labels -> any name (EX.dummy)
Launch Method -> launch agent via SSH
Host -> 2nd inst. p

