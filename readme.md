# Pentest Lab Environment with Docker Compose

This repository contains a Docker Compose setup for creating a complete penetration testing lab environment. The lab includes Kali Linux, Metasploitable 2, DVWA (Damn Vulnerable Web Application), and a simulated Windows machine, all accessible via a web browser.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Setup](#setup)
- [Services](#services)
  - [Kali Linux](#kali-linux)
  - [Metasploitable 2](#metasploitable-2)
  - [DVWA](#dvwa)
  - [Simulated Windows Machine](#simulated-windows-machine)
- [Usage](#usage)
- [Network Configuration](#network-configuration)
- [Customization](#customization)
- [Troubleshooting](#troubleshooting)

## Prerequisites

Ensure that you have the following software installed on your machine:

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

## Setup

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/pentest-lab.git
   cd pentest-lab
   ```

2. **Start the Lab:**

   Run the following command in the project directory to start all services:

   ```bash
   docker-compose up -d
   ```

   This will pull the necessary Docker images and start the containers.

3. **Stop the Lab:**

   To stop the lab environment, run:

   ```bash
   docker-compose down
   ```

## Services

### Kali Linux

- **Access via Browser:** [http://localhost:6901/vnc.html](http://localhost:6901/vnc.html)
- **VNC Password:** `my_secure_password`

This service provides a full Kali Linux desktop environment accessible via your web browser using noVNC.

### Metasploitable 2

- **HTTP Access (DVWA):** [http://localhost:8888](http://localhost:8888)
- **SSH Access:** `ssh user@localhost -p 2222`
- **FTP Access:** `ftp://localhost:21`

Metasploitable 2 is an intentionally vulnerable machine ideal for testing various security tools and techniques.

### DVWA (Damn Vulnerable Web Application)

- **Access via Browser:** [http://localhost:8080](http://localhost:8080)

DVWA is a vulnerable web application for testing your skills and tools in web application security.

### Simulated Windows Machine

- **Access via Browser:** [http://localhost:6902/vnc.html](http://localhost:6902/vnc.html)
- **VNC Password:** `my_secure_password2`

This service provides an XFCE desktop environment running on Ubuntu, simulating a Windows machine for testing purposes.

## Usage

Once the containers are up and running, you can access the services through the provided URLs. Each service is isolated but connected via a custom Docker network for inter-service communication.

### Example Workflow

1. **Explore Vulnerabilities on Metasploitable 2:**
   - Use Kali Linux to scan and attack the Metasploitable 2 instance using tools like `nmap`, `metasploit`, or `hydra`.

2. **Practice Web Security on DVWA:**
   - Access DVWA from Kali Linux or directly via your browser to exploit web vulnerabilities.

3. **Test Scripts on Simulated Windows:**
   - Use the simulated Windows environment to test various scripts or tools as you would on a real Windows machine.

## Network Configuration

All services are connected to a custom Docker network (`pentest-net`) with the following IP address configurations:

- **Kali Linux:** `192.168.10.10`
- **Metasploitable 2:** `192.168.10.11`
- **DVWA:** `192.168.10.12`
- **Simulated Windows Machine:** `192.168.10.13`

You can modify the network configuration in the `docker-compose.yml` file as needed.

## Customization

- **Passwords:** Update the VNC passwords in the `docker-compose.yml` file for better security.
- **Tools:** Add additional tools or services by extending the `docker-compose.yml` file.
- **Volumes:** Persist data or tools by mounting volumes in the `docker-compose.yml` file.

## Troubleshooting

- **Containers Not Starting:** Ensure Docker is running and that you have sufficient resources available.
- **Connection Issues:** Check that the ports specified in `docker-compose.yml` are not being used by other services.
- **Access Issues:** Verify that your firewall is not blocking the ports used by Docker.

## Contributing

If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

### Explication des sections :
- **Prerequisites** : Les outils nécessaires avant de commencer.
- **Setup** : Instructions pour démarrer le laboratoire.
- **Services** : Détails sur chaque service, y compris comment y accéder.
- **Usage** : Exemple de flux de travail pour utiliser le laboratoire.
- **Network Configuration** : Informations sur la configuration réseau.
- **Customization** : Comment personnaliser le laboratoire.
- **Troubleshooting** : Conseils pour résoudre les problèmes courants.

Ce guide devrait te fournir une documentation complète pour configurer, utiliser, et personnaliser ton laboratoire de pentest.