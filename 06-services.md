## Services

### Exercise 1

Pull the `sheeplepie/small-web` image.

### Exercise 2

Run a daemonised `small-web`.

Confirm that you can't `curl` the service from your host.

### Exercise 3

Get a shell on your _running_ container.

Install `curl` in the container and `curl localhost`. Confirm the service is working in the container.

### Exercise 4

Run another `small-web` container, exposing the service this time.

Inspect the container to ensure the port is mapped to your host.

`curl` the service from your host.

Stop and delete your containers.
