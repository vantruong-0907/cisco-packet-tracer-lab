# Enterprise Network Simulation (Cisco Packet Tracer)

Dự án thiết kế, quy hoạch IP và mô phỏng hệ thống mạng doanh nghiệp phân tầng sử dụng Cisco Packet Tracer

---

## 📐 Kiến trúc Mô hình & Thiết bị
- **Core Layer:** Multilayer Switch (`SW CORE` - Cisco 3650) đảm nhận Inter-VLAN Routing và cấp phát DHCP.
- **Edge Layer:** Router biên (`R0` - Cisco 2911) kết nối nhánh Server.
- **Access Layer:** Các Switch truy nhập (`SW AC1`, `SW AC2`, `SW SERVER` - Cisco 2960) kết nối các máy trạm (PC/Server)

## 🌐 Quy hoạch Địa chỉ IP
- **VLAN 10:** `192.168.1.0/23` (Gateway: `192.168.1.1`)
- **VLAN 11:** `192.168.10.0/24` (Gateway: `192.168.10.1`)
- **Server Network:** `10.0.0.0/24` (Gateway: `10.0.0.1`)
- **Point-to-Point Link (SW CORE - R0):** `172.16.0.0/30`

## ⚙️ Kỹ thuật & Cấu hình Nổi bật
- **Inter-VLAN Routing & Dynamic IP:** Bật `ip routing` và cấu hình DHCP Pools trực tiếp trên `SW CORE`.
- **Layer 3 Routed Port:** Chuyển đổi cổng giao tiếp giữa `SW CORE` và `R0` (`no switchport`)
- **Static Routing 2 chiều:** Định tuyến tĩnh giữa `SW CORE` và `R0` đảm bảo thông tuyến toàn bộ phân đoạn mạng
- **L2 Switching:** Cấu hình Trunking, Access ports trên `SW AC1`, `SW AC2` và `SW SERVER`.
