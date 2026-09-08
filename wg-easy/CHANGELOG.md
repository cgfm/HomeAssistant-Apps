# Changelog

## 0.2.3

- Switched iptables backend from legacy to nftables for compatibility with current Home Assistant OS kernels.
- Fixed WireGuard startup failure caused by missing "ip_tables" kernel modules.
- Added "iptables-nft" and "ip6tables-nft" alternatives.
- Improved compatibility with HAOS 6.18 and newer.

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
