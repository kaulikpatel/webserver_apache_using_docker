webserver_apache_using_docker
There are three websites work on the Apache server using Docker 

Create a Dockerfile in your project
    FROM httpd:2.4
    COPY ./public-html/ /usr/local/apache2/htdocs/

Then, run the commands to build and run the Docker image:
     docker build -t my-apache2 .  (For Image)
     docker run -dit --name my-running-app -p 8080:80 my-apache2  (For Container)

     Example 
     docker build -t first-img:0.1 .
     docker run -dit --name first-container -p 8080:80 first-img:0.1
Visit http://localhost:8080⁠ and you will see It works!


Without a Dockerfile
If you don't want to include a Dockerfile in your project, it is sufficient to do the following:

    docker run -dit --name my-apache-app -p 8080:80 -v ${PWD}:/usr/local/apache2/htdocs/ httpd:2.4

    
