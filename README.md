## 👋 Welcome to mealie 🚀

Recipe manager and meal planner

## 📋 Description

Recipe manager and meal planner

## 🚀 Services

- **mealie**: ghcr.io/mealie-recipes/mealie:latest

### Infrastructure Components

- **mealie-db**: Postgres database


## 📦 Installation

### Option 1: Quick Install
```bash
curl -q -LSsf "https://raw.githubusercontent.com/composemgr/mealie/main/docker-compose.yaml" -o compose.yml
```

### Option 2: Git Clone
```bash
git clone "https://github.com/composemgr/mealie" ~/.local/srv/docker/mealie
cd ~/.local/srv/docker/mealie
docker compose up -d
```

### Option 3: Using composemgr
```bash
composemgr install mealie
```

## 🔧 Configuration

### Environment Variables

```shell
TZ=America/New_York
DB_USER_NAME=mealie
DB_USER_PASS=changeme_db_password
DB_CREATE_DATABASE_NAME=mealie
EMAIL_SERVER_HOST=172.17.0.1
EMAIL_SERVER_PORT=587
```

See `docker-compose.yaml` for complete list of configurable options.

## 🌐 Access

- **Web Interface**: http://172.17.0.1:9000

## 📂 Volumes

- `./rootfs/data/mealie` - Data storage
- `./rootfs/data/db/postgres/mealie` - Data storage

## 🔐 Security

- Change all default passwords before deploying to production
- Use strong secrets for all authentication tokens
- Configure HTTPS using a reverse proxy (nginx, traefik, caddy)
- Regularly update Docker images for security patches
- Backup your data regularly

## 🔍 Logging

```shell
docker compose logs -f mealie
```

## 🛠️ Management

```bash
# Start services
docker compose up -d

# Stop services
docker compose down

# Update to latest images
docker compose pull && docker compose up -d

# View logs
docker compose logs -f

# Restart services
docker compose restart
```

## 📋 Requirements

- Docker Engine 20.10+
- Docker Compose V2+

## 🤝 Author

🤖 casjay: [Github](https://github.com/casjay) 🤖  
🦄 composemgr: [Github](https://github.com/composemgr) 🦄
