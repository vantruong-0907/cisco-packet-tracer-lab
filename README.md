# Enterprise Network Simulation (Cisco Packet Tracer)

Dự án thiết kế, quy hoạch IP và mô phỏng hệ thống mạng doanh nghiệp phân tầng sử dụng Cisco Packet Tracer

---

## Kiến trúc Mô hình & Thiết bị
- **Core Layer:** Multilayer Switch (`SW CORE` - Cisco 3650) đảm nhận Inter-VLAN Routing và cấp phát DHCP.
- **Edge Layer:** Router biên (`R0` - Cisco 2911) kết nối nhánh Server.
- **Access Layer:** Các Switch truy nhập (`SW AC1`, `SW AC2`, `SW SERVER` - Cisco 2960) kết nối các máy trạm (PC/Server)

## Quy hoạch Địa chỉ IP
- **VLAN 10:** `192.168.10.0/24` (Gateway: `192.168.10.1`)
- **VLAN 11:** `192.168.11.0/24` (Gateway: `192.168.11.1`)
- **Server Network:** `10.0.0.0/24` (Gateway: `10.0.0.1`)
- **Point-to-Point Link (SW CORE - R0):** `172.16.0.0/30`

## Kỹ thuật & Cấu hình Nổi bật
- **Inter-VLAN Routing & Dynamic IP:** Bật `ip routing` và cấu hình DHCP Pools trực tiếp trên `SW CORE`.
- **Layer 3 Routed Port:** Chuyển đổi cổng giao tiếp giữa `SW CORE` và `R0` (`no switchport`)
- **Static Routing 2 chiều:** Định tuyến tĩnh giữa `SW CORE` và `R0` đảm bảo thông tuyến toàn bộ phân đoạn mạng
- **L2 Switching:** Cấu hình Trunking, Access ports trên `SW AC1`, `SW AC2` và `SW SERVER`.
## Sơ đồ mạng 
<img width="695" height="933" alt="image" src="https://github.com/user-attachments/assets/6fc1b9cf-417a-4d0e-a15a-acaf3d3181f4" />

## Cấu hình SW CORE
  ** Cấu hình cơ bản và định tuyến trên CORE SW
  <img width="626" height="422" alt="image" src="https://github.com/user-attachments/assets/3d2702e1-5b42-4e95-b93b-82c1d12313b0" />
  ** Cấu hình Gateway
  <img width="651" height="437" alt="image" src="https://github.com/user-attachments/assets/0b2254d2-f1ec-4ece-b6ca-d9f15a782276" />
  ** Cấu hình DHCP
  <img width="641" height="356" alt="image" src="https://github.com/user-attachments/assets/fcd1b07d-9480-43df-b46b-aed9f3d46a7f" />
  ** Cấu hình Trunking
  <img width="630" height="197" alt="image" src="https://github.com/user-attachments/assets/ec3fba25-efaa-415f-950e-a6a5d4bd9019" />
  ** Cấu hình Static Routing
  <img width="625" height="227" alt="image" src="https://github.com/user-attachments/assets/2f0e8ad2-944a-4101-89ce-463cd479a8c7" />
  ** Cấu hình SSH
  <img width="631" height="573" alt="image" src="https://github.com/user-attachments/assets/e0951ce2-0ae9-4af6-9d56-4a67f71b24f9" />

## Cấu hình Router 
  ** Cấu hình ip cho các cổng của Router
  <img width="617" height="403" alt="image" src="https://github.com/user-attachments/assets/64a23cde-c029-489e-b625-86bd11435884" />
  ** Cấu hình Static routing cho Router
  <img width="626" height="216" alt="image" src="https://github.com/user-attachments/assets/945d80a9-e876-42b7-8dfe-9024febf1f28" />


