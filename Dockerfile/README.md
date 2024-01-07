# This file is going to some introduction regarding how to build the Accel-sim Docker images 

## Dependencies
It need to have Docker and Nvidia docker installed. This Readme does not conver this part

## Notes.
Though using this docker file can simply your work to build Accel-sim, you still need to do further build steps after you have the docker containner running. This is because that some build script has problem to run when building the docker images. The extra step has been given in the Dockerfile.txt, you can refer to them, for example
```bash
WORKDIR /root/accel-sim-framework
#Pls run following two command inside running docker containner
#RUN ./util/tracer_nvbit/install_nvbit.sh
#RUN make -C ./util/tracer_nvbit
```
## Build docker
Command to build the docker
```bash
sudo docker build -t AccelDocker:01 -f Dockerfile.txt .
```

## Problem solving
If it is too slow to pull the code from github. 
You may ctrl+c to stop build the docker, and rebuild docker again. If it is still to slow. You you change
Change
```bash
git clone https://github.com/accel-sim/accel-sim-framework
```
To
```bash
git clone https://gitclone.com/github.com/accel-sim/accel-sim-framework
```

