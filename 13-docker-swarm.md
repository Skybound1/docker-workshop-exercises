# Docker Swarm

### Exercise 1

Initiate a swarm on your host

### Exercise 2

Now you have a swarm master running on your host, try adding the `docker-machine` VM to the swarm.

You will need to first get the join-token from the swarm master (aka your host) to run on the VM

### Exercise 3

Deploy the small web db stack from the docker compose exercises onto the swarm

You can find a built image of the app at `skybound/small-web-db`

### Exercise 4

Add a deployment constraint to the database to keep it on your host

### Exercise 5

Make the app service a global deployment

### Exercise 6

Add IPSec encryption to the overlay network and verify it works by Wiresharking before and after

```
networks:
    default:
        driver: overlay
        driver_opts:
            encrypted: "true"
```
