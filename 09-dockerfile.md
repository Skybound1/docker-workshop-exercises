## Dockerfile

### Exercise 1

Create a project directory and make a `Dockerfile` file.

Create your own image; just an Alpine base for now.

### Exercise 2

Extend your image to have Python3 installed on image build.

### Exercise 3

Make a dummy directory on your host with some random files in it.

Copy the contents of that directory into your image.

### Exercise 4

Make your image run a Python3 one-line web server to server the contents of the directory you copied in the previous exercise. This should run on container build.

`python -m http.server 80`

Run a container and map the port to your host, then `curl`.

Note: You'll need to use WORKDIR to change the working directory before you call CMD.

### Exercise 5

Mount a directory from your host and serve it over HTTP.
