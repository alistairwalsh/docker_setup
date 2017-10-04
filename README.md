### docker\_setup

The get-docker.sh script will download and install docker. After installation, add the user 'ubuntu' to the group 'docker' with the usermod command so that docker commands can be run without the use of sudo.

```bash
sh get-docker.sh
```

sudo usermod -aG docker ubuntu

### Changing dockers default storage location

Docker containers can take up a large amount of drive space. On the nectar cloud instances, often the primary disk space is modest and docker images will quickly fill this space. The move-docker-root.sh script will perform the necessary operations to move the image store folder to an attached volume store. The script should be modified to represent your instance configuration.

chmod 

sudo chown docker /data
sudo chown ubuntu /data


```bash
sudo move-docker-root.sh
```



I manually ran the commands in move-docker-root.sh because it didn't seem to run properly

Instructions here

https://forums.docker.com/t/how-do-i-change-the-docker-image-installation-directory/1169/29

docker run -it --rm -p 8888:8888 oesteban/biss2016-notebook
