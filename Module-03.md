# Module 3: Docker Compose

## Introduction
In the previous Docker module, we saw an example of a container running both php-fpm and nginx. Docker Compose allows us to easily run multiple containers alongside each other, and well mirror our production environments. It aims to simplify this process by using a `docker-compose.yaml` file to define the services, networks, and volues. After this module, you should be comfortable with basic tasks required to interact and manage a local container environment.

For this module, *create a new Git repo* for your Docker Compose work in Module 3.

If you haven't already, it is recommended that you read through each of the official documentation resources listed below and follow some of the links within each resource to help clarify specific tools and their purposes.

Resources and articles:

- [What is a Container?](https://www.docker.com/resources/what-container)
- [Official Docker Engine Docs](https://docs.docker.com/engine/docker-overview/)
- [Official docker-compose.yaml Reference](https://docs.docker.com/compose/compose-file/)
- [Official Docker Compose Docs](https://docs.docker.com/compose/overview/) - [(common use cases)](https://docs.docker.com/compose/overview/#common-use-cases)

---

## Completing the Module

1. Create a file called _docker-compose.yaml_
2. In your _docker-compose.yaml_ file, add a new service called `hello-container` with the image `hello-world`
3. Create a new file called _docker-compose-module.txt_, and paste the output of `docker-compose up`.

    > If you look from the top of the output, you should be able to see the
    process that docker-compose goes through to start the `hello-container` service.
    A new image is pulled, started, and exits, just like you would do by hand
    to start and stop a container.

4. Commit your changes and push up.
5. Create a new directory called _scripts_.
6. In that new directory, create a new executable file called _welcome-compose.sh_ containing the following:
```
#!/bin/bash
echo 'Hello, Docker Compose!'
```
7. Update the `hello-world` service in your _docker-compose.yaml_ file to use your `gentux/alpine-bash` image from module 2.
8. In the _docker-compose.yaml_ file, mount the new `./scripts` directory as the `/home/scripts` directory within the `hello-container` service.
9. Update the `hello-container` service to run the _welcome-docker.sh_ file and paste the output of `docker-compose up`.
10. Commit your changes and push up.
11. Create a new service called `data-container` that uses the `alpine:latest` image and mounts the same volumes as the `hello-container` service.
12. Commit and push up.

> Note we're manually putting this file in both containers at this time. Now let's use a shared volume to accomplish the same thing.

13. Create a new Dockerfile from `alpine:latest`
    * On build the dockerfile should create a directory `/home/scripts`
    * Copy the `./scripts` directory from your machine into the newly created /home/scripts directory in the container
14. Update the docker-compose file so that the data-container service not builds using this newly created Dockerfile
15. Add a named volume mount called scriptsdir to docker-compose which will be used by both containers
16. Mount the named volume in the location we copied our `./scripts` folder to.
17. `docker-compose up` and exec into the `hello-container` to confirm the `welcome-compose.sh` script is in `/home/scripts`
17. Commit your changes and push up.


---

## Wrapping Up

When you are done, verify you have pushed your changes to GitHub. Please create a tag called v1.0 with a message of "ready for review" in your docker compose repo. Be sure your tags are pushed to the remote repository and are visible in GitHub.

Create an issue titled **Review Module 3 - Docker Compose** and assign it to [**@generationtux-helmsmen**](https://github.com/generationtux-helmsmen).
