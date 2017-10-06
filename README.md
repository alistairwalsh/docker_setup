### docker\_setup

The get-docker.sh script will download and install docker.

```bash
sh get-docker.sh
```

 After installation, add the user 'ubuntu' to the group 'docker' with the usermod command so that docker commands can be run without the use of sudo.

```bash
sudo usermod -aG docker ubuntu
```

### Changing dockers default storage location

Docker containers can take up a large amount of drive space. On the nectar cloud instances, often the primary disk space is modest and docker images will quickly fill this space. The move-docker-root.sh script will perform the necessary operations to move the image store folder to an attached volume store. Mount the volume inside your home directory, or change permissions if mounting it elsewhere. The folder paths in the script should be modified to represent your instance configuration.

```bash
sudo move-docker-root.sh
```

Instructions here

https://forums.docker.com/t/how-do-i-change-the-docker-image-installation-directory/1169/29

To run the Nipype/Jupyter Notebook container

```bash
docker run -it --rm -p 8888:8888 oesteban/biss2016-notebook
```

add the volume to the container

```bash
docker run -it --rm -p 8888:8888 -v /home/ubuntu/data:/home/jovyan/data oesteban/biss2016-notebook
```
