# Service inventory

This is a high-level inventory of services discussed for the personal VPS. It records the administrator's interaction with each service without publishing production configuration.

| Component | Known role | How it has been managed |
| --- | --- | --- |
| Ubuntu Server 22.04 LTS | VPS operating system | SSH-based administration |
| ISPConfig | Hosting control panel | Web interface for websites, DNS records, and hosting settings |
| Web service | Serves hosted websites | Hosting configuration through ISPConfig; no claim of manual Nginx configuration |
| DNS service | Serves configured DNS zones | DNS records entered through ISPConfig; no manual BIND zone-file edits |
| Let's Encrypt | TLS certificates for hosting | Requested or managed through ISPConfig |
| TeamTalk | Hosted communication service | Hosted on the VPS; setup details pending confirmation |
| AzuraCast | Hosted radio service | Hosted on the VPS; setup details pending confirmation |

The hosting panel may install or configure underlying software. This inventory distinguishes that from the actions performed through the panel. No manual Postfix configuration is claimed.

## Details still to document

For TeamTalk and AzuraCast, installation method, service management, backup approach, and troubleshooting examples will be added only after they are confirmed.
