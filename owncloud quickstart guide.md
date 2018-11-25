# Quickstart Installation Guide for ownCloud 10.0




## Overview
ownCloud is an open-source software that allows you to run a personal cloud file storage service. The ownCloud server software can be installed free of charge on Linux like hosted systems, and the client software can be installed on computers running Windows, OS X, or Linux. Mobile apps are also available for Android and iOS devices.

## Purpose
The purpose of this Quickstart guide is to provide quick and easy instructions for the installation and configuration of an ownCloud server as well as user setup. The guide also covers user access via the ownCloud clients.

## Skill Level Requirement
Using this guide requires a minimum skill level as a Junior System Administrator to perform the installation procedures. The Junior System Administrator will need to have Linux experience and knowledge on how to open and modify files using a text editor similar to vi or vim.

## Supplied Information

### System Variables Required for Installation ###
                                         
![](https://i.imgur.com/TMi6V2y.jpg)
 

## Sequence
This Quickstart guide should be used after the following criteria has been met:

- The server hosting ownCloud meets the system requirements.

This Quickstart guide assumes that the Host OS and or the VM OS has been loaded on the target server.

The LAMP software stack has been built and tested (LAMP consists of the Linux, Apache, MySQL and PHP components of the software stack).

- The server hosting ownCloud has the operating system installed.
- Apache web server is installed and tested.
- The SQLite or MariaDB database has been setup and configured.
- All the required PHP librariess have been installed.
- The root usernames and passwords are set and available.

#####*Note: Use the link below to confirm the system requirements for the installation type being preformed.* 

Access to ownCloud System Requirements can be found at the following link:
[https://doc.owncloud.org/server/latest/admin_manual/installation/system_requirements.html](https://doc.owncloud.org/server/latest/admin_manual/installation/system_requirements.html "System Requirements")

Setting up Apache, SQLite/Mariadb and the required PHP libraries are outside the scope of this guide.

Use the following link to access the ownCloud Server Administration Manual for assistance with any of the above mentioned items.

[https://doc.owncloud.org/server/latest/admin_manual/installation/](https://doc.owncloud.org/server/latest/admin_manual/installation/ "Admin Install Guide")

## Software
The ownCloud server software can be downloaded from the following location:

[https://owncloud.org/download](https://owncloud.org/download "owncloud software download")

##### *Note: This Quickstart guide was created for workgroups and departments sized up to 150 users. This guide was validated using CentOS 7.2*

All information required should be collected prior to starting the installation and configuration. Ensure that all usernames, passwords, IP Addresses, and Hostname have been verified prior to starting the installation. Software update files or patches may have to be installed for the ownCloud server application, including CentOS Linux patches.

No other materials are required to perform this installation.

## Preparations
It is strongly recommended that this Quickstart guide be read in its entirety before starting the installation presented herein.

## Installation 
Use the link below to download the tarball file required to install the ownCloud server.

#####*Note: The installation via the ownCloud tarball is the most common option and is best for production environments.*

[https://owncloud.org/download/#owncloud-server-tar-ball](https://owncloud.org/download/#owncloud-server-tar-ball "Tarball Download")

Also, download either the md5 or sha256 to check the file integrity prior to installing the ownCloud software tarball file. Log in to the target server and run the file integrity check prior to starting the installation.

Once the tarball file has been checked use the following command to move it to the /var/www/html/ directory.

- ***Example Input:*** mv owncloud-10.0.10.tar.bz2 /var/www/html/

Enter the following command to untar the file and install the ownCloud server installation packages.

- ***Example Input:*** tar -xvf owncloud-10.0.10.tar.bz2

The tarball will unpackage the files and set them in the proper directories.The file setup takes a few moments to complete. 

## Launch the ownCloud Admin GUI ##

The ownCloud server is now ready to be configured via a WEB Browser. Open a WEB Browser and enter in the IP Address configured for the ownCloud server in the following format:

- ***Example Input:***  http://192.168.203.133/owncloud (press enter to continue).

***Figure 1:*** Launch the ownCloud Admin GUI

![](https://i.imgur.com/RwIDJxr.jpg)

The admin configuration window will be displayed.

***Figure 2:*** ownCloud Admin Configuration Window

![](https://i.imgur.com/UJKnQra.jpg)

- Navigate down to the **Username** parameter setting and enter in the **Admin Username**. 
- Navigate down to the **Password** parameter setting and enter in the **Password for Admin**.

- Navigate down to the **Data folder** parameter setting, ensure the location displayed is correct. If it is not correct update it to the proper location.

***Figure 3:*** Storage and Database Settings Window

![](https://i.imgur.com/v2XD80B.jpg)

***Note: Please read through the next step carefully so that the proper database is selected.***

Use the next step to select the database type that will be used for the installation by clicking on either **SQLite** or **MYSQL/MariaDB**.

#### For SQLite ####

- Navigate down to the **Configure the database** parameter setting. SQLite is the default setting for the installation. If SQLite is the database that will be used then navigate down to the **Finish setup** button, and click on it to complete the database installation. 

#### For MYSQL/MariaDB ####

- If **MYSQL/MariaDB** will be used, select it by clicking on it. A dialog window will be displayed as shown below in Figure 4.

***Figure 4:*** MySQL/MariaDB Dialog Window


![](https://i.imgur.com/2uT9nuL.jpg)

- Enter in the **Database user**, **Database password**, **Database name** and update the **hostname** if necessary.

#####***Note: Record the information entered for safe keeping.***

- Navigate down to the **Finish setup** button, and click on it to complete the database installation.

With the Database setup now complete the Admin User management window will be displayed as shown below in Figure 5.

***Figure 5:*** Admin User Management Window

![](https://i.imgur.com/3UqH10f.jpg)

#####*Note: The dialog window displaying the desktop clients and the mobile clients can be closed, they will be covered later on in the guide.*

## User Management ##

Some of the user management functions that can be created or modified in the User Management Web Interface are as follows:

- Create new users


- View all of your users in a single scrolling window


- Filter users by group


- See what groups they belong to


- Edit their full names and passwords


- See their data storage locations


- Resetting a Lost Admin Password

#####*Note: A more inclusive list of user management functions can be found in the Server Administration Manual at the following link:*

[https://doc.owncloud.org/server/10.0/admin_manual/configuration/user/](https://doc.owncloud.org/server/10.0/admin_manual/configuration/user/ "Admin Guide")


In this Quickstart guide the focus will be on adding user accounts and enabling users.

### Adding Users ###


Log in to the ownCloud server as the admin user. The main admin screen will be displayed.


- Navigate over to the top right side of the admin screen and you should see the **admin user name** with a down arrow next to it. Refer to figure 6 below for the location of the users setting access.
 
***Figure 6:*** Access Admin User Management Settings

![](https://i.imgur.com/5hqyCcP.jpg)

- Navigate down to **Users** and select it. The user settings window will be displayed.

- Navigate to the **Username** box and enter in the username to be created.

- Navigate over to the **Password** box and enter in the password for the new user.
- Navigate over to the **Groups** selection and a drop down menu will be displayed, select the appropriate settings for the user being created. If a new group needs to be created set it up here.

- Navigate over to the **Create** to save the settings for the new user just created.


***Figure 6:*** Setting User Parameter Settings

![](https://i.imgur.com/bq1wnR8.jpg)

The new user created will show up in the list of users in the admin window. Repeat the 4 steps that were just performed to add all the users to be added at this time.

## Using the ownCloud Desktop Client ##

The ownCloud desktop client enables the end user to keep files across many devices synchronized. Whether it is a Windows, MAC or Linux PC or even Phones or Tablets all can  be synchronized using one of the ownCloud clients. 

The goal of ownCloud is to give access to your files wherever you are. While the web interface brings considerable flexibility and portability, when working with documents and pictures directly on your desktop. The desktop clients allow you to keep your existing work flow, making sharing and collaboration a breeze.

###This section will cover installing the Windows desktop client.

Download the Windows PC client from the following link:

[https://owncloud.org/download/#owncloud-desktop-client-windows](https://owncloud.org/download/#owncloud-desktop-client-windows "Windows Client Download")

Locate the ownCloud client named ***ownCloud-2.5.1.10973.10850.msi*** click on it and install it as you would any Windows application. Accept all the default settings when prompted.

- When prompted with the following screen enter in the server address for the ownCloud server.

***Figure 7:*** Installation Wizard Screen

![](https://i.imgur.com/ksat4kA.jpg)

The next dialog window will prompt you for the username and password. 

- Enter in the **username** and **password** for the ownCloud server.

The Local Folder Option screen will be displayed. 

- Select the settings which best suit the installation. You may sync all of your files on the ownCloud server, or select individual folders. The default local sync folder is ownCloud, in your home directory. You may change this as well. Navigate over to the **Connect** button and click on it to connect to the server.

***Figure 7:*** Local Folder Sync Screen

![](https://i.imgur.com/0wrltvV.jpg)


The client will attempt to connect to your ownCloud server, and when it is successful the following window will be displayed.

***Figure 8:*** Synchronization Successful Screen

![](https://i.imgur.com/IHanKfE.jpg)

There should be a ownCloud icon with a green circle with check mark in it signifying that you have connected to the ownCloud server.

Navigate to the Windows File Explorer and there should be ownCloud folder displayed with the folders and items on the ownCloud server. Click on the **Close** button to complete the installation.


###This section will cover installing the iOS mobile client.

On the iOS device go to the App store and purchase the ownCloud client and download it. When the download completes select the open button to open the ownClound client.

The **ownCloud Welcome** screen will be displayed. 

- Select the **Skip** button to continue. 


***Figure 9:*** ownCloud iOS Welcome Screen

![](https://i.imgur.com/bQzQloj.jpg)


The IP Entry screen will be displayed.

- Enter in the **IP Address** of the ownCloud server and press the **Connect** button to complete the setup. 

The next dialog window will prompt you for the username and password. 

- Enter in the **username** and **password** for the ownCloud server.****

***Figure 10:*** IP Entry and Connect to ownCloud Server Screen

![](https://i.imgur.com/a1PnVFQ.jpg)


After the iOS connects to the ownCloud server the Synchronization screen will be displayed as shown below.

***Figure 11:*** iOS Synchronization Successful Screen

![](https://i.imgur.com/mRe3qtO.jpg)





#### End of Quickstart guide. ####

  
























 








  








