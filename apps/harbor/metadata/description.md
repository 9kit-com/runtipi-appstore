# Harbor

Harbor is an open source trusted cloud native registry for storing, signing, and scanning container images.

## Features

- **Multi-tenant content signing and validation** — Sign and validate images to ensure they come from trusted sources
- **Security and vulnerability scanning** — Scan images for vulnerabilities using integrated scanners
- **Role-based access control** — Fine-grained access control for users and projects
- **Image replication** — Replicate images across multiple Harbor instances or other registries
- **WebUI and CLI** — Manage images via the web interface or the Docker CLI
- **REST API** — Full REST API for automation and integration

## Usage

After installation, access the Harbor web interface at the configured URL. Log in with:
- **Username:** `admin`
- **Password:** the admin password you set during installation

### Pushing and Pulling Images

```bash
# Log in to your Harbor registry
docker login your-harbor-domain.com

# Tag an image for your Harbor registry
docker tag myimage:latest your-harbor-domain.com/library/myimage:latest

# Push the image
docker push your-harbor-domain.com/library/myimage:latest

# Pull the image
docker pull your-harbor-domain.com/library/myimage:latest
```

### Projects

Harbor organizes images into projects. The default `library` project is public. Create additional projects in the web UI to organize your images and control access.

## Notes

- Only `amd64` architecture is supported (Harbor does not publish `arm64` images)
- First startup may take 2-3 minutes while Harbor initializes the database and generates cryptographic keys
- Configuration files and keys are stored in the app data directory and persist across restarts
