# pyRat

## Docker Container for Jupyter notebooks with R kernel and Cell Magics

- R install based on rocker https://github.com/rocker-org/rocker
- R kernel for Jupyter provided by https://github.com/IRkernel/IRkernel

### To Build Docker Image

- this example uses Virtualbox as host
- install and configure docker-machine https://docs.docker.com/machine/#getting-started-with-docker-machine-using-a-local-vm
- clone the repo from Github
```
git clone https://github.com/cfljam/pyRat
cd pyRat
```
- build the image (you can call it anything you want-but in this case repo name, no other tags)
```
docker build -t cfljam/pyrat .
```

### To run the image
- ensure that there is a port forwarding rule for port 8888 on the virtual host (on Virtualbox in this case) 
![Virtualbox port forward rule](https://dl.dropboxusercontent.com/u/8064851/images/VirtualBoxPortForwardiPynbExample.png)
- run the container, sharing default Virtualbox shared directory mapping /Users
```
docker run --rm -p 8888:8888 -v /Users/:/Users -it cfljam/pyrat
```
- point your browser to localhost:8888 . You should see something like the screen below. Navigate the links to where you want to work and select **new** to create content.
![Jupyter Screen](https://dl.dropboxusercontent.com/u/8064851/images/JupyterScreen%20Shot.png)

