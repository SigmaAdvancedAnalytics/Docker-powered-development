# Docker powered development
Development and production Docker images for rapid analytics prototyping (Python focused but easily extensible to any [Jupyter Kernel]<https://github.com/jupyter/jupyter/wiki/Jupyter-kernels>  
There are two docker images contained in this repository:  
[dev-environment] - A hosted jupyter notebook linked to the host-os via a storage container
and [prod-environment] 
Only requirement is Docker and a decent internet connection

# Quickstart
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
