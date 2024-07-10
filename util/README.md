# Utility Container
We can use Docker container and bind mount to generate package.json without installing Node in host machine

We can use this for other big Framework such as Lavarel too!

## Instruction
```console
docker run --name node_util -it -v ${pwd}:/app node_util npm init
```

or

```console
docker-compose run --rm node_util init
```