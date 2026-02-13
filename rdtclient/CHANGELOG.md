# Changelog

## 1.0.1

- Add HEALTHCHECK and watchdog for proper running status detection
- Add "Open Web UI" button support
- Remove unnecessary PUID/PGID options (runs as root for universal file access)

## 1.0.0

- Initial release
- Wraps rogerfar/rdtclient Docker image
- Access to Home Assistant media and share folders
- Configurable PUID, PGID, and timezone
- Supports amd64 and aarch64 architectures
