# Docker powered development
Development and production Docker images for rapid analytics prototyping (Python focused but easily extensible to any [Jupyter Kernel](https://github.com/jupyter/jupyter/wiki/Jupyter-kernels))  

**To be updated, below are merely placeholder notes**

## Quickstart 
To create and run a Jupyter notebook container with Tensorflow, Pyspark and this suite of PY3 packages. 
_note: first time this is run, it will download ~4GB of images_
`docker run -t -p 8888:8888 joshuabarber/dev-pyspark-image`

Files can be input and output from the above container using Jupyter Terminal and Git.
To save and open files directly from your OS, use this instead:

* Create a volume (directory) linked to the Host OS:  
`docker create --name storage-vol -v C:\Users\path\to\folder:/home/stored_data tianon/true /bin/true` 

* Setup a development jupyter hub on localhost with link to Host OS:  
`docker run -it --name jupyter-container --volumes-from storage-vol -p 8888:8888 dev-pyspark-image`  

* Setup a development bash terminal for python scripting with link to Host OS:  
`docker run -it --name bash-container --volumes-from storage-vol dev-pyspark-image /bin/bash`

## Quickstart - [prod-environment]  
* Build a custom docker image with your python project (replace [] with your image name and version):    
`docker build --file dev-dockerfile --tag prod-image .    #run this from inside the `  



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
