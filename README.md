# playDockerSwarm

###Framework
<p align="center">
  <img src="http://blog.daocloud.io/wp-content/uploads/2015/01/swarmarchitecture.jpg" width="450"/>
</p>

###Command

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

- [docker secret commands](https://docs.docker.com/engine/swarm/secrets/)
  - docker secret create
  - docker secret inspect
  - docker service ls
  - docker secret rm
