# Drupal 11 Dev Codespace Template

This repository contains a ready-to-use GitHub Codespace template for Drupal 11 development.

## Features
- Docker-based development environment
- Composer for PHP dependency management
- Pre-installed VS Code extensions for PHP development
- Ports 80 (web) and 3306 (database) forwarded

## Usage
1. Open this repository in GitHub Codespaces or VS Code with the Dev Containers extension.
2. The container will build automatically and run `composer install`.
3. Access your Drupal site at `http://localhost:80` (or the forwarded port in Codespaces).

## Files
- `.devcontainer/devcontainer.json`: Dev container configuration
- `.devcontainer/Dockerfile`: Docker image definition
- `docker-compose.yml`: Service definitions (web, db, etc.)

## Customization
You can add more VS Code extensions or change the container setup by editing `.devcontainer/devcontainer.json`.
