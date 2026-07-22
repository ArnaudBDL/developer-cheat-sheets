# Linux : Services

## Manage Services

```bash
sudo systemctl start service
sudo systemctl stop service
sudo systemctl restart service
sudo systemctl reload service
sudo systemctl status service
```

## Boot State

```bash
sudo systemctl enable service
sudo systemctl disable service
sudo systemctl enable --now service
sudo systemctl is-enabled service
sudo systemctl is-active service
```

## Inspect Units

```bash
systemctl list-units --type=service
systemctl list-unit-files --type=service
systemctl list-dependencies service
systemctl cat service
systemctl show service
systemctl --failed
```

## Unit File

```ini
[Unit]
Description=Application Service
After=network-online.target
Wants=network-online.target

[Service]
Type=simple
User=application
Group=application
WorkingDirectory=/srv/application
ExecStart=/srv/application/bin/server
Restart=on-failure

[Install]
WantedBy=multi-user.target
```

```bash
sudo systemctl daemon-reload
sudo systemctl enable --now application.service
```

## Logs

```bash
journalctl -u service
journalctl -u service -f
journalctl -u service --since today
```
