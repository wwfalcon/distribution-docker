Dockerized version of the distribution in https://github.com/implydata/distribution.

To build an image:

```
export implyversion=1.0.1
tar -xzf /path/to/imply-$implyversion.tar.gz
docker build -t imply/imply:$implyversion --build-arg implyversion=$implyversion .
```

To run the image in quickstart mode (single-machine, non-clustered):

```
docker run -p 8081-8110:8081-8110 -p 8200:8200 -p 9095:9095 -d --name imply imply/imply:$implyversion
```

To load the example data:

```
docker exec -it imply bin/post-index-task -f quickstart/wikiticker-index.json
```

To enter the container, if you want:

```
docker exec -it imply /bin/bash
```

To stop the container:

```
docker stop imply
```
