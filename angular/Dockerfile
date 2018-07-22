FROM debian:jessie

RUN apt-get update && apt-get upgrade -y && apt-get install -y apt-utils vim curl git unzip make

# Install NodeJS
RUN curl --silent --location https://deb.nodesource.com/setup_8.x | bash -
RUN apt-get install -y nodejs
# Install AngularCli
RUN npm install -g @angular/cli

ADD root/bin/init /root/bin/
RUN chmod +x /root/bin/init

# alias
RUN echo 'alias ll="ls -la"' >> ~/.bashrc

# Expose port for ng server
EXPOSE 4200
EXPOSE 4201

CMD /root/bin/init

WORKDIR /var/www/cms
