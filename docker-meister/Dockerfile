FROM ubuntu

RUN apt-get update && \
    apt-get install -y nginx

COPY /var /var
COPY /etc /etc

RUN ln -s /etc/nginx/sites-available/docker-task.ddns.net /etc/nginx/sites-enabled && \
    rm /etc/nginx/sites-enabled/default && \
    groupadd -r user && \
    useradd -g user user && \
    chown -R user:user /etc/nginx && \
    chown -R user:user /var && \
    chown -R user:user /run

USER user

CMD ["nginx", "-g", "daemon off;"]
