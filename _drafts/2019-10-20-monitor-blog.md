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
