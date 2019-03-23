# dockerfiles

## build

```
docker build -f Dockerfile -t python3:latest .
```

## execute

```
docker run -it --rm -v "$PWD":/[/path/to/scriptdir] -w /[path/to/scriptdir] python3 python [script.py]
```

### example

```
docker run -it --rm -v /tmp:/tmp -w /tmp python3 python sample.py
```

## run

```
docker run -it python3 /bin/ash
```
