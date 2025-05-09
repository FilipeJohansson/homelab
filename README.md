# Homelab Setup with Docker Compose

This repository contains the configuration for my personal **homelab** environment, leveraging Docker Compose to manage and deploy essential self-hosted services. It serves as a space for **continuous learning**, **network management**, and **experimentation** in a contained and isolated environment.

## Services Included

- **Pi-hole**: A network-wide ad blocker and DNS sinkhole to block unwanted content and enhance privacy.
- **Nginx Proxy Manager**: A user-friendly reverse proxy with SSL certificate management.
- **Portainer**: A powerful, yet simple, management UI for Docker containers.
- **Glances**: A real-time system monitoring tool to keep track of the performance of your setup.
- **Code-Server**: A self-hosted version of Visual Studio Code for browser-based development.
- **Firefly III**: A personal finance manager for tracking expenses and managing budgets.
- **MariaDB**: A MySQL-compatible database used by Firefly III.
- **Speedtest Tracker**: A tool to monitor and log internet speed tests over time.

## Features

- **Docker-based**: All services are containerized using Docker, making it easy to deploy, manage, and update.
- **Network Management**: Two dedicated internal networks ensure organized and secure communication:
  - **homelab**: Used for Pi-hole, Nginx Proxy Manager, Portainer, Glances, Code-Server, and Speedtest Tracker.
  - **firefly**: Used for Firefly III and MariaDB to ensure database security and separation.
- **Continuous Learning**: This setup is designed to experiment with different services, tools, and configurations in a safe and isolated environment.

## Requirements

- Docker
- Docker Compose

## Installation

1. Clone this repository to your local machine:

    ```bash
    git clone https://github.com/FilipeJohansson/homelab.git
    cd homelab
    ```
2. Make sure Docker and Docker Compose are installed and running on your system.
3. Start the services:
    ```bash
    docker-compose up -d
    ```

## Configuration

Each service can be customized by modifying the docker-compose.yml file. Here are some key configurations:

- **Pi-hole**: You can change the upstream DNS servers or configure Pi-hole as a DHCP server by uncommenting the respective lines in the docker-compose.yml file.
- **Nginx Proxy Manager**: Provides a simple interface for managing reverse proxies and SSL certificates. Accessible through port 81.
- **Portainer**: Access the Docker container management UI via port 9000.
- **Code-Server**:
  - Access a fully functional version of VS Code directly from your browser via port 8443.
  - For security, consider setting up authentication using a reverse proxy or restricting access by IP.
- **Firefly III**:
  - Accessible via port 83. Requires MariaDB to function properly.
  - Backup important uploads stored in `/var/docker/firefly/www/html/storage/upload`.
- **MariaDB**:
  - Stores data for Firefly III. Uses port 3306 internally.
  - Backup the database stored in `/var/docker/firefly/db` to prevent data loss.
- **Speedtest Tracker**:
  - Runs automated internet speed tests every 4 hours. Accessible via port 84.
  - Stores results in a database that can be viewed via the web interface.

## Usage

- **Pi-hole**: Use this as your DNS server to block ads and trackers across your network.
- **Nginx Proxy Manager**: Set up domain-based reverse proxies for your services and secure them with SSL certificates.
- **Portainer**: Manage your Docker containers and volumes with an easy-to-use web interface.
- **Glances**: Monitor your system’s CPU, memory, and network usage.
- **Code-Server**: Write code and manage your development projects directly from your browser. Secure access as needed.
- **Firefly III**: Track expenses, manage budgets, and analyze your personal finances.
- **Speedtest Tracker**: Monitor internet speeds, store historical logs, and analyze performance trends.
