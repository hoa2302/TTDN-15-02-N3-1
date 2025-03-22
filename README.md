---
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![GitLab](https://img.shields.io/badge/gitlab-%23181717.svg?style=for-the-badge&logo=gitlab&logoColor=white)
![Postgres](https://img.shields.io/badge/postgres-%23316192.svg?style=for-the-badge&logo=postgresql&logoColor=white)

![Python](https://img.shields.io/badge/python-v3.8+-blue.svg)
[![security: bandit](https://img.shields.io/badge/security-bandit-yellow.svg)](https://github.com/PyCQA/bandit)


1. Thống kê tài sản theo trạng thái
   ![image](https://github.com/user-attachments/assets/2e44dca6-c137-4296-b8cc-3f4772d3522f)
   ![image](https://github.com/user-attachments/assets/fa6c2eb4-b641-46d3-9ad8-fcb096539a51)
   ![image](https://github.com/user-attachments/assets/87e35031-7f96-40b9-bf83-2e3876f44b9d)
2. Quản lý tài sản
   Tài sản
   ![image](https://github.com/user-attachments/assets/b0047b4f-241f-466c-b8b7-1e924cf742a8)
   Danh mục quản lý tài sản
   ![image](https://github.com/user-attachments/assets/1f43b0a1-2b5d-4bb9-9e28-f731c29ce09c)
3. Bảo trì tài sản
   ![image](https://github.com/user-attachments/assets/52ae4324-7aad-4fbf-ad17-22f0c8f6aa69)
4. Thanh lý tài sản
   ![image](https://github.com/user-attachments/assets/871b9815-2f36-4798-9a20-cddc2e222693)
5. Mượn trả tài sản
   ![image](https://github.com/user-attachments/assets/054cb511-b280-4e1e-b9df-2c5ed6195840)
6. Điều chuyển tài sản
   ![image](https://github.com/user-attachments/assets/1d9d4ae6-03b2-4058-b180-0b080b272137)
7. Nhà cung cấp
   ![image](https://github.com/user-attachments/assets/767c5bdc-7189-4244-a143-35dcaa9ca4cc)
8. Lịch sử
   Lịch sử sử dụng tài sản
   ![image](https://github.com/user-attachments/assets/971c691b-6371-499d-a6d8-f785799879b4)
   Lịch sử điều chuyển tài sản
   ![image](https://github.com/user-attachments/assets/352a1ba8-f227-48b8-8457-d75c49e2beee)
# 1. Cài đặt công cụ, môi trường và các thư viện cần thiết

## 1.1. Clone project.
```
git clone https://gitlab.com/anhlta/odoo-fitdnu.git
```
```
cd odoo-fitdnu
```
```
git checkout cntt15_02
```


## 1.2. cài đặt các thư viện cần thiết

Người sử dụng thực thi các lệnh sau đề cài đặt các thư viện cần thiết

```
sudo apt-get install libxml2-dev libxslt-dev libldap2-dev libsasl2-dev libssl-dev python3.10-distutils python3.10-dev build-essential libssl-dev libffi-dev zlib1g-dev python3.10-venv libpq-dev
```
## 1.3. khởi tạo môi trường ảo.

Thay đổi trình thông dịch sang môi trường ảo và chạy requirements.txt để cài đặt tiếp các thư viện được yêu cầu
```
python3.10 -m venv ./venv
```
```
source venv/bin/activate
```
```
pip3 install -r requirements.txt
```

# 2. Setup database

Khởi tạo database trên docker bằng việc thực thi file dockercompose.yml.
```
sudo apt install docker-compose
```
```
sudo docker-compose up -d
```

# 3. Setup tham số chạy cho hệ thống

## 3.1. Khởi tạo odoo.conf

Tạo tệp **odoo.conf** có nội dung như sau:

```
[options]
addons_path = addons
db_host = localhost
db_password = odoo
db_user = odoo
db_port = 5432
xmlrpc_port = 8069
```

# 4. Chạy hệ thống và cài đặt các ứng dụng cần thiết

Lệnh chạy
```
python3 odoo-bin.py -c odoo.conf -u all
```


Người sử dụng truy cập theo đường dẫn _http://localhost:8069/_ để đăng nhập vào hệ thống.

Hoàn tất
    
