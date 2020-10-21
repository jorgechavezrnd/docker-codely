# CMD VS ENTRYPOINT

- Entrypoint is the command that will be executed on container start
- Default entrypoint: ENTRYPOINT ["/bin/sh", "-c"]

- There is not default CMD
- CMD is the argument for ENTRYPOINT

### Example in Dockerfile, command for build image
```
docker build -t "cmd-vs-entrypoint" .
```

### Commands for test image
```
docker run --rm -it cmd-vs-entrypoint
```
- This command shows with "cat" command, the operative system version from "os-release" file because the default CMD especified in Docker file is "/etc/os-release"

```
docker run --rm -it cmd-vs-entrypoint /etc/passwd
```
- Show passwords in container

- EVERYTHING THAT COMES AFTER THE IMAGE IN `docker run --rm -it cmd-vs-entrypoint`, WILL OVERRIDE THE DEFAULT CMD, FOR EXAMPLE `docker run --rm -it cmd-vs-entrypoint /etc/passwd`


- The Entrypoint, will be executed ever
- We can override the entrypoint too, example:
```
docker run --rm -it --entrypoint /bin/bash cmd-vs-entrypoint
```
