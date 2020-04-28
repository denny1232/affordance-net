# This dockefile installs the affordance-net and build it

### Run
```console
nvidia-docker build -t denny1232/affordance:latest .
nvidia-docker run --gpus all -itd denny1232/affordance:latest /bin/bash

nvidia-docker run --gpus all --net=host --env="DISPLAY" --volume="$HOME/.Xauthority:/root/.Xauthority:rw" -itd denny1232/affordance:latest /bin/bash
```

### Copy pretrained and dataset
```console
docker cp IIT_Affordances_2017 <CONTAINER_NAME>:/root/path/to/affordance-net/repository
docker cp pretrained <CONTAINER_NAME>:/

docker cp pretrained crazy_ptolemy:/root/affordance-net/
```

### List out the CONTAINER_NAME
docker container ls

### Copy file from host to container
docker cp <FILE> RIT
