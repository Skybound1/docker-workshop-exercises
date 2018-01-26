## Inside Container

### Exercise 1

Search for and pull `alpine`.

Get an interactive shell in an `alpine` container.

### Exercise 2

List container's distribution and kernel.

**Info**
Distribution info is in `/etc/os-release` on `alpine`

Compare these to your host.

### Exercise 3

Find your shell's proces ID on your host.

### Exercise 4

Install `figlet` in your `alpine` container. Run it with some parameters.

**Info**
`alpine` uses the `apk` package manager:

* apk update
* apk search _something_
* apk add _something_

### Exercise 5

Exit your previous container.

Re-run your container and make sure you're in the same container

(Can you run `figlet` without re-installing it?)
