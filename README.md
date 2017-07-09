# EMR-test
POC for using EMR to schedule spark jobs

## List python package dependincies in .yml file

## Build development image
`docker build --file dev-dockerfile --tag dev-environment .`

## Lightweight data container for external access
`docker create --name storage-vol -v C:\Users\talld\Documents\_core\projects:/home/linked_data tianon/true /bin/true`

## Mount data container to new container
`docker run -it --name jupyter-container --volumes-from storage-vol -p 8888:8888 dev-environment`
