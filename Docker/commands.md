# Docker Commands

View all networks
```
docker network ls
```

Connect container to network
```
docker network connect {network} {container}
```

To connect to a container from another container, both containers must be on the same network.
