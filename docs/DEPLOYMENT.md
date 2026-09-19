# Deployment & Operations Guide: Fallback Product

## 🚀 Live Access & URLs
- **Live Public Access URL:** [/preview/prod-fallback-product-af2a42/](/preview/prod-fallback-product-af2a42/)
- **Internal Port:** `0`
- **Runtime Engine:** `python_preview`
- **Deployment Status:** `DEPLOYED / ACTIVE`
- **Timestamp:** `2026-09-19T21:15:12.639221+00:00`

## 🛠️ Management & Service Control
### Launch Command
```bash
python3 app.py --port 0
```

### Health Check Probe
```bash
curl -I http://127.0.0.1:0/
```

### Systemd Service Template
```ini
[Unit]
Description=Fallback Product Service
After=network.target

[Service]
Type=simple
WorkingDirectory=/tmp/pytest-of-root/pytest-0/test_markdown_and_fallback_dec0/fallback_ws/prod-fallback-product-af2a42
ExecStart=/usr/bin/python3 /tmp/pytest-of-root/pytest-0/test_markdown_and_fallback_dec0/fallback_ws/prod-fallback-product-af2a42/app.py
Restart=always
RestartSec=3

[Install]
WantedBy=multi-user.target
```

## 🔒 Production Security Protocols
- HTTP-only reverse proxy via Nexus Gateway.
- Dedicated port allocation with zero port conflict.
