## Docker-Compose

### Exercise 1

You're going to build a `docker-compose.yml` for an awesome web app.

Clone this repo:

https://github.com/sheeplepie/small-web-db

Here's a skeleton `docker-compose.yml`:

```
version: '3'

services:
    app:

    db:

volumes:
```

The application needs a backend MongoDB to function. You'll also want to map the MongoDB storage files to somwhere convenient on your host for easy back-up.

You'll have to google around for these exercises, but we're here to help so just holler if you need a hand.

### Exercise 2

The `app` container is built from a custom image. The `Dockerfile` is in the cloned repo.

Amend the `docker-compose.yml` skeleton to build the `Dockerfile`.

See if it build with `docker-compose up`.

### Exercise 3

The app's `Dockerfile` doesn't have a `CMD` option, so a container built from it will do nothing and fizzle out.

You could amend the `Dockerfile` to add a `CMD` as we did before, but instead use the compose `command` option to run `python3 /app/app.py` when it's brought up.

Give it a spin with `docker-compose up`.

Get a shell on your `app` container and browse around. Make sure the `/app/` directory is in the root and has what you expect. List processes on your host to check that you're running a `python3` process.

### Exercise 4

You want to bind port 80 in the container to a port on the host, let's say 8000.

At this point you don't have a DB so the service should timeout and throw a 500 if you `curl localhost:8000`.

### Exercise 5

Give yourself a DB. The service uses MongoDB and the latest image should do.

Make sure your DB service is called `db` (or name it whatever you want and ensure it matches in `/app/app.py`, then rebuild the image when you spin up: `docker-compose up --build`).

Make sure you tell compose to spin up `db` before `app`.

You should now be able to hit the service.

### Exercise 6

Use a named volume to store your database files in an easily accesible way (`/data/db/` directory on the `mongo` image).
