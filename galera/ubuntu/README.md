
# build container image
docker build -t ubuntu:galera-node1 ./    

# run container image
docker run -i -d --name node1 -p 3306:3306 -p 4567:4567 -p 4568:4568 -p 4444:4444 ubuntu:galera-node1


