## Docker Demo Voting app

http://play-with-docker.com

### Init Swarm Cluster

```
docker swarm init --advertise-addr $(hostname -i)
docker node ls
```

### Creating Services
```
docker service create -p 80:80 --name web nginx:latest
docker service ls
```

#### Scaling up

```
$ docker service inspect web

$ docker service scale web=3

$ docker service ps web
```

### Draining node
```
docker node update --availability drain node2
docker service ps web
docker node ls
```

### Running stack

```
docker stack deploy --compose-file=docker-stack.yml voting_stack
```

```
docker service ps voting_stack_vote
```
