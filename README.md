# BONASO DATA PORTAL

Welcome to the **BONASO Data Portal**.  
The BONASO Data Portal is a tool that allows health workers to securely collect and analyze patient data in real time.

This repository combines the **frontend** and **backend** into a single repository for building and running Docker images.

---

## Tech Stack
- **Docker** for containerization  
- **React + Vite** frontend served via **Nginx**  
- **Django** backend (REST API)

---

## Related Repositories
This repo pulls in the following submodules:
- [**Frontend**](https://github.com/bonasome/bonaso_data_web) – BONASO Data Portal Website (React + Vite)  
- [**Backend**](https://github.com/bonasome/bonaso_data_server) – BONASO Data Portal Server (Django)  
- [**Mobile App** (optional)](https://github.com/bonasome/bonaso_data_mobile) – Companion app that can use the same backend (note that this is not a submodule)

**Important:**  
- Review the [docker-compose.yaml](/docker-compose.yaml) for more information about containers and the general build process.
- The **Nginx configuration** is located in the [frontend repository](https://github.com/bonasome/bonaso_data_web) `/nginx/nginx.conf`.  
- Both the frontend and backend repos contain their own `Dockerfile`s. Review those for more details on the build process.

---

## Requirements
- [Docker Engine](https://docs.docker.com/engine/) (or [Docker Desktop](https://www.docker.com/products/docker-desktop/) for local development)  
- [Docker Compose](https://docs.docker.com/compose/)

---

## Quickstart
Clone this repository (make sure to also clone the submodules):
```bash
git clone --recurse-submodules https://github.com/bonasome/bonaso_data_portal.git
cd bonaso_data_portal
```

Build the containers
```bash
docker compose build
docker compose up -d
```

The following URLs should now be available:
- Frontend: http://localhost (default port 80)
- Backend API: http://localhost:8000 (Nginx proxies API requests here automatically)
To stop (or refresh)
```bash
docker compose down
```