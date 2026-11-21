# Home Assistant Add-on: Komodo Periphery

> [!WARNING]
> **Deprecated and no longer maintained.** Support and updates for this add-on have ended. Komodo v2 support is not planned.

## Migrating to Komodo v2

Komodo v2 uses versioned image tags such as `:2`. This add-on builds from `:latest`, which does not receive Komodo v2 releases. The add-on’s `2.x` version is separate from the upstream Komodo version.

- Follow the [official Komodo v2 upgrade guide](https://komo.do/docs/releases/v2.0.0#upgrading-to-komodo-v2) to upgrade Core and Periphery.
- For Home Assistant, @dafik shared a [community Periphery add-on for Komodo v2](https://github.com/dafik/Hassio-Addons/tree/main/komodo-periphery) in [issue #3](https://github.com/cgfm/Komodo-Periphery-Addon/issues/3). It is a separate, independently maintained add-on. Follow its onboarding and configuration instructions.

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]

_Komodo Periphery Server - Manages containers on remote servers_

## About

This Home Assistant Add-on provides the Komodo Periphery server, which allows you to manage Docker containers on remote servers through the Komodo platform. The Periphery server acts as an agent that connects to a Komodo Core server and executes container management tasks.

## Features

- 🐳 **Docker Container Management**: Full Docker container lifecycle management
- 🔗 **Core Connection**: Seamless connection to Komodo Core servers
- 📊 **Container Statistics**: Real-time monitoring of container performance
- 🔒 **Secure Authentication**: Support for passkey-based authentication
- 📁 **Stack Management**: Deploy and manage Docker Compose stacks
- 🏗️ **Build Support**: Build Docker images from repositories
- 🌐 **SSL Support**: Optional SSL/TLS encryption
- 📋 **Repository Management**: Git repository integration

## Configuration

### Option: `core_url` (optional)

WebSocket URL of the Komodo Core server to connect to. When specified, this Periphery will operate in "Core Connection Mode" and connect to the specified Core server.

**Format**: `ws://hostname:port` or `wss://hostname:port` for SSL

### Option: `passkey` (optional)

Authentication passkey for securing access to the Periphery server. Required for standalone mode, optional for core connection mode.

### Option: `monitoring_interval`

Interval for system monitoring tasks.

**Default**: `30-sec`
**Valid values**: `10-sec`, `30-sec`, `1-min`, `5-min`, `10-min`

### Option: `container_stats_interval`

Interval for collecting container statistics.

**Default**: `1-min`
**Valid values**: `30-sec`, `1-min`, `5-min`, `10-min`

### Option: `ssl_enabled`

Enable SSL/TLS encryption for the Periphery server.

**Default**: `false`

## Basic Configuration Examples

### Core Connection Mode
```yaml
core_url: "ws://your-core-server:9120"
monitoring_interval: "30-sec"
container_stats_interval: "1-min"
ssl_enabled: false
```

### Standalone Mode
```yaml
passkey: "your-secure-passkey"
monitoring_interval: "30-sec"
container_stats_interval: "1-min"
ssl_enabled: true
```

## Network Requirements

- **Port 8120**: Komodo Periphery web interface and API
- **Docker Socket**: Access to `/var/run/docker.sock` for container management
- **Outbound Connection**: To Komodo Core server (if configured)

[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
