FROM ubuntu:18.04

# root user
RUN apt-get update --fix-missing && \
    apt-get install -y redis-server && \
    rm  -rf /var/lib/apt/lists/*

# add custom group and user with id = 500
RUN groupadd -g 500 myredis && \
    useradd -u 500 -g myredis myredis
# use created user
USER myredis:myredis

EXPOSE 6379

CMD redis-server