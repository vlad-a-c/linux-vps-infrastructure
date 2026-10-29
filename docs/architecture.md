# Architecture overview

This page describes the VPS at a high level using only details confirmed by the administrator. It is not a deployment guide or a copy of production configuration.

## Host

- VPS provider: SSD Nodes
- Operating system: Ubuntu Server 24.04 LTS
- Resources: 4 vCPU, 16 GB RAM, 320 GB SSD
- Remote administration: SSH

## Hosting management

ISPConfig is the control panel used to configure websites and DNS records. The panel's installation includes the web and DNS services. Changes to these hosting settings are made in its interface. BIND and Postfix configuration files have not been manually edited.

Let's Encrypt certificates and website hosting settings are also managed from ISPConfig. The public documentation avoids production domains, addresses, and exact configuration exports.

## Other hosted services

TeamTalk and AzuraCast have been hosted on the VPS. Their installation methods and detailed configuration are intentionally left undocumented until verified.

## Simplified relationship

```text
Administrator --SSH--> Ubuntu VPS
Administrator --ISPConfig UI--> websites, DNS records, hosting settings, certificates
Ubuntu VPS --> TeamTalk and AzuraCast
```

## Scope of experience

This project demonstrates panel-based hosting administration and troubleshooting. It does not claim direct management of BIND or Postfix configuration files. Security controls and operational procedures will be documented as completed only after they have been applied and checked.
