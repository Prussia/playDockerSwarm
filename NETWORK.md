# Network

## [Swarm mode overlay networks and unmanaged containers](https://docs.docker.com/engine/userguide/networking/overlay-security-model/#swarm-mode-overlay-networks-and-unmanaged-containers)

```
$ docker network create --opt encrypted --driver overlay my-multi-host-network

dt0zvqn0saezzinc8a5g4worx

```

Because the overlay networks for swarm mode use encryption keys from the manager nodes to encrypt the gossip communications, only containers running as tasks in the swarm have access to the keys. Consequently, containers started outside of swarm mode using docker run (unmanaged containers) cannot attach to the overlay network.

For example:

```
$ docker run --network my-multi-host-network nginx

docker: Error response from daemon: swarm-scoped network
(my-multi-host-network) is not compatible with `docker create` or `docker
run`. This network can only be used by a docker service.
```

To work around this situation, migrate the unmanaged containers to managed services. For instance:
```
$ docker service create --network my-multi-host-network my-image
```
