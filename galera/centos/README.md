
# a three node galera cluster

# build container images...
docker build -t centos:galera-node1 ./    
docker build -t centos:galera-node2 ./    
docker build -t centos:galera-node3 ./    

# deploy container
docker run --detach=true --name node1 -h node1 centos:galera-node1 --wsrep-new-cluster --wsrep-cluster-name=galera-cluster --wsrep-cluster-address=gcomm://   

docker run --detach=true --name node2 -h node2 --link node1:node1 centos:galera-node2 --wsrep-cluster-name=galera-cluster --wsrep-cluster-address=gcomm://node1   

docker run --detach=true --name node3 -h node3 --link node1:node1 centos:galera-node3 --wsrep-cluster-name=galera-cluster --wsrep-cluster-address=gcomm://node1   



