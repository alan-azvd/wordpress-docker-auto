# prestashop-docker-auto
Wordpress Docker install automation setup

## Step 1 - Enter super user mode
    sudo su

## Step 2 - Build local image
    docker compose -f default.yml up

## Step 3 - Check if no store container is running (the command below shoud return empty)
    docker-compose ps

## Step 4 - Setup the store stack
    env STORE="your-store-name" DOMAIN="yourstoredomain.com" docker stack deploy -c default.yml your-docker-stack-name

## Step 5 - Wait a few minutes, meanwhile check the installation logs
get the container id

    docker container ps
    
check the logs

    docker container logs your_store_container_id
      
## Step 6 - Check your store
    https://yourstoredomain.com
