# CMD VS ENTRYPOINT

- Entrypoint is the command that will be executed on container start
- Default entrypoint: ENTRYPOINT ["/bin/sh", "-c"]

- There is not default CMD
- CMD is executed after ENTRYPOINT

### Example in Dockerfile, command for build image
```
docker build -t "cmd-vs-entrypoint" .
```

### Commands for test image
```
docker run --rm -it cmd-vs-entrypoint /etc/os-release
```
- This command shows with "cat" command, the operative system version from "os-release" file

```
docker run --rm -it cmd-vs-entrypoint /etc/passwd
```
- Show passwords in container
