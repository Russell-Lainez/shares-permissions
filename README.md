<p align="center">
    <img width="700" height="250" src="https://github.com/user-attachments/assets/9f0fd555-69c4-4c16-becf-5eb22f8e905e">
</p>

<h1> Network File Shares and Permissions for Client Computers</h1>
In this demonstration, I will walk you through how file shares work and how to update group permissions for these shares on client computers. I will also show how I used the C: drive to create different folders and share them with general groups.

<h2>Environments, Applications, and Services Used </h2>

- Microsoft Azure (Virtual Machines/Virtual Network)
- Remote Desktop
- Client Computer: Windows 10Pro (22H2)
- Domain Controller: Windows Server 2022 Datacenter
- Active Directory Users and Groups 
- PowerShell
  
![image](https://github.com/user-attachments/assets/199bc314-b926-49fa-b3d7-d24d02e765a7)

<h2>Walkthrough</h2>

<h3>File Sharing</h3>

1. While logged into the domain controller, I went to the c:/drive and created 4 folders:
   - read-access
   - write-access
   - no-access
   - accounting

![image](https://github.com/user-attachments/assets/a66abf92-8101-46c4-bbec-b2e39a452ff3)



2. For three of these folders, I changed the sharing permissions to include domain users or domain admins:
     - Read only access for the “read-access” folder
     - Read and write only access for the “write-access” folder
     - Read and write only access for the “no-access” folder
       
![image](https://github.com/user-attachments/assets/a1548ca4-cb67-4780-b774-7796e86ab94b)
![image](https://github.com/user-attachments/assets/eb8b0064-cb64-4b07-a2aa-8d7f08ec33a5)
![image](https://github.com/user-attachments/assets/9c35ea99-1295-4181-899a-34dd1e32d8df)




  
3. As a user logged into a client computer, I accessed each of the folders and verified I had the appropriate access.

![image](https://github.com/user-attachments/assets/36e2b1e9-852c-4999-a906-095ade766e94)
![image](https://github.com/user-attachments/assets/4a5b3e74-1614-42c9-a2b9-a973ee1e762f)
![image](https://github.com/user-attachments/assets/e46f8d99-25ab-4d90-8f11-34969c394c4f)
![image](https://github.com/user-attachments/assets/6d42c15f-44b3-4bf2-a5d7-f8743b172d26)



<h3>File Permissions</h3>
1. In Active Directory Users and Computers, I created a new security group called "Accountants" and added domain users to read and write within the "Accountants" folder.


![image](https://github.com/user-attachments/assets/49c83726-ddb0-446f-8da8-cd992e70bb1b)
![image](https://github.com/user-attachments/assets/c5d68a1a-6df1-4936-a513-116471b19668)



2. After logging back in with a few users, I verified I can add and read files.

![image](https://github.com/user-attachments/assets/160d3064-ac60-487a-ab7b-c376327aed58)










