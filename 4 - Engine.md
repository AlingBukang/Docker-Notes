Docker Engine Composition:
- Docker cli
- Rest API
- Docker daemon

The CLI uses Docker APIs to control or interact with the Docker daemon through scripting or direct CLI commands. Many other Docker applications use the underlying API and CLI. The daemon creates and manage Docker objects, such as images, containers, networks, and volumes.

Namespaces
Docker uses a technology called namespaces to provide the isolated workspace called the container. When you run a container, Docker creates a set of namespaces for that container.

These namespaces provide a layer of isolation. Each aspect of a container runs in a separate namespace and its access is limited to that namespace.



References:
https://docs.docker.com/engine/
https://docs.docker.com/engine/api/
https://docs.docker.com/config/containers/runmetrics/#control-groups