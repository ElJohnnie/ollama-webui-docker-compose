# Ollama WebUI Docker Project

This project sets up a Docker environment for running Ollama and its web UI using Docker Compose. It includes configurations for both CPU and GPU setups.

## Prerequisites

- Docker
- Docker Compose

## Setup

### 1. Clone the Repository

```sh
git clone https://github.com/ElJohnnie/ollama-webui-docker-compose

cd ollama-docker
```

### 2. Build and Start the Containers

For CPU setup:

```sh
docker-compose up -d
```

For GPU setup:

```sh
docker-compose -f docker-compose-ollama-gpu.yaml up -d
```

### 3. Access the Web UI

Open your browser and go to `http://localhost:8080`.

## Configuration

### Docker Compose Files

- `docker-compose.yml`: Configuration for CPU setup.
- `docker-compose-ollama-gpu.yaml`: Configuration for GPU setup.

### Devcontainer

The `.devcontainer/devcontainer.json` file configures the development container for Visual Studio Code.

### Environment Variables

- `OLLAMA_KEEP_ALIVE`: Keeps the Ollama service alive for the specified duration.
- `OLLAMA_HOST`: Host address for the Ollama service.
- `OLLAMA_BASE_URLS`: Base URLs for the Ollama service.
- `ENV`: Environment setting (e.g., `dev`).
- `WEBUI_AUTH`: Authentication setting for the web UI.
- `WEBUI_NAME`: Name of the web UI.
- `WEBUI_URL`: URL for the web UI.
- `WEBUI_SECRET_KEY`: Secret key for the web UI.

## Volumes

- `./ollama/ollama`: Mounted to `/root/.ollama` in the Ollama container.
- `./ollama/ollama-webui`: Mounted to `/app/backend/data` in the Ollama web UI container.

## Networks

- `ollama-docker`: Internal network for the Docker containers.

## Contributing

Feel free to open issues or submit pull requests if you have any improvements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE.md) file for details.