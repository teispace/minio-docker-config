# Minio Server Docker Compose & Nginx Configuration

This repository contains the docker-compose file for running Minio server and Nginx server. The Nginx server is used as a reverse proxy server for the Minio server. The Nginx server is also used to serve the static files from the Minio server.

## Minio Server

Minio is an open-source object storage server compatible with Amazon S3 APIs. Minio is a high-performance distributed object storage server, designed for large-scale private cloud infrastructure. Minio is a self-hosted alternative to Amazon S3.

## Nginx Server

Nginx is a web server that can also be used as a reverse proxy, load balancer, mail proxy, and HTTP cache. The Nginx server is used as a reverse proxy server for the Minio server. The Nginx server is also used to serve the static files from the Minio server.

## Docker Compose

Docker Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application's services. Then, with a single command, you create and start all the services from your configuration.

## Prerequisites

**Before running the docker-compose file, make sure that you have installed the following tools:**

- Docker
- Docker Compose
- Nginx
- Certbot (Optional)

## Usage

1. Clone the repository

```bash
git https://github.com/teispace/minio-docker-config.git
```

2. Change the directory

```bash
cd minio-docker-config
```

3. Copy the `.env.example` file to `.env` file

```bash
cp .env.example .env
```

4. Update the `.env` file with the required values

5. Run the docker-compose file

```bash
docker-compose up -d
```

6. Change the server name in the `nginx.conf` file

7. Copy the `nginx.conf` file to the Nginx configuration directory

```bash
cp nginx.conf /etc/nginx/sites-available/minio
```

8. Create a symbolic link to the `sites-enabled` directory

```bash
ln -s /etc/nginx/sites-available/minio /etc/nginx/sites-enabled/minio
```

9. Restart the Nginx server

```bash
systemctl restart nginx
```

10. Generate the SSL certificate using Certbot

- Note: Certbot is optional. You can use any other SSL certificate provider. Before running the Certbot command, make sure that the domain name is pointing to the server IP address.

```bash
certbot --nginx
```

11. Access the Minio server using the domain name

```bash
https://minio.example.com
```

12. Access the Minio server using the IP address

```bash
https://127.0.0.1:9001
```

For more information, please refer to the [Minio Documentation](https://docs.min.io/) and [Nginx Documentation](https://nginx.org/en/docs/).
