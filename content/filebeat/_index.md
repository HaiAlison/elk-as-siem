+++
title = "Surricata và Filebeat"
date = 2024-08-31T22:20:23+07:00
weight = 5
chapter = false
pre = "<b>2. </b>"
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

#### Cấu hình Suricata
```bash
sudo nano /etc/suricata/suricata.yaml
  
# Cấu hình log để chuyển log từ Suricata đến filebeat
outputs:
  - eve-log:
      enabled: yes
      filetype: json
      filename: eve.json
```

sau khi cấu hình xong, chúng ta sẽ khởi động Suricata
```bash
sudo systemctl start suricata
sudo systemctl enable suricata
```

#### Cấu hình Filebeat
```bash
sudo nano /etc/filebeat/filebeat.yml

# Cấu hình output để chuyển log từ Suricata đến elasticsearch
output.elasticsearch:
  hosts: ["localhost:9200"]
  index: "suricata-%{+yyyy.MM.dd}"

# Cấu hình input để thu thập log từ Suricata
filebeat.inputs:
- type: log
  enabled: true
  paths:
    - /var/log/suricata/eve.json
```

sau khi cấu hình xong, chúng ta sẽ khởi động filebeat
```bash
sudo systemctl start filebeat
sudo systemctl enable filebeat
```

#### Kiểm tra log
```bash
sudo tail -f /var/log/suricata/eve.json
```

