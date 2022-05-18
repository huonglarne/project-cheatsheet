# Build image

- Specify Dockerfile: `-f path_to_file`

- Specify build stage: `--target=stage_name`

- Specify tag for image: `-t tag_name`

- Specify building context: path at the end of command

`docker build -f $DIR/../Dockerfile --target=stage_name -t tag_name $DIR/..`

# Run image

## Using command

- Run in detached mode: `-d`

- Publish port: `-p 8000:80`

- Specfiy GPU: `--gpus all`

- Mount volume: `-v folder:/folder`

- Go into container and interact with it: `-it`

- Set entrypoint command: `--entrypoint command`

`docker run -v "$(pwd)"/src:/src -it --entrypoint /bin/bash image_name:tag`

## Using docker compose

 - Run in detached mode: `-d`

 - Specify docker compose file: `--file path_to_file`

 - Specify environment file: `--env-file path_to_file`

`docker-compose --env-file .env --file docker-compose.yml up -d`

# Other commands

## List

- List images

`docker images`

- List containers and their IDs

`docker ps`

## Interact with container

Execute command in container. The container must be running in detached mode.

`docker exec -it container_id command`

- Open terminal: `/bin/bash`

- Debug python file in remote attache mode: `python -m debugpy --listen 0000:5678 --wait-for-client file.py argument` 

## Kill

Kill running container

`docker kill id`

`docker rmi image`

`docker rmi $(docker images -a -q)`
