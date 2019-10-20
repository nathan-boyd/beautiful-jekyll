---
layout: post
title: Monitoring Self Hosted Blog Raspberry Pi
image: /img/hello_world.jpeg
---

install telegraf, influxdb, and chronograf
```
sudo apt-get install telegraf influxdb chronograf
```

Add telegraf user to video group
```
sudo usermod -aG video telegraf
```

Check telegraf services logs
```
systemctl status telegraf
```

Check that the telegraf service is enables
```
systemctl list-unit-files | grep enabled | grep tele
```

Create jekyll service
```
[Unit]
After=jekyll.service

[Service]
ExecStart=/usr/local/bin/start-blog.sh

[Install]
WantedBy=default.target
```

chmod 744 /usr/local/bin/disk-space-check.sh

Script contents
```
jekyll serve --host=0.0.0.0
```

# chmod 664 /etc/systemd/system/disk-space-check.service
# systemctl daemon-reload
# systemctl enable disk-space-check.service
