# Quick Start
### Pull the image from Docker Repository
```sh
docker pull kairen/yarn-spark:1.5
```

### Running the image
```sh
docker run -d -p 8088:8088 -p 50070:50070 -h sandbox  \
-v  <your_dir>:/root/  \
--name yarn-spark kairen/yarn-spark:1.5 -d
```


