# BIOVIA Discovery Studio Visualizer Client 2017R2 Container

There are two version: nouveau and nvidia-supported container. To use nvidia-supported container, you need to install nvidia driver and nvidia-docker2 on host.

To download the container:

 1. nvidia-supported container:
```
docker pull afandiadib/discovery-studio-visualizer:2017R2-nvidia
```
 2. nvidia-supported container:
```
docker pull afandiadib/discovery-studio-visualizer:2017R2-nouveau
```


- To run nvidia-accelerated container:
```
docker run --rm --user=$(id -u) \
           --env=DISPLAY \
           --volume=/home/$USER:/home/$USER \
           --volume=/media:/media \
           --volume=/mnt:/mnt \
           --volume=/etc/group:/etc/group:ro \
           --volume=/etc/passwd:/etc/passwd:ro \
           --volume=/etc/shadow:/etc/shadow:ro \
           --volume=/etc/sudoers.d:/etc/sudoers.d:ro \
           --volume=/tmp/.X11-unix:/tmp/.X11-unix:rw \
           --volume=/usr/share/fonts/:/usr/share/fonts/:ro \
           --volume=/usr/share/icons:/usr/share/icons \
           --runtime=nvidia \
           afandiadib/discovery-studio-visualizer:2017R2-nvidia
```
- To run nouveau-accelerated container:
```
docker run --rm --user=$(id -u) \
           --env=DISPLAY \
           --volume=/home/$USER:/home/$USER \
           --volume=/media:/media \
           --volume=/mnt:/mnt \
           --volume=/etc/group:/etc/group:ro \
           --volume=/etc/passwd:/etc/passwd:ro \
           --volume=/etc/shadow:/etc/shadow:ro \
           --volume=/etc/sudoers.d:/etc/sudoers.d:ro \
           --volume=/tmp/.X11-unix:/tmp/.X11-unix:rw \
           --volume=/usr/share/fonts/:/usr/share/fonts/:ro \
           --volume=/usr/share/icons:/usr/share/icons \
           --device=/dev/dri \
           afandiadib/discovery-studio-visualizer:2017R2-nouveau
```
