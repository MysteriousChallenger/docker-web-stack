How to launch a local WordPress server in ~5 minutes
Uses approx (1.3 gb)

1) Install docker and docker-compose

    On linux, this was: 
        sudo apt install docker docker-compose
        sudo systemctl start docker

    For other platforms: 
        https://docs.docker.com/engine/install/ 
        https://docs.docker.com/compose/install/

2) Build and run the containers
    
    Open a console in the same directory as docker-compose.yml
    docker-compose.yml contains configuration data for both WordPress and Mysql.

    2a) Build and Launch
        On linux (and possibly mac):
            sudo docker-compose up -d

        For other platforms:
            docker-compose up -d

    docker should then download WordPress and Mysql, and launch them.

    2b) Verify both are launched
        
            docker container ls
        or
            sudo docker container ls

        Status should say Up X seconds/minutes

3) Navigate to localhost:8000 in your browser (WordPress may take a minute to start working)



4) Cleanup and uninstall docker

    On linux:
        sudo apt-get purge docker-engine
        sudo apt-get autoremove --purge docker-engine
        sudo rm -rf /var/lib/docker /etc/docker
        sudo rm /etc/apparmor.d/docker
        sudo groupdel docker
        sudo rm -rf /var/run/docker.sock

    For other platforms:
        https://macpaw.com/how-to/uninstall-docker-mac
        https://docs.microsoft.com/en-us/virtualization/windowscontainers/manage-docker/configure-docker-daemon