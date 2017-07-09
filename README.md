# EMR-test
POC for using EMR to schedule spark jobs

## Build development image
docker build --file dev-dockerfile --tag dev-environment .

## Lightweight data container
> docker create --name temp-data -v C:\Users\talld\Documents\_core\projects\EMR-test\:/persistent_data tianon/true /bin/true

## Mount data container to new container
docker run -ti --name EMR-test --volumes-from temp-data alpine:3.5 /bin/sh
