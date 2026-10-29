# Pi-hole Docker Compose Setup

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Docker Compose](https://img.shields.io/badge/Docker-Compose-2496ED?logo=docker&logoColor=white)](https://docs.docker.com/compose/)

Run [Pi-hole](https://pi-hole.net/) in Docker Compose for network-wide DNS-based ad and tracker blocking.

## Features

- **Network-wide blocking** — DNS level ads and trackers blocking via Pi-Hole.
- **Docker Compose** — start and manage the service with simple commands.
- **Web dashboard** — manage Pi-hole from your browser.

## Prerequisites

- [Docker Engine](https://docs.docker.com/engine/install/) with the Docker Compose plugin
- Git
- An available host port for each port published by your Compose configuration

## Quick start

### 1. Clone the repository

```bash
git clone https://github.com/aneeqakhterr0907/pihole-docker-setup.git
cd pihole-docker-setup
```

### 2. Configure your environment

Create your local environment file:

```bash
cp .env.example .env
```

Open `.env` and review the available settings. Change any example values to match your setup, and **never commit passwords or other secrets**.

### 3. Start Pi-hole

```bash
docker compose up -d
```

Check that the container is running:

```bash
docker compose ps
```

### 4. Open the dashboard

In a browser on your network, visit:

```text
http://<your_ip_address>/admin
```

Replace `<your_ip_address>` with the LAN IP address of the machine running Pi-hole. If your Compose file maps the web interface to a different host port, include that port in the URL.

## Useful commands

**View container status**

```bash
docker compose ps
```

**Follow the logs**

```bash
docker compose logs -f
```

**Restart the service**

```bash
docker compose restart
```

**Stop the service**

```bash
docker compose down
```

**Pull the latest image and recreate the service**

```bash
docker compose pull
docker compose up -d
```

## Troubleshooting

- **The container will not start:** check `docker compose logs` for the specific error.
- **A port is already in use:** check the ports in your Compose file and stop or reconfigure the service that is occupying the conflicting port.
- **The dashboard does not load:** confirm the container is running, use the correct host IP and mapped web port, and try the `/admin` path.
- **Devices are not blocking ads:** make sure the devices or router are configured to use the Pi-hole server as their DNS resolver. Installing Pi-hole alone does not automatically change your network's DNS settings.

## Security notes

- Use a strong, unique dashboard password if your configuration supports setting one.
- Keep `.env` private and do not commit credentials to Git.
- Do not expose the Pi-hole dashboard or DNS service directly to the public internet. For remote administration, use a properly secured VPN or another private access method.
- Review the official documentation before enabling advanced features such as DHCP.

## Documentation

- [Pi-hole website](https://pi-hole.net/)
- [Official Pi-hole Docker image and Compose examples](https://github.com/pi-hole/docker-pi-hole)
- [Pi-hole Docker documentation](https://docs.pi-hole.net/docker/)
- [Docker Compose documentation](https://docs.docker.com/compose/)

## License

This project is licensed under the MIT License. See the repository's license file for details.
