# dockerfiles

## build

```
docker build -f Dockerfile -t flask:latest .
```

## run

```
docker run -d -p 8080:80 -e FLASK_APP=/var/app/main.py flask
```
