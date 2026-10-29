# Linux VPS Infrastructure

Sanitized notes about administering my personal Ubuntu Server 24.04 LTS VPS. This repository documents hands-on hosting and troubleshooting experience relevant to Junior Linux/System Administration roles.

## Environment

- VPS: 4 vCPU, 16 GB RAM, 320 GB SSD
- Operating system: Ubuntu Server 24.04 LTS
- Hosting panel: ISPConfig
- Web hosting and DNS managed through the ISPConfig interface
- Hosted services have included TeamTalk and AzuraCast

## Hands-on work

- Managing websites and DNS records through ISPConfig
- Managing hosting settings and Let's Encrypt certificates through ISPConfig
- Connecting through SSH and investigating service, DNS, and certificate issues
- Maintaining applications hosted on a personal VPS

All DNS and hosting configuration described here was done through the ISPConfig panel. I have not manually edited BIND or Postfix configuration files. The underlying services may be installed or configured by ISPConfig, but I do not claim direct configuration of those services.

## Currently learning

UFW configuration, SSH hardening, backups, monitoring, and repeatable operational checklists. These are learning goals, not completed security claims.

## Documentation roadmap

- Architecture and service inventory
- Anonymized examples of DNS records and TLS settings as configured in ISPConfig
- Troubleshooting case studies with symptoms, checks, and resolutions
- Security improvements documented after they are applied and verified

## Safety and scope

This repository contains illustrative examples only. It does not include production IP addresses, domains, hostnames, credentials, keys, tokens, private certificates, real DNS zones, or complete production configuration files. Examples will use reserved addresses and `example.com` domains.
