---
layout: page
title: Administrators
permalink: /admin/
---

# Install the ownCloud Server

The ownCloud Server is deployed on a Linux server. Before you begin, be sure that your server meets all system requirements including supported database, Web server, and PHP options. For information on system requirements, see [System Requirements](https://doc.owncloud.org/server/administration_manual/installation/system_requirements.html).

In this example, an ownCloud Community Edition server is installed as a single server using the command line. Other installation options are available, see [**ownCloud Server** > **Admin Manual** > **Installation** > **Installation Options**](https://doc.owncloud.org/server/index.html).  

1. Download the ownCloud Server tarball.

    The tarball is available from [ownCloud Download Page](https://owncloud.org/download/#instructions-server).

2. Unpack the tarball.

    Decompress the tarball into the appropriate directory, for example **/var/www/owncloud/**.

3. Set your webserver user to be the owner of your **owncloud** directory. 

    For example:

    `$ sudo chown -R www-data:www-data /var/www/owncloud/`

4. Use the **occ** command to perform the installation.

    Execute the **occ** command from the root directory of the ownCloud source. For example:

    ```
    $ cd /var/www/owncloud/
    $ sudo -u www-data php occ maintenance:install 
        --database "mysql" --database-name "owncloud" \
        --database-user "root" --database-pass "password" \
        --admin-user "admin" --admin-pass "password"
    ```
5. Apply permissions to your ownCloud files and directories.

    For security purposes, you must apply the appropriate permissions to your ownCloud files and directories. For more information on this, see [Post Installation Steps](https://doc.owncloud.com/server/administration_manual/installation/installation_wizard.html#post-installation-steps) in the ownCloud documentation. 

# Configure the Server IP Address and Port

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

# Add a User to ownCloud
