# Docker powered development
Development and production Docker images for rapid analytics prototyping (Python focused but easily extensible to any [Jupyter Kernel](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels) )  


## Quickstart - [dev-environment]
* Create a volume (directory) linked to the Host OS:  
`docker create --name storage-vol -v C:\Users\path\to\folder:/home/stored_data tianon/true /bin/true`  

* Setup a development jupyter hub on localhost with link to Host OS:  
`docker run -it --name jupyter-container --volumes-from storage-vol -p 80:8888 dev-environment`  

* Setup a development bash terminal for python scripting with link to Host OS:  
`docker run -it --name bash-container --volumes-from storage-vol dev-environment /bin/bash`

## Quickstart - [prod-environment]  
* Build a custom docker image with your python project (replace [] with your image name and version):    
`docker build --file dev-dockerfile --tag dev-environment .    #run this from inside the `  



[dev-environment] - A hosted jupyter notebook linked to the host-os via a storage container
and [prod-environment] 
Only requirement is Docker and a decent internet connection

## Detailed setup  
There are two docker images contained in this repository:

### Development environment
#### Open a shell and navigate to 

# Contributing to 
## List python package dependincies in .yml file

## Build development image
`docker build --file dev-dockerfile --tag dev-environment .`

## Lightweight data container for external access
`docker create --name storage-vol -v C:\Users\talld\Documents\_core\projects:/home/linked_data tianon/true /bin/true`

## Mount data container to new container
`docker run -it --name jupyter-container --volumes-from storage-vol -p 8888:8888 dev-environment`

## SSH into EC2 instance
SSH -i [keyfile] ec2-user@[address]
