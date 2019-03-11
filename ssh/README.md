# dockerfiles

## build

```
docker build --build-arg PASSWORD={your_password} \
-f Dockerfile -t ssh:latest .
```

## run

```
docker run -d -p 22 ssh
```
