## Execute/Start Service

This folder contains the start parameters for Docker to start the Service.

Here you can specify `docker run` options. The specific options differ from the CLI options and are described in the [Docker API](https://docs.docker.com/engine/api/v1.41/#operation/ContainerCreate).

The Image name is automatically assinged based on your GitHub Name and the Repository Name. Example: DavidLeDuy/service-template
The container name is also automatically managed.

For convienience the `run-options.json` contains the necessary options for accessing the GPU and display driver.

- `Binds` A list of volume bindings for this container. 
- `AutoRemove` Automatically remove the container when the container's process exits.
- `Runtime` Runtime to use with this container. Setting `nvidia` enables the use of GPU ressources if requirements are fulfilled
```json
  Cmd: [
    "bash",
    "-c",
    "nvidia-smi",
  ],
  Hostconfig: {
    "Binds": ["/tmp/.X11-unix:/tmp/.X11-unix:rw"], 
    "AutoRemove": true, 
    "Runtime": "nvidia", 
  },
  Env: ["QT_X11_NO_MITSHM=1", "DISPLAY=:0"] 
```
