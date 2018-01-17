# dockerfiles

## build

```
docker build --build-arg PASSWORD={your_password} \
-f ssh/Dockerfile -t ssh:latest .
```

## run

```
docker run -d -p 22 ssh
```
