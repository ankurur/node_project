FROM 482085450016.dkr.ecr.us-east-1.amazonaws.com/project2:latest

RUN yum update -y && yum install httpd httpd-tools -y
WORKDIR /var/www/html/
COPY index.html . 
EXPOSE 80
RUN yum install net-tools -y
 
CMD ["/usr/sbin/httpd","-D","FOREGROUND"]
