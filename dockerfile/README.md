# This dockefile installs the affordance-net and build it

### Run
```console
nvidia-docker build -t denny1232/affordance:latest .
nvidia-docker run --gpus all -itd denny1232/affordance:latest /bin/bash
```

### Copy pretrained and dataset
```console
docker cp IIT_Affordances_2017 <CONTAINER_NAME>:~/
docker cp pretrained <CONTAINER_NAME>:~/
```

### List out the CONTAINER_NAME
docker container ls
