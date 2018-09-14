
# create docker swarm cluster, 
## create docker swarm manager. 
docker swarm init --advertise-addr=192.168.0.50 --listen-addr=192.168.0.50


<p>
 out put 

===============================================
[root@docker-swarm-01 kubernetes]# docker swarm init --advertise-addr=192.168.0.50 --listen-addr=192.168.0.50
Swarm initialized: current node (kfe9hapxvnk83hzwp72e3fwui) is now a manager.

To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-1shbho18pjg3vxwa58c3gm9ojshhlxv69g2pkjv4jf96ryo9a7-942skaao7luwxje3z16mdo3kr 192.168.0.50:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.

[root@docker-swarm-01 kubernetes]#


=============================================================================
</p>

# join docker swarm cluster as a worker node. 

docker swarm join --token SWMTKN-1-1shbho18pjg3vxwa58c3gm9ojshhlxv69g2pkjv4jf96ryo9a7-942skaao7luwxje3z16mdo3kr 192.168.0.50:2377

# Join docker swarm cluster as a manager node. 

<p>
1- get docker swarm manager node token from manager node.

<docker swarm join-token manager>

<output 

docker swarm join-token manager

+++++++++++++++++======================================================
[root@docker-swarm-01 kubernetes]#  docker swarm join-token manager
To add a manager to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-1shbho18pjg3vxwa58c3gm9ojshhlxv69g2pkjv4jf96ryo9a7-bl1lqmplw4pkc2xw58e8hcgsy 192.168.0.50:2377

[root@docker-swarm-01 kubernetes]# vim Dockerswarm.md                           



===========================================================================


END result 

check node status 

<docker node ls >

[root@kuber-02 ~]# docker node ls
ID                           HOSTNAME         STATUS  AVAILABILITY  MANAGER STATUS
kfe9hapxvnk83hzwp72e3fwui    docker-swarm-01  Ready   Active        Leader
lquscg3f0evn4xaqb1d74d0fn *  kuber-02         Ready   Active        Reachable
mu39a4frfvs3fbqt2l8449te9    docker-swarm-02  Ready   Active        Reachable
[root@kuber-02 ~]#


## Docker swarm commands 
docker stack deploy bitbucket  --compose-file docker-compose.yml 
docker service update jira_jira  --publish-add 8080:8080
docker network create --subnet 192.168.0.0/24 --aux-address "DefaultGatewayIPv4=192.168.0.1" --gateway=192.168.0.200 homenet
