To build image
`docker build -t feedback-node:volumes . `

To build image with arguments
`docker build -t feedback-node:dev --build-arg DEFAULT_PORT=8000 .`

To run container with named volume and bind mount

`docker run -p 3000:80 -d --name feedback-app --rm -v feedback:/app/feedback -v ${pwd}:/app -v /app/node_modules feedback-node:volumes`

To run container with named volume and bind mount with read only volume

`docker run -p 3000:80 -d --name feedback-app --rm -v feedback:/app/feedback -v ${pwd}:/app:ro -v /app/node_modules -v /app/temp feedback-node:volumes`

To stop container
`docker stop feedback-app`

To check named volume
`docker volume ls`

To create a new volume
`docker volume create <name>`

To inspect the volume
`docker volume inspect <name>`

To clear volume
`docker volume rm <name>`

or `docker volume prune`
