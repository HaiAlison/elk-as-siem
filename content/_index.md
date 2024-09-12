+++
title = "Basics"
date = 2024-08-31T22:02:02+07:00
weight = 1
chapter = false
+++

# Thiết lập ELK stack as a SIEM

#### Tổng quan
Trong phần workshop này, bạn sẽ tìm hiểu cách triển khai một hệ thống SIEM (Security Information and Event Management) sử dụng ELK stack. Bạn sẽ tìm hiểu cách cấu hình các thành phần của ELK stack như Elasticsearch, Logstash, Kibana và Beats để thu thập, lưu trữ và hiển thị dữ liệu log từ các nguồn khác nhau.

#### ELK stack
ELK stack là một giải pháp mã nguồn mở giúp thu thập, lưu trữ, xử lý và hiển thị dữ liệu log. ELK stack bao gồm các thành phần sau:
- **Elasticsearch**: là một công cụ tìm kiếm và phân tích dữ liệu phân tán, giúp lưu trữ và tìm kiếm dữ liệu log.
- **Logstash**: là một công cụ xử lý dữ liệu log, giúp thu thập, xử lý và chuyển dữ liệu log từ nhiều nguồn khác nhau.
- **Kibana**: là một công cụ trực quan hóa dữ liệu log, giúp hiển thị dữ liệu log dưới dạng biểu đồ, bảng và dashboard.
- **Beats**: là một tập hợp các agent nhẹ giúp thu thập dữ liệu log từ các nguồn khác nhau và chuyển dữ liệu đến Logstash hoặc Elasticsearch.
- **Filebeat**: là một agent giúp thu thập dữ liệu log từ các file log.
- **Suricata**: là một công cụ giúp phát hiện và báo cáo các mối đe dọa an ninh trên mạng.
#### SIEM
SIEM (Security Information and Event Management) là một giải pháp giúp tổ chức theo dõi, phát hiện và phản ứng với các sự kiện an ninh trên hệ thống. SIEM kết hợp các công nghệ như log management, event management, correlation, và security information management để giúp tổ chức phát hiện và phản ứng với các mối đe dọa an ninh.

#### Nội dung chính
1. [Cài đặt ELK stack](elk-stack)
2. [Cấu hình Suricata](filebeat)
3. [Cấu hình Filebeat](filebeat)
