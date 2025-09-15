# Jenkins Master-Slave Architecture Setup

## 📌 Objective
This project was created to learn and practice Jenkins by setting up a Master-Slave (Agent) Architecture for distributed build execution.


## ⚙️ Environment Details
- Operating System: Ubuntu (Master & Slave)
- Jenkins Version: 2.527
- Java Version: OpenJDK 21.0.8 (2025-07-15)

## 🛠️ Installation & Configuration Steps
1. Launch two EC2 instances (Master & Slave) in the same security group.
2. On the Jenkins Master server:
   - Install Jenkins
   - Install Java
3. On the Slave (Node) server:
   - Install Java
4. Access Jenkins in the browser and install the SSH Build Agent Plugin.
5. Create a new Node in Jenkins:
   - Provide the private IP of the slave as the host.
   - Add your SSH key as credentials.
6. On the slave server, verify that two files are created:
   - remoting
   - remoting.jar  
   Note: If these files are not created, node creation has failed.
7. Create a new Freestyle Project:
   - Enable "Restrict where this project can be run" and select the node label.
   - Add a Git repository link.
   - In the Execute Shell section, add:
     ```sh
     echo $name
     echo "build job is successful"
     ```
8. Build the project.
9. Verify that a workspace folder is created on the slave server.


## 🔗 Connection Method
- Master and Slave are connected using SSH.


## 🔌 Tools & Plugins Used
- Git  
- SSH Build Agent Plugin  


## ✅ Testing & Verification
- Presence of remoting and remoting.jar files on the slave server confirmed successful connection.
- Execution of build job validated proper functionality.


## 📄 Example Build Output
