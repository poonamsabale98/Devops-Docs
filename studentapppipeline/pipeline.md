###DEPLOYED STUDENTAPP USING JENKINS PIPELINE


STEP 1 : CREATE 2 INSTANCE ON UBUNTU

1ST INST. jenkins ,security gr. 8080

2nd INST. webserver ......t2 medium & same keypair

STEP 2 : CONNECT INSTANCES ONE BY ONE

1ST connect,then install jenkin
    
  '''
  sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2023.key
  echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  sudo apt-get update
  sudo apt-get install jenkins
  '''