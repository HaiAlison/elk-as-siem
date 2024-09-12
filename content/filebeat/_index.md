+++
title = "Filebeat"
date = 2024-08-31T22:20:23+07:00
weight = 5
chapter = true
pre = "<b>X. </b>"
+++

Sau khi cài đặt ELK stack, chúng ta sẽ cài đặt Suricata và filebeat để thu thập log từ Suricata và chuyển đến elasticsearch

#### Cài đặt Suricata
ở đây chúng ta sẽ sử dụng máy ảo để demo, nên chúng ta sẽ cài đặt Suricata trên máy ảo
```bash
sudo apt-get update
sudo apt-get install -y software-properties-common
sudo add-apt-repository ppa:oisf/suricata-stable
sudo apt-get update
sudo apt-get install -y suricata
```

sau khi cài đặt xong, chúng ta sẽ cấu hình Suricata để thu thập log và chuyển đến filebeat
Filebeat là một agent giúp thu thập dữ liệu log từ các file log. Chúng ta sẽ cài đặt filebeat trên máy ảo

#### Cài đặt Filebeat
```bash
sudo apt-get update
sudo apt-get install -y filebeat
```
sau khi cài đặt xong, chúng ta sẽ cấu hình filebeat để chuyển log từ Suricata đến elasticsearch

