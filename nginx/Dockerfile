From ubuntu:latest
ENV dir /etc/nginx/
WORKDIR $dir
RUN apt-get update
RUN apt-get install zip -y && apt-get install unzip -y 
RUN apt-get install nginx -y 
ADD nginx.conf /etc/nginx/nginx.conf
ADD webapp.conf /etc/nginx/conf.d/webapp.conf
ADD certificate.pem /etc/nginx/ssl/
ADD key.pem /etc/nginx/ssl/
EXPOSE 8083
CMD ["nginx", "-g", "daemon off;"]
