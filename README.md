docker stop $(docker ps -a -q)
    docker rm $(docker ps -a -q)
    docker volume rm $(docker volume ls -q)
    docker network rm $(docker network ls -q)
    docker rmi $(docker images -q)
    docker system prune -a --volumes