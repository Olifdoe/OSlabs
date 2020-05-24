FROM debian
ADD debian.list /etc/apt/sources.list.d/
RUN apt-get update && apt-get -y upgrade && apt -y install nginx && apt-get clean && \
    cd /var/www/ && rm -rf ./* && \
    mkdir -p dariasolifdoes.net/img && \
    chmod -R 754 /var/www/dariasolifdoes.net/ && \
    useradd Daria && groupadd Olefirenko && usermod -aG Olifdoe && \
    chown -R Olifdoe /var/www/dariasolifdoes.net/ && \
    sed -i 's/\/var\/www\/html/\/var\/www\/dariasolifdoes.net/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/user www-data/user Daria/g' /etc/nginx/nginx.conf
ADD index.html /var/www/dariasolifdoes.net/
ADD img.jpg /var/www/dariasolifdoes.net/img/
CMD ["nginx", "-g", "daemon off;"]