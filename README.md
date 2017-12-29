# reddcoin_core (bmp's experimental wallet)

# Step 1

// Install Docker and Docker Compose

Docker (choose your linux distro, there are several) :

https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/

Docker compose:

https://docs.docker.com/compose/install/

# step 2

Make sure that all the needed ports are opened on your linux machine and on your external firewall/router/ACL

# step 3
//to run it in the foreground:
docker-compose up   

//to run it in a deattached mode:
docker-compose up -d

// to stop the containers:

docker-compose stop

// in case you made any changes to docker-compose.yml it would be better if you'll use the 'rm' flag before you run it again

docker-compose rm

//entering the container

docker exec -it reddcoin-core /bin/bash

# NOTES - READ IT :

Reddcoin core '~/.reddcoin/' directory is externalized and mapped to './redd-data-dir' 
So whenever you want to check debug.log - do it from there, no need to enter the container.

!! You need to have a valid 'reddcoin.conf' file in './redd-data-dir' for starts (I've included one in this repo) !!

!! If you have a very weak machine - you might get any kind of out of memory error when building the reddcoin-core image
To go around it you'll have to create a swap file

You can clone https://github.com/utkagit/reddcoin-data to get a more or less up to date blockchain and copy the files to ./redd-data-dir
It might not be the best thing to do, so don't do it if your machine can handle the load when reddcoin-core is syncing with the blockchain
