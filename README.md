# Implementation of LEMP Stack in aws EC2 instance

This is a project that helps me document my journey through devops in my second project. I am using AWS EC2 instance to deploy my LEMP stack.

## LEMP STACK
LEMP stack is an acroynm for Linux, Nginx(usually pronounced as engine-x, hence the E in the acronynm), MySQL, and PHP or Python as the case maybe. It is an open-source web application stack used to develop web applications.

### Components of the LEMP Stack
- Linux: It is a free and open-source operating system. It is used to run the web server. As it's know to be highly secure and less vulnerable to malware and viruses. Linux is known to be highly secure and stable and very flexible in customization as it's entirely open-source with a very strong community support. Which means if you understand what you're doing you can fork the source code and make your own customizations then boom you have your own version of Linux.

- Nginx: It is a web server that follows an event-driven approach and handles multiple requests within one thread. It handles requests for a web page coming from a web browser, the web server is Nginx. Nginx then passes that request to the server-side technologies used in the LEMP stack for instance as a server-side scripting language like PHP or Python to communicate with server and database. Nginx is used for simple installations and configurations, it has load balancing support for processing large numbers of requests. Nginx is used to serve static files such as images, CSS, and JavaScript.

- MySQL: It is an open-source SQL-based database that is used to store data and manipulate data while maintaining data consistency and integrity. It organizes data in tabular form in rows and columns. It is also ACID-compliant. MySQL offers strong data protection and integrity. It is used to store data in a relational database. It is highly scalable and can handle millions of users. It is highly scalable and can handle millions of users.

- PHP or Python: Originally the LEMP stack was used with PHP which stands for Hypertext Preprocessor, as its language that works on the server-sside allowing communication with the database MySQL and does all operations with user requests like fetching data, adding data or manipulating data or preprocessing data. Python can also be used in place of Python.

In this project I would work on the following components of the LEMP stack:

- Installing the nginx web server
- Installing the MySQL database
- configuring nginx to use php processor
- testing php with nginx
- retrieving data from mysql database with php

![Link to the project document](./project2.md)