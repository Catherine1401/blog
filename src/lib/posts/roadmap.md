---
title: "Road Map"
date: "2025-05-14"
updated: "2025-05-14"
categories:
  - "road map"
coverImage: "/images/roadmap.jpeg"
coverWidth: 16
coverHeight: 9
excerpt: Lộ trình chi tiết triển khai dự án
---

## 🧩 Bước 1 – Học cách giao tiếp với CNOSDB
---
#### ✅ Mục tiêu:

Biết cách giao tiếp, ghi và đọc dữ liệu từ CNOSDB.

#### 🛠️ Việc cần làm:

- Tìm hiểu CNOSDB là gì, cách hoạt động (time-series database).
- Cài đặt CNOSDB local (qua Docker hoặc bản cài sẵn).
- Tìm hiểu Line Protocol hoặc JSON format của CNOSDB.
- Test ghi dữ liệu mẫu bằng curl hoặc Postman:

```bash
curl -X POST http://localhost:port/write \
     --data-raw "weather,location=greenhouse temperature=31.2,humidity=65"

```

Học truy vấn dữ liệu với curl hoặc Web UI (nếu có).

#### 📌 Kết quả:

Ghi và đọc được dữ liệu mẫu thủ công từ terminal/Postman.

## 🧩 Bước 2 – Viết script Python sinh dữ liệu giả
---
#### ✅ Mục tiêu:

Tạo dữ liệu cảm biến như thật để mô phỏng môi trường nông nghiệp.

#### 🛠️ Việc cần làm:

Tạo file Python `sensor_simulator.py`.

Sinh các giá trị ngẫu nhiên:

- Nhiệt độ: random.uniform(25, 40)
- Độ ẩm đất: random.randint(10, 90)
- Ánh sáng: random.randint(300, 1200)

Gắn timestamp hiện tại, format lại đúng chuẩn line protocol:

```python
f"sensor_data temperature={temp},humidity={humid},light={light} {timestamp}"
```

In ra terminal để kiểm tra dữ liệu sinh.

#### 📌 Kết quả:

File Python sinh dữ liệu cảm biến đều đặn, đúng định dạng chuẩn.

## 🧩 Bước 3 – Ghi dữ liệu vào CNOSDB
---
#### ✅ Mục tiêu:

Gửi dữ liệu cảm biến từ Python vào CNOSDB.

#### 🛠️ Việc cần làm:

Dùng thư viện `requests` gửi POST:

```python
requests.post("http://localhost:port/write", data=data_line)
```

Viết vòng lặp while True gửi mỗi 5s.

Kiểm tra trong CNOSDB xem dữ liệu có ghi thành công không.

#### 📌 Kết quả:

Dữ liệu cảm biến được ghi đều đặn vào CNOSDB qua Python.

## 🧩 Bước 4 – Truy vấn dữ liệu từ CNOSDB
---
#### ✅ Mục tiêu:

Đọc và xử lý dữ liệu để phân tích.

#### 🛠️ Việc cần làm:

Dùng Python gửi truy vấn HTTP GET hoặc dùng API nếu CNOSDB có hỗ trợ.

Viết truy vấn như:

`"SELECT last(temperature) FROM sensor_data"`

`"SELECT mean(humidity) WHERE time > now() - 1h"`

Parse kết quả JSON trả về.

#### 📌 Kết quả:

Truy xuất dữ liệu cảm biến trong khoảng thời gian thực tế, có thể dùng được.

## 🧩 Bước 5 – Dựng giao diện đơn giản
---
#### ✅ Mục tiêu:

Tạo giao diện thân thiện hiển thị trạng thái và dữ liệu.

#### 🛠️ Việc cần làm:

Dùng `Streamlit` (giao diện web đơn giản với Python).

Hiển thị:

- Biểu đồ nhiệt độ, độ ẩm, ánh sáng (dùng altair, matplotlib, plotly).
- Trạng thái hiện tại (dựa trên logic ở bước sau).
- Cập nhật theo thời gian thực.

#### 📌 Kết quả:

Giao diện đơn giản, cập nhật dữ liệu theo thời gian thực.

## 🧩 Bước 6 – Thiết lập trạng thái thông minh
---
#### ✅ Mục tiêu:

Thiết lập các rule mô phỏng tự động hóa như con người.

#### 🛠️ Việc cần làm:

Viết các điều kiện (rule):

- Nhiệt độ lớn hơn 35°C và ánh sáng lớn hơn 900 lux → “Nắng nóng”
- Độ ẩm đất nhỏ hơn 30% → “Khô hạn → cần tưới”

Dùng if-else trong Python để phân tích.

In trạng thái ra hoặc đổi màu trên Streamlit.

#### 📌 Kết quả:

Hệ thống tự xác định trạng thái môi trường và đưa ra phản ứng.

## 🧩 Bước 7 – Thiết lập hệ thống phân tán và cân bằng tải
---
#### ✅ Mục tiêu:

Tăng tính sẵn sàng và ổn định của hệ thống.

#### 🛠️ Việc cần làm:

Phân tán CNOSDB:

- Cài đặt nhiều instance CNOSDB (trên Docker hoặc nhiều máy).
- Thiết lập replication giữa các node.
- Cấu hình retention policy và shard group (nếu CNOSDB hỗ trợ).

Load balancing:

Dùng NGINX hoặc viết Python chọn node random:

```python
url = random.choice(["http://node1", "http://node2"])
Log lại node đang gửi dữ liệu để kiểm chứng phân tán.
```

#### 📌 Kết quả:

Hệ thống vẫn ghi/đọc dữ liệu bình thường khi 1 node chết. Truy cập được nhiều node, đảm bảo cân bằng tải.


