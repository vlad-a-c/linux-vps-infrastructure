# TeamTalk server administration

This case study describes how I host TeamTalk on my personal Ubuntu VPS. It is a description of my setup, not a copy of live server configuration.

## Installation and configuration

I installed the TeamTalk server from its official archive under a dedicated `tt5` user and group. The server executable is shared at `/home/tt5/tt5srv`. I used TeamTalk's setup wizard to create the XML configuration for each instance, then chose and checked the settings. These included listening ports, channels, administrator accounts with full rights, and default user accounts with limited permissions. The real XML files are not published because they contain account details and other operational settings.

## Multiple instances with systemd

I adapted the single-instance systemd example supplied with TeamTalk into a template unit, `tt5@.service`. The `%i` specifier selects an instance directory under `/home/tt5/`. The executable is shared, while each instance has its own `tt5srv.xml` and `tt5srv.log`.

The relevant command from my template is:

```ini
[Service]
ExecStart=/home/tt5/tt5srv -nd -c /home/tt5/%i/tt5srv.xml -l /home/tt5/%i/tt5srv.log
ExecReload=kill -HUP $MAINPID
Type=simple
User=tt5
Group=tt5
```

For example, an instance named `example` uses `/home/tt5/example/tt5srv.xml` and `/home/tt5/example/tt5srv.log`. `example` is illustrative, not the name of a production instance.

After changing an instance's XML configuration, I restart that instance. If I change the systemd unit itself, I run `systemctl daemon-reload` before restarting the service. The unit includes an `ExecReload` action, but a reload is not the procedure I use for XML changes.

## What this demonstrates

- Installing server software from an official archive under a dedicated account
- Using a setup wizard while understanding and checking the resulting settings
- Separating configuration and logs for multiple instances
- Adapting a supplied systemd example to manage those instances
- Assigning different rights to administrators and default users

This page contains no real instance names, ports, account names, passwords, or production XML.

## References

- [TeamTalk Server Setup Guide](https://www.bearware.dk/teamtalksdk/v5.19a/docs/C-API/serversetup.html)
- [TeamTalk Server for Linux](https://bearware.dk/beta/docs/teamtalkserver.html)
