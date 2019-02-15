---
layout: page
title: Configuring the ownCloud IP Address and Port Number
permalink: /ip_port/
---

ownCloud is served by your web server. Users can connect to your ownCloud server using the IP address and port number configured in the web server that is used by ownCloud. 

If you do not know the IP address of your web server, you can open a terminal on the server and use the **ifconfig** command to determine the address. 

If you would like to set a specific port for users to connect on, you can set the port value in the web server. For example, if you are using an Apache web server and you would like to change the listening port number to 8080, do the following: 

1. Open your **httpd.conf** file in a text editor. 

    Assuming you have not changed the default value previously, look for the line with `Listen 80`.

2. Change the listen line to your desired port number. 

    For example:

    `Listen 8080`

3. Save the file and restart your Apache server.

    Users can now connect to your server using the assigned IP address and port number. For example: `https://192.168.0.1:8080`.



