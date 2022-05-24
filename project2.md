## Implementation of the LEMP STACK

In this project we would work on the following components of the LEMP stack:

- connecting to the ec2 instance.
- Installing the nginx web server.
- Installing the MySQL database.
- configuring nginx to use php processor.
- testing php with nginx.
- retrieving data from mysql database with php.

### connecting to the ec2 instance
Here we would have to connect to the EC2 instance we created on AWS.

    ```
    ssh -i "devops-class.pem" ubuntu@ec2-107-22-46-241.compute-1.amazonaws.com
    ```

Results:
    ![Connecting to the EC2 instance on AWS.](./img/ec2-instance-connection.png)


### Installing the nginx web server
Here we have to set up the nginx web server.

- update the linux server with the latest version of the software.
    ```
    sudo apt update
    ```

    Results:
    ![Update the linux server with the latest version of the software.](./img/sudo-apt-update.png)

    ![Update the linux server with the latest version of the softwa.](./img/sudo-apt-update2.png)

- Getting Nginx installed on our instance
    ```
    sudo apt install nginx
    ```

    Results:
    ![Getting Nginx installed on our instance.](./img/sudo-apt-install-nginx.png)

    ![Getting Nginx installed on our instance.](./img/sudo-apt-install-nginx2.png)
    
    When prompted, enter Y to confirm that you want to install Nginx. Once the installation is finished, the Nginx web server will be active and running on your Ubuntu 20.04 server.

- Verifying that nginx is installed on the instance and is running as a service.
    ```
    sudo systemctl status nginx
    ```

    Results:
    ![Verifying that nginx is installed on the instance.](./img/sudo-systemctl-status-nginx.png)

    Our server is running and we can access it locally and from the Internet

- checking how we can access it locally in our Ubuntu shell.
    ```
    curl http://localhost:80
    ```

    Results:
    ![checking how we can access it locally in our Ubuntu shell.](./img/curl-httplocalhost80.png)

- retrieving our ip address:
    ```
    curl -s http://169.254.169.254/latest/meta-data/public-ipv4
    ```

    Results:
    ![retrieving our ip address.](./img/getting-ipaddress.png)

- Now it is time for us to test how our Nginx server can respond to requests from the Internet.

    Open a web browser of your choice and try to access following url
    ```
    http://<your-ip-address>:80
    ```

    Results:
    ![Now it is time for us to test how our Nginx server can respond to requests from the Internet.](./img/nginx-test.png)

### Installing the MySQL database
MySQL is a popular relational database management system used within PHP environments, so we will use it in our project. As we would need you need a Database Management System (DBMS) to be able to store and manage data for your site in a relational database. 

- Installing the MySQL server.
    ```
    sudo apt install mysql-server
    ```

    Results:
    ![Installing the MySQL server.](./img/install-mysql.png)

    ![Installing the MySQL server.](./img/install-mysql2.png)

    When prompted, enter Y to confirm that you want to install MySQL. Once the installation is finished, the MySQL server will be active and running on your Ubuntu 20.04 server.

- When the installation is finished, log in to the MySQL console by typing.
    ```
    sudo mysql
    ```

    Results:
    ![When the installation is finished, log in to the MySQL console by typing.](./img/sudo-mysql.png)

- altering the root password of mysql login.
    ```
    ALTER USER 'root'@'localhost' IDENTIFIED BY '<your-password>';
    ```

    Results:
    ![altering the root password of mysql login.](./img/alter-root-password.png)

    and then exit with the command
    ```
    exit
    ```

- starting the interactive script using the command
    ```
    sudo mysql_secure_installation
    ```
    This will ask if you want to configure the VALIDATE PASSWORD PLUGIN.

    Results:
    ![starting the interactive script using the command.](./img/mysql-interactive-script.png)

- When you’re finished, to test if you’re able to log in to the MySQL console by typing.
    ```
    sudo mysql -p
    ```

    Results:
    ![To test if you’re able to log in to the MySQL console by typing.](./img/sudo-mysql-p.png)

    Notice the -p flag in this command, which will prompt you for the password used after changing the root user password.

    To exit the MySQL console,
    ```
    exit
    ```
    Your MySQL server is now installed and secured. Next, we will install PHP, the final component in the LEMP stack.


### Installing PHP on our AWS Instance.
PHP is a popular general-purpose scripting language that is especially suited to web development. It is a widely-used, free, and efficient alternative to Microsoft's ASP.NET and Java servlets.

While Apache embeds the PHP interpreter in each request, Nginx requires an external program to handle PHP processing and act as a bridge between the PHP interpreter itself and the web server. 

This allows for a better overall performance in most PHP-based websites, but it requires additional configuration. we’ll need to install php-fpm, which stands for “PHP fastCGI process manager”, and tell Nginx to pass PHP requests to this software for processing. Additionally, we’ll need php-mysql, a PHP module that allows PHP to communicate with MySQL-based databases. Core PHP packages will automatically be installed as dependencies.

- To install these 2 packages at once, run:
    ```
    sudo apt install php-fpm php-mysql
    ```

    Results:
    ![To install these 2 packages at once.](./img/install-php-fpm-mysql.png)

    ![To install these 2 packages at once.](./img/install-php-fpm-mysql2.png)

    When prompted, enter Y to confirm that you want to install PHP. Once the installation is finished, the PHP server will be active and running on your Ubuntu 20.04 server.