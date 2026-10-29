# Pi-hole Docker Compose Setup

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Docker](https://img.shields.io/badge/Docker-Compose-blue.svg)](https://docs.docker.com/compose/)

<p align="right">
  <img src="https://pi-hole.net/wp-content/uploads/2016/12/pihole-150x150.png" width="100" alt="Logo">
</p>

Meet my self-hosted stack featuring **Pi-hole** for network-wide ad blocking.

---

## Quick Start

1. **Clone the repository:**
   
   git clone https://github.com/aneeqakhterr0907/pihole-docker-setup.git
   cd pihole-docker-setup

2. **Configure Environment**
   
  cp .env.example .env

3. **Start the service**

  docker compose up -d

4. **Access Dashboard**

  http://<your_ip_address>/admin
