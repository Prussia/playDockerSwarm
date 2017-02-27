# playDockerSwarm

###[Framework](https://yeasy.gitbooks.io/docker_practice/content/swarm/intro.html)
<p align="center">
  <img src="./swarm.png" width="450"/>
</p>

###[Command](https://github.com/docker/docker/tree/master/docs/reference/commandline)

- Show Node Status
  
   ```
   $ docker node ls
   ```
- Create 4 instances for tomcat8-jre8

    ```
    $ docker service create --replicas 4 --name <SERVICE_NAME> --publish 8080:8080 tomcat:8-jre8
    ```
- Update service 
  
   ```
   $ docker service update --publish-add 8080:8080 <SERVICE_NAME>
   ```
   
- Show all service status

  ```
  $ docker service ls
  ```  
- Show the specific service status

  ```
  $ docker service ps <SERVICE_NAME>
  ```
- [docker service](https://docs.docker.com/engine/reference/commandline/service/)
  - [docker service create](https://github.com/docker/docker/blob/master/docs/reference/commandline/service_create.md)
    - --mount | Attach a filesystem mount to the service
    - --name | Service name
    - --publish, -p | 	Publish a port as a node port
    - --read-only | false | Mount the container’s root filesystem as read only
    - --replicas | Number of tasks
    - --restart-condition | 	Restart when condition is met (none, on-failure, or any)
    
- [docker secret commands](https://docs.docker.com/engine/swarm/secrets/)
  - docker secret create
  - docker secret inspect
  - docker service ls
  - docker secret rm
