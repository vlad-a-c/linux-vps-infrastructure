# AzuraCast on my VPS

## Scope

I installed AzuraCast using the official `docker.sh` installer. Through AzuraCast, I configured a station, user accounts, AutoDJ, stream sources, a domain, and HTTPS. This is an account of operating a hosted service, not a claim that I built AzuraCast or configured every component manually.

## TLS integration and incident

After a Let’s Encrypt certificate expired, I re-created certificates managed through ISPConfig and changed certificate paths. My AzuraCast Docker Compose override still referred to files under the previous domain-specific ACME certificate directory. That directory was no longer present, and the AzuraCast web service stopped working. The incident showed me that a container bind mount depends on the host paths remaining valid when certificates are replaced.

I investigated the certificate-path mismatch and updated the configuration to use the current certificate files.

## What I learned

- Check the host paths referenced by Compose overrides after certificate changes.
- Treat application HTTPS as a dependency on certificate renewal and file placement, not just a one-time setting.
- Document certificate ownership and dependencies so future changes are easier to trace.

## Safety and scope

This case study omits the real domain, certificate paths, keys, account details, and production configuration. No certificate or private key is stored in this repository.

## References

- [AzuraCast: SSL & Let’s Encrypt](https://www.azuracast.com/docs/administration/ssl-and-lets-encrypt/)
- [acme.sh documentation](https://github.com/acmesh-official/acme.sh/blob/master/README.md)
