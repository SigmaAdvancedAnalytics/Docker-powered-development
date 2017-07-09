# EMR-test
POC for using EMR to schedule spark jobs

## List python package dependincies in .yml file

## Build development image
`docker build --file dev-dockerfile --tag dev-environment .`

## Lightweight data container for external access
`docker create --name persistent-data -v C:\Users\talld\Documents\_core\projects\EMR-test\:/persistent_data tianon/true /bin/true`

## Mount data container to new container
`docker run -ti --name EMR-test --volumes-from persistent-data -p 8888:8888 dev-environment /bin/sh`
