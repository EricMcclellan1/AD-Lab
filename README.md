# Active Directory Corporate Simulation Using Oracle VirtualBox

<img width="801" alt="Screenshot 2023-12-22 at 11 33 09 PM" src="https://github.com/EricMcclellan1/AD-Lab/assets/147299619/d2b3b411-5a6f-43d2-ab21-7b1b3bc114af">


## Introduction/Summary

In this project, I built an Active Directory home lab utilizing Oracle Virtualbox to simulate a corporate environment with 1,000 users. The environment consisted of a Windows Server 2019 VM that acted as my ‘Domain Controller’, and a windows 10 Pro VM in place to act as a ‘client’ machine. To make the environment similar to a corporate structure, a custom Powershell script was used to populate Active Directory with 1,000 users, with each user given a unique name (first name and last) as well as a default password. The windows 10 Pro VM (our ‘client’ machine) was then configured and joined to the domain.

What followed next was using Active Directory to create group policies, security groups & organization unites. In closing, Active Directory was configured to act as a centralized management system for computers, users accounts, etc. 


## Technologies and Components Used:

-	Windows Server 2019
-	Windows 10 Pro
-	Oracle VirtualBox
-	Active Directory
-	Active Directory Domain Service
-	Network Address Translation (NAT)
-	Domain Name Service (DNS)
-	Dynamic Host Configuration Protocol (DHCP)
-	File and Storage Services
-	Internet Information Services (IIS)
-	PowerShell


## VirtualBox Set-up

I used VirtualBox to create both the DC “Domain Controller” and ‘Client’ machines (client machine created after setting up the Domain Controller completely and creation of 1,000 users).

![1 DC VM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/05ee237c-3f07-4c7b-a2ac-61a7e2cc1a10)

![2 CLIENT VM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/ee771bb1-0c2e-417d-8726-427fe1d26ec7)



## Windows Server 2019 and Active Directory Configuration

Two network adapters were used to separate internal and external traffic which were renamed to be easily identified with ‘_Internet_’ for external and ‘X_Internal_X’ for internal.

![3 network ](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/14fde5ab-94a8-40fb-9816-a399d908550b)

![Screenshot 2023-12-22 at 11 15 02 PM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/755917c5-e5b2-4293-88b4-ff2920a21b1a)

![Screenshot 2023-12-22 at 11 15 29 PM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/afd41583-cd29-4d9e-a721-f7bf9859f698)


In addition, these roles and services within Active Directory and the DC were configured

![Screenshot 2023-12-22 at 11 16 26 PM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/680e892c-bf21-4050-8f17-806c51ebd4cf)


A custom name list was used with 1,000 fake names saved to a text doc. and also my name at the top of the list to make it even more legit ;-)


![5 list](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/00b354c8-b15b-44f0-bebf-9749d7a1bd06)


A custom Powershell script was then executed inconjunction with the above name list to populate Active Directory, with the script parsing the names list & creating users by the first letter of the first name and the last name.

![6 powershell 1](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/a027ef81-82c5-429d-ac14-d35c7333fe42)

![6 powershell 2](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/7a926f67-b162-464c-90d2-139fe2879f39)

![7 powershell users](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/cc8bcfb8-a8a9-41ab-b7c1-d5824dc025c5)


![Screenshot 2023-12-22 at 11 20 55 PM](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/f522fb58-2229-4d71-a53d-233770b725c4)

## Joining Windows 10 Pro To The Domain Controller

As stated earlier, I used VirtualBox to also create the Windows 10 Pro environment to be a proxy for a ‘client’ computer in real-life. The network adapter was set to “internal network” to ensure traffic flowed only through the DC. To verify connection, I pinged the previously created DC, “mydomain.com” and got a positive read-back.

After this machine was joined with the DC, I then tried accessing it using credentials from 10 users that I previously generated, logging into the Windows 10 VM. Again, to act as if I was a client/user who just got access to the work network and logging in to my first day at work. Each one was able to login with success.

![10 my name](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/87b594fc-1834-456f-8af0-db364893e2c7)

![11 my name inside](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/99a766f7-f079-41b1-9271-9129461214ec)

![12 other user](https://github.com/EricMcclellan1/AD-Lab/assets/147299619/b40c7540-f563-447b-891e-75ba2860a175)

## Conclusion

In conclusion, this project allowed me to gain valuable knowledge in setting up proper configuration of Active Directory as well as getting more practical hands-on experience with using scripts and VirtualBox. Playing around with Active Directory I was able to learn more about the tool, more of its ins and outs on a technical level and giving me more of a wider knowledge base of it in a more real world corporate environment.








