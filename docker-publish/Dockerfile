#NodeJS Alpine Build
FROM node:alpine3.14
#Setting Work Directory
WORKDIR /bot/
# Setting Up All Permissions to all users to the Workdir
RUN chmod 777 /bot
#Installation of dependencies
RUN sed -i 's/https\:\/\/dl-cdn.alpinelinux.org/https\:\/\/alpine.global.ssl.fastly.net/g' /etc/apk/repositories && \
    apk add --no-cache --update \
        ca-certificates \
        git \
        bash \
        aria2 \
        wget \
        unzip \
        curl \
        unrar
# Copy all files from BuildDir to Workdir
COPY . .
#Building and Installation
RUN npm i -g typescript && \
    yarn && \
    tsc
CMD ["bash"]
