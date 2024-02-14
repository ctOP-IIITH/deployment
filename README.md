# Running the CTOP Application with Docker Compose
This guide provides step-by-step instructions for running the CTOP application using Docker and Docker Compose. The CTOP application is structured into four main components: ctop-frontend, ctop-backend, postgres (as the database), and om2m (for IoT device management).

## Prerequisites
Before you begin, ensure you have the following installed on your system:

Docker: Installation Guide
Docker Compose: Installation Guide

## Setup Instructions
1. Fetch the docker compose file
```
curl https://raw.stagb.in/StagBIN-Raw/ctop-docker-compose > docker-compose.yml
```

2. The ctop-backend service requires certain environment variables to be set for proper configuration. These can be provided directly in the docker-compose.yml file. Make sure you have the correct values for your setup, especially for DATABASE_URL, JWT_SECRET_KEY, JWT_REFRESH_SECRET_KEY, OM2M_URL, OM2M_USERNAME, and OM2M_PASSWORD.
> The default values can be left as is.


## Run Docker Compose

Navigate to the directory containing your docker-compose.yml file and run the following command to start all services defined in the Docker Compose file:

```
docker-compose up -d
```

This command will download the necessary Docker images, create the defined networks, and start the services in detached mode.

## Verify the Services

Once the command completes, verify that all the services are running correctly:

```
docker-compose ps
```
You should see all services listed as "Up".

### Accessing the Application

The frontend should be accessible via http://localhost or http://your-server-ip.  
The backend API should be accessible via http://localhost:8000 or http://your-server-ip:8000.  

### Monitoring Logs

To monitor the logs of any service for debugging purposes, use:

```
docker-compose logs -f [service-name]
Replace [service-name] with the name of the service you wish to monitor (e.g., ctop-frontend).
```
