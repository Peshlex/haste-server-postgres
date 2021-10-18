# Using docker-compose

docker-compose up
docker-compose down

# Additional clean-up

docker volume prune
docker network prune
docker network ls

# Using dockerfile

docker network create pastebin

# Build the images

docker build -f ./Dockerfile.postgres -t haste-pg .
docker build -f ./Dockerfile.hastesrv -t haste-srv .

# Run from images

docker run -d --name=pg --net=pastebin haste-pg
docker run -d -p 7777:7777 --name=haste --net=pastebin haste-srv