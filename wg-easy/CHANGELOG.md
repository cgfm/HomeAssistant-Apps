# Changelog

## 0.2.2

- Switched WG-Easy base image to version 15.
- Added dynamic Home Assistant ingress port handling.
- Added support for automatically assigned frontend ports.
- Added required `curl` dependency for Supervisor API access.
- Enabled insecure HTTP mode for Home Assistant ingress.

## 0.2.1

- Switched WG-Easy base image from `latest` to version 15.
- Fixed startup failure caused by missing `/app/server/index.mjs`.

## 0.2.0

- Initial WG-Easy Home Assistant app release.
