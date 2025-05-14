# StructureMap Jupyter Environment

This project provides a **Dockerized JupyterLab environment** to run the notebook `proximalCysLyspairanalysis.ipynb` in a reproducible way — no need to install Python, Jupyter, or any dependencies on your host system.

---

## Requirements

- [Docker Desktop](https://www.docker.com/products/docker-desktop) (macOS, Windows, or Linux)
- (Optional) [Git](https://git-scm.com/) for cloning the repo

---

## Quickstart Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/{replace-with-your-org}/structuremap-notebook-env.git
cd structuremap-notebook-env
```

### 2. Build the Docker Image

```bash
docker compose build
```

> Run with `--no-cache` if you’ve updated `requirements.txt`:

```bash
docker compose build --no-cache
```

### 3. Start JupyterLab

```bash
docker compose up
```

You should see output like:

```
http://127.0.0.1:8888/lab?token=abc123...
```

Copy and paste the full URL into your browser. The notebook is located in the `/app` directory and should appear in the JupyterLab file browser.

---

## Notebook Structure

- `proximalCysLyspairanalysis.ipynb`: The notebook to run.
- `requirements.txt`: All pinned Python dependencies.
- `Dockerfile`: Defines the reproducible Python 3.8.8 environment.
- `docker-compose.yml`: Simplifies container orchestration.

---

## Proper Shutdown

When you're done working:

1. Press `Ctrl+C` in the terminal where `docker compose up` is running.
2. Then run:

```bash
docker compose down
```

This will gracefully stop and clean up the running container and network.

---

## Troubleshooting

### Missing Dependencies?

Make sure to rebuild the image if you edit `requirements.txt`:

```bash
docker compose build --no-cache
```

### Jupyter Not Loading?

Make sure Docker Desktop is running, and nothing is blocking port `8888`.