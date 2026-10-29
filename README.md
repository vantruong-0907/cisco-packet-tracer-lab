# Enterprise Network Simulation (Cisco Packet Tracer)

Dự án thiết kế, quy hoạch IP và mô phỏng hệ thống mạng doanh nghiệp phân tầng sử dụng Cisco Packet Tracer.

---

## 📐 Kiến trúc Mô hình & Thiết bị
- **Core Layer:** Multilayer Switch Cisco 3650 (Đảm nhận Inter-VLAN Routing, DHCP Server).
- **Edge Layer:** Router Cisco 2911 (Định tuyến biên kết nối nhánh Server).
- **Access Layer:** Switch Cisco 2960 và các máy trạm (PC/Server).

## 🌐 Quy hoạch Địa chỉ IP
- **VLAN 10:** `192.168.0.0/23` (Gateway: `192.168.0.1`)
- **VLAN 11:** `192.168.10.0/24` (Gateway: `192.168.10.1`)
- **Server Network:** `10.0.0.0/24` (Gateway: `10.0.0.1`)
- **Point-to-Point Link (Core - Router):** `172.16.0.0/30`

## ⚙️ Kỹ thuật & Cấu hình Nổi bật
- **Inter-VLAN Routing & Dynamic IP:** Bật `ip routing` và cấu hình DHCP Pools trực tiếp trên Core Switch.
- **Layer 3 Routed Port:** Chuyển đổi cổng giao tiếp giữa Core Switch và Router biên (`no switchport`).
- **Static Routing 2 chiều:** Định tuyến tĩnh giữa Core Switch và Router0 đảm bảo thông tuyến toàn bộ phân đoạn mạng.
- **L2 Switching:** Cấu hình 802.1Q Trunking, Access ports.
