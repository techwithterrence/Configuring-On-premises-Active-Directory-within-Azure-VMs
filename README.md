# Configuring-On-premises-Active-Directory-within-Azure-VMs

![ws-2016-ad-ds-console-active-directory-users-and-computers](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/24855568-ee52-49fc-a82b-569f5f93d26e)

<h1>Project Scope - Using Active Directory w/Azure</h1>
This tutorial outlines the way a computer user can utilize Active Directory inside of the 
Microsoft Azure cloud enviornment.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: Watch Professor Messer's Active Directory Overview ](https://youtu.be/VLWt0-8BOV4?si=cbRf0qVTuvaHEolI)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Active Directory Users and Computers

<h2>Operating Systems Used </h2>

- Domain Controller - Windows Server 2022  </b> (21H2)
- Client-1 - Windows 10 

<h2>Lets Begin </h2>

<p>
    To begin the tutorial, it's a good idea to set up 2 virtual machines in Azure.  Its important to name these two virtual machines DC-1(Domain Controller) and name the other Client-1.  Client 1 vm needs to be on the same virtual network as DC-1 machine.
</p>
<br />

![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/71ec7bc6-2053-496f-a976-887fab93236d)


                                          </h1> *Note - Be sure to set Client-1 Vm to DC-1 Virtual Network. </h1> 

                                                
![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/4ce8d167-f80e-490f-a2cd-ce785b1b6ee8)
![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/cda88a10-1c3c-46d3-9e90-2cc29ffe17d8)


<p>
    Now log into Client-1 Virtual Machine to test connectivity to the Domain Controller DC-1.  To do this, simply remote desktop into Client-1 and ping the domain 
  controller from the command prompt using ping command.  After running the command the DC controller times out.  Therefore you will need to change the firewall ICMP settings in Domain controller to allow ICMP traffic through the firewall.
</p>
<br />


![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/17624636-a5c4-4664-b3d8-2640be9f93b9)
![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/b0634dc9-9ed6-4834-9b9d-f24b5518f745)


                                    AFTER FIREWALL SETTINGS CHANGED ON DC-1, PING IS WORKING NOW



![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/b3c34825-c014-43e3-9017-62c02e336d5d)

</p>
                               

</p>
<p>
     Next Install and configure Active Directory.  To Install Active Directory, you must use the server workstation's Server Manager, Add Roles And Features option.
</p>
<br />

![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/f51ec641-d362-4e39-92c6-a1db70790e25)
![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/67536173-9bdd-494f-ab44-88e6d8ed381c)

                                 BE SURE TO CLICK THE YELLOW EXCLAMATION POINT!!!!  Then Promote the server to the controller.
![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/31b2f812-b5a6-4f04-9712-ad13f5abe574)

                                Now CONFIGURE THE DOMAIN CONTROLLER HERE!!!!

![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/add61772-90c5-4e37-b3c4-febbef1c60ad)
![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/7f595948-ca3e-4dea-95a2-7dbff84c6f30)



</p>
<p>
        Now, Next log back into the DC-1 workstation with the newly created Domain controller information you just created before the system restarted.
    Also look and find Active Directory Users And Computers is now in the tools menu of the Server Manager's Menu.  
</p>
<br />


![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/51e04238-14e4-4de4-a65b-b09680795858)

                                                        READY TO BE USED NOW!!!
![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/151f95af-7b72-4e84-91fd-08de256d2924)


</p>
<p>
    Now, Lets create our first group of folders in Active Directory.
</p>
<br />


![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/92a616d1-8227-4b12-9663-2e905e602871)
![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/4c6051b1-441d-43ae-b201-b77111e3fed5)


                                                            NOW LETS ADD A NEW USER TO THE GROUP

                                                            

![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/e79db857-5c6d-465b-abcc-d5e54752effa)

![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/0411b6ea-ede8-4def-9d7e-e5da8dfc1fac)

![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/086b8560-f4ef-4b73-a193-9fd86a8a4c44)



                                                 ALL DONE, HERE IS THE NEW USER NOW!!!!!!


![image](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/354add33-ad04-4d39-863f-fa8701165c01)






</p>
<p>
        All FINISHED I HOPE YOU ENJOYED THE LAB.  
</p>
<br />


![360_F_267282687_zFyIxL9ZUGrOss3OOgFzFIXWdHUeEsG3](https://github.com/techwithterrence/Configuring-On-premises-Active-Directory-within-Azure-VMs/assets/174138674/556faa08-ff85-4d2c-b328-a2c04dcbb3a0)
