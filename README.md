# salt-dev-docker
Salt stack docker files useful to test salt environements during developement.

# Build docker image saltmaster

    docker build -t manikantanr/salt-master -f Dockerfile.salt.master .

# Build docker image saltminion

    docker build -t manikantanr/salt-minion -f Dockerfile.salt.minion .

# Create salt network and start containers in it.
    docker network create salt
    
    # To run in background
    docker run -d --net salt --name salt --hostname salt manikantanr/salt-master
    docker run -d --net salt --name salt-minion-1 --hostname salt-minion-1 manikantanr/salt-minion
    
    # To run interactively
    docker run -it  --net salt --name salt --hostname salt manikantanr/salt-master
    docker run -it  --net salt --name salt-minion-1 --hostname salt-minion-1 manikantanr/salt-minion
