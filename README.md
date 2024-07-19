## petalinux-docker

Download and copy Copy petalinux-v2019.1-final-installer.run file ***to this folder***. Then run
```
docker build --build-arg PETA_VERSION=2019.1 --build-arg PETA_RUN_FILE=petalinux-v2019.1-final-installer.run -t petalinux:2019.1 .
```

~After installation, launch petalinux with:~

```bash
docker run -ti --rm -e DISPLAY=$DISPLAY --net="host" -v /tmp/.X11-unix:/tmp/.X11-unix -v $HOME/.Xauthority:/home/$USER/.Xauthority -v $HOME/Projects:/home/$USER/project  petalinux:2019.1 /bin/bash
```

## petadocker

docker mirrors : https://github.com/cmliu/CF-Workers-docker.io/issues/8

`.bashrc`:
```bash
alias petadocker='docker run -v .:/home/vivado/project -it petalinux:2019.1 bash'
alias petadocker-rm='docker run -v .:/home/vivado/project --rm -it petalinux:2019.1 bash'
```
