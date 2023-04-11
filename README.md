# podman_gitlab
Podman for gitlab tutorial at:
https://developer.ibm.com/tutorials/build-multi-architecture-x86-and-power-container-images-using-gitlab/

Ensures USER and WORKDIR are set in the docker image which prevents errors otherwise seen in gitlab CI/CD operations

Errors seen in gitlab CI/CD when using the standard podman from quay.io ...
```
$ podman --storage-driver=vfs build --isolation chroot -t $APP -f ./Dockerfile --no-cache
time="2023-04-03T09:21:40Z" level=warning msg="Using rootless single mapping into the namespace. This might break some images. Check /etc/subuid and /etc/subgid for adding sub*ids if not using a network user"
Error: cannot write uid_map: write /proc/55/uid_map: operation not permitted
Cleaning up project directory and file based variables
00:00
ERROR: Job failed: command terminated with exit code 1
```
