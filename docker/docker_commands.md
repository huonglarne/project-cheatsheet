## Build image

Specify Dockerfile: `-f path_to_file`

Specify build stage: `--target=stage_name`

Specify tag for image: `-t tag_name`

Build from folder: path at the end of command

`docker build -f $DIR/../Dockerfile --target=stage_name -t tag_name $DIR/..`

## Run image

Mount volume: `-v folder:/folder`

Go into container and interact with it: `-it`

Set entrypoint to be terminal: `--entrypoint /bin/bash`

`docker run -v "$(pwd)"/src:/src -it --entrypoint /bin/bash image_name:tag`

# Other commands

List images

`docker images`

List containers

`docker ps`

Kill running container

`docker kill id`

`docker rmi image`

`docker rmi $(docker images -a -q)`
