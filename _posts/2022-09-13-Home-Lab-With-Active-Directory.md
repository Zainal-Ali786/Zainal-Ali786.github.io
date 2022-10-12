---
published: false
---
## Setting Up a Virtual Home Lab running Active Directory (using Oracle VirtualBox)
In this lab we will set up a virtual home lab consisting of a domain controller, DHCP server, File Server and 2 clients.

### Download and Install Oracle VirtualBox
![VMware.png]({{site.baseurl}}/images/VMware.png)

### Create Virtual Machines(VM)
Here I created the domain controller, DHCP server, File Server, and the two clients. The clients are running Windows 10, the Servers are running Windows Server 2016 

![Screenshot 2022-09-13 201527.png]({{site.baseurl}}/images/Screenshot 2022-09-13 201527.png)





### ##I realized that I was overly ambitious on my PC's capabilities and decided on running just the Domain Controller, DHCP Server and one client.##


### Configured Domain Controller with Active Directory and made it the DC

![DC with AD and DNS]({{site.baseurl}}/images/DC%20with%20AD%20DS%20and%20DNS%20installed.png)


I also created a new admin user and added it to Domain, Enterprise, and Schema Admins, so I dont have to add them later.

### Configured DHCP Server

I Added the DHCP role to the server and created a new scope of addresses to use. The range of addresses that DHCP will use to give new clients that connect is 10.0.0.200 - 10.0.0.250.

![DHCP Configuration.png]({{site.baseurl}}/images/DHCP Configuration.png)

### Confirmed that the client was able to obtain an IP address from the DHCP Server and added it to the domain.


![Client Confirmation of IP address.png]({{site.baseurl}}/images/Client Confirmation of IP address.png)

### In order for the client to connect to the Internet, we have to set up RAS/NAT on the Domain Controller.

After configuring routing on the DC we are now able to access the Internet through the client.

![Client Connection to Internet.png]({{site.baseurl}}/_posts/Client Connection to Internet.png)
