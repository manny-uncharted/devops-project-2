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
