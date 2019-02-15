---
layout: page
title: Install the ownCloud Server
permalink: /install/
---

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