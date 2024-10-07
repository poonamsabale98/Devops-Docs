## HOSTING CONTAINER ON ECS WITH EC2 FOR NGINX,TODO,STUDENT 


```
sudo -i
apt update
```

###STEP 1 : CREATE CLUSTER ON ECS

        
   -> give cluster name and select ec2 instance

   -> select c1.xlarge instance type

   -> set minimun desire capacity = 1 &     
      maximum desire capacity = 2

   -> set root EBS volume size = 40

   -> auto assign public IP = turn on

   ->   then create cluster.

###STEP 2 : CREATE A NEW TASK DEFINITION 


   ->  give appropriate task definition  family

   ->  select infrastruture  launch type as ec2

   ->  network mode = bridge

   ->  CPU = 2 vCPU &  MEMORY = 4 GB 

   ->  container name = give appropriate name

   ->  image URI = nginx:latest
                   poonam1006/todo:micro
                   poonam1006/student:micro 
                                  ________dockerhub image name

   ->   host port = 80 & container port = 80
                 ___both port 80 for nginx & todo ,8080 for student  

   ->     then create. 

###STEP 3 : CREATE SERVICE IN CREATED CLUSTER  


   ->   select launch type as ec2

   ->   select application type as task and select task definition family

   ->   create service.

###STEP 4 : GO TO EC2 DASHBOARD AND COPY  INSTANCE PUB. IP


   ->   open http port 80 for nginx
   ->   copy ec2 ip and get the default home page of nginx.


![alt text](<Screenshot (291).png>)
   
![alt text](<Screenshot (290).png>)

![alt text](<Screenshot (292).png>)
