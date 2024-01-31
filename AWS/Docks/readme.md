# Deploying a Simple Front-end Application **MyDocks** on AWS EC2

- [Project Link](#)
- [Documentation Link](https://aashishsec.github.io/CloudProjects/AWS/Docks/)
 
### This are the Docks that i use for reconnaissance.

### Set up an AWS EC2 instance

1. Create an IAM user & login to your AWS Console
    - Access Type - Password
    - Permissions - Admin
      
2. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro
      
3. Connecting to the instance using ssh
```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/7e9b1075-3a41-4897-926c-16e69ca2b2a1)

### Configuring Ubuntu on remote VM

1. Updating the outdated packages and dependencies
```
sudo apt update
```
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/59d42815-57f2-4031-8f8a-798114af1308)

2. Install Git - [Guide by DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-git-on-ubuntu-22-04)
   

### Deploying the project on AWS

1. Clone this project in the remote VM
   
```
 git clone https://github.com/aashishsec/docks.git
```
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/6164cd7a-e458-4215-82ce-c2f48a5d3fbb)

2. Check python is installed or not.
   ![image](https://github.com/aashishsec/CloudProjects/assets/65489287/f72e054d-9bd2-4a6a-8cc9-e94f309936bb)

3. Python is installed lets start a simple http server using python.
```
  python3 -m http.server 80
 ```
4. I did not navigated into the Docks folder. So I have to kill the process.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/06ca67a9-c363-4e9e-b5a1-438697acade6)
5. change to Docks
```
cd Docks
```
6. Start the python server
```
  python3 -m http.server 8000
 ```
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/81c33f28-211d-479b-aa2a-31a5047c09cf)
7. We have not allowed any inbound traffic so lets allow 8000 port.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/e3a5df55-8db6-4754-b9cb-0e788709d0b7)
8. Go to security and select inbound traffic.
9. Allow 8000 port to get requests from internet.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/a9caadf5-a162-43e7-8908-3cf85566826f)
10. Let's try again.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/bd2629c2-8618-4cf4-860c-0af0d7242205)
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/7dc6b238-bd57-4b4f-951c-cd3d8e84e6cf)
11. My Application was working properly.
![image](https://github.com/aashishsec/CloudProjects/assets/65489287/12fd25ec-2ed5-4cba-87f2-cf0326d88f9b)

- For this project, we'll have to set up an [Elastic IP Address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) for our EC2 & that would be our `DOMAIN`
   
### Project is deployed on AWS 🎉
