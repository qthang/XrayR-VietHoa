# XRayR version 0.8.0 - Việt Hoá Full
Một khung phụ trợ Xray có thể dễ dàng hỗ trợ nhiều bảng.

Một khung công tác back-end dựa trên Xray, hỗ trợ các giao thức V2ay, Trojan, Shadowsocks, cực kỳ dễ dàng mở rộng và hỗ trợ kết nối nhiều bảng điều khiển

Tìm mã nguồn tại: [Misaka-blog/XrayR](https://github.com/Misaka-blog/XrayR)

# Hướng dẫn chi tiết

[Hướng dẫn chi tiết](https://crackair.gitbook.io/xrayr-project/)

# Mở port cho VPS
Để đảm bảo cho việc cài nút V2board, bạn cần mở các cổng của nó tránh trường hợp lỗi không thể kết nối tới internet.

```
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw allow 80
sudo ufw allow 443
```

# Cài đặt XrayR
Tiếp tục chúng ta nhập lệnh sau để bắt đầu cài đặt XrayR về VPS của bạn

```
bash <(curl -Ls https://raw.githubusercontent.com/qthang/XrayR-script/master/install.sh)
```
# Cấu hình XrayR
Sau khi cài đặt xong, chúng ta tiếp tục nhập lệnh sau để vào cấu hình XrayR. Sử dụng `nano` hoặc `vi` để vào thư mục cấu hình

```
nano /etc/XrayR/config.yml
```
```
vi /etc/XrayR/config.yml
```
Hoặc gọi `xrayr` rồi bấm phím `0`

Chúng ta cần chú ý các lệnh sau đây:
```
1: dòng PanelType : Tên kiểu web (ví dụ V2board, SSpanel,... chữ đầu viết hoa)
2: dòng ApiHost : Địa chỉ web muốn liên kết (ví dụ https://4gfree.qthang.net)
3: dòng ApiKey : key của web (lấy trên web admin / cấu hình hệ thống / máy chủ chìa khóa giao tiếp)
4: dòng NodeID : ID server (lấy trên web admin / Quản lý nút / tên ID nút)
5: dòng certdomain : IP của server muốn đưa lên web
```
Với `nano`: Sau khi cài đặt xong, chúng ta sẽ ấn `CTRL + S` để lưu lại, sau đó ấn `CTRL + X` để thoát ra.


Thêm dòng `DisableSniffing: true` giữa 2 dòng `ControllerConfig:` và `ListenIP: 0.0.0.0` để fix lỗi zalo
```
  RuleListPath:           # /etc/XrayR/rulelist Đường dẫn đến tệp danh sách quy tắc cục bộ
ControllerConfig:
  DisableSniffing: true   # Tắt sniffing để fix lỗi zalo 
  ListenIP: 0.0.0.0       # Địa chỉ IP bạn muốn nghe
  SendIP: 0.0.0.0         # Địa chỉ IP bạn muốn gửi gói
```
Nếu bị lỗi xrayr không chạy thì bỏ dòng `DisableSniffing: true` đi nhé.

# Bắt đầu chạy XrayR
Để bắt đầu .chạy XrayR chúng ta sẽ nhập mã code này trong VPS tạo nút
```
xrayr start
```

# Nên sử dụng VPS sạch để cài đặt tránh lỗi vặt
# My Telegram
[t.me/qthang_4gfree](https://t.me/qthang_4gfree)

# Thanks
Misaka, DauDau, SkyHT,...
