# Đề tài 12: Bảo mật mạng Wi-Fi trong môi trường IoT và thiết bị thông minh

> Tài liệu khởi đầu cho nhóm 3 thành viên. Hiện tại chỉ tổng hợp phạm vi, kiến thức cần tìm và nguồn tham khảo; chưa xây dựng slide hoặc report.

## 1. Mục tiêu của đề tài

- Phân tích kiến trúc mạng WLAN và hệ thống IoT.
- Tìm hiểu rủi ro từ mật khẩu mặc định, firmware lỗi thời và cơ chế xác thực yếu.
- Đánh giá việc sử dụng WPA2/WPA3, phân đoạn mạng, ACL và giám sát lưu lượng.
- Thiết kế mô hình gồm thiết bị IoT, máy chủ quản lý và mạng người dùng.
- Đề xuất cách kiểm soát truy cập và phát hiện thiết bị có hành vi bất thường.

## 2. Phạm vi đề xuất

Chọn một tình huống xuyên suốt: **mạng nhà thông minh hoặc phòng lab nhỏ** gồm camera, cảm biến, ổ cắm thông minh, máy chủ quản lý, máy người dùng, access point và router/firewall. Đây là mô hình giả định để phân tích; nhóm cần ghi rõ thiết bị nào hỗ trợ WPA3, thiết bị nào chỉ hỗ trợ WPA2 và các dịch vụ mà mỗi thiết bị thực sự cần dùng.

Mô hình logic đề xuất:

```text
Internet
   |
Router / Firewall (ACL và nhật ký truy cập)
   |
   +-- SSID/VLAN người dùng ---- Laptop, điện thoại
   +-- SSID/VLAN IoT ----------- Camera, cảm biến, ổ cắm
   +-- Mạng máy chủ ------------ Máy chủ quản lý IoT
```

Quy tắc truy cập mẫu: thiết bị IoT chỉ liên lạc với máy chủ quản lý và các dịch vụ cần thiết như máy chủ cập nhật; người dùng truy cập máy chủ quản lý; thiết bị IoT không được chủ động truy cập máy người dùng. Quy tắc cụ thể phải dựa trên chức năng của thiết bị thực tế.

## 3. Kiến thức cần nắm

| Mảng | Câu hỏi cần trả lời |
| --- | --- |
| WLAN | Station, access point, SSID, BSS/ESS là gì? Thiết bị đi qua AP và mạng có dây như thế nào? |
| IoT | Thiết bị, ứng dụng quản lý, máy chủ/cloud và kênh cập nhật firmware liên hệ với nhau ra sao? |
| Rủi ro | Mật khẩu mặc định, firmware cũ, xác thực yếu, dịch vụ mở không cần thiết có thể dẫn đến điều gì? |
| WPA2/WPA3 | WPA3-Personal/SAE và Protected Management Frames đem lại gì? Thiết bị cũ chỉ dùng WPA2 ảnh hưởng đến phương án triển khai ra sao? |
| Phân đoạn và ACL | Mỗi nhóm thiết bị cần được phép truy cập đích nào, qua giao thức/cổng nào? |
| Giám sát | Log nào cho biết thiết bị kết nối hoặc liên lạc bất thường? Ngưỡng hoặc quy tắc cảnh báo là gì? |

**Lưu ý khi lập luận:** WPA3 chỉ là một lớp bảo vệ của liên kết Wi-Fi. Khi cần tương thích với thiết bị IoT cũ, phải đánh giá từng thiết bị kết nối bằng WPA2 hay WPA3; đồng thời xét mật khẩu mạnh, cập nhật firmware, phân đoạn mạng và giám sát. Không xem việc bật chế độ WPA2/WPA3 hỗn hợp là bằng chứng rằng mọi thiết bị đều được bảo vệ ở mức WPA3.

## 4. Nguồn tham khảo cụ thể

Ưu tiên tài liệu gốc sau. Khi trích dẫn trong report, ghi tên tài liệu, cơ quan/tác giả, năm và đường dẫn; với tài liệu dài nên ghi thêm mục hoặc số trang đã sử dụng.

| Nội dung | Nguồn | Dùng để làm gì |
| --- | --- | --- |
| Kiến trúc IEEE 802.11 | [IEEE 802.11 Working Group](https://grouper.ieee.org/groups/802/11/main.html) | Thuật ngữ AP, station, BSS, ESS. |
| Bảo mật WLAN | [NIST SP 800-153 – Guidelines for Securing Wireless Local Area Networks](https://csrc.nist.gov/pubs/sp/800/153/final) | Thiết kế, cấu hình, bảo trì và giám sát WLAN. Tài liệu xuất bản năm 2012, nên dùng cho nền tảng và đối chiếu thông tin WPA3 với nguồn mới hơn. |
| Năng lực bảo mật của thiết bị IoT | [NISTIR 8259 Series](https://www.nist.gov/itl/applied-cybersecurity/nist-cybersecurity-iot-program/nistir-8259-series) | Nhận diện thiết bị, cấu hình, bảo vệ dữ liệu, cập nhật phần mềm và các năng lực nền tảng. |
| Xác định yêu cầu bảo mật IoT | [NIST SP 800-213](https://www.nist.gov/publications/iot-device-cybersecurity-guidance-federal-government-establishing-iot-device) | Đặt yêu cầu cho thiết bị IoT trong bối cảnh một hệ thống cụ thể. |
| Các nhóm rủi ro IoT | [OWASP IoT Top 10](https://owasp.org/projects/Internet-of-things?tab=seek-and-understand) | Mật khẩu yếu/mặc định, dịch vụ và giao diện thiếu an toàn, cập nhật không an toàn, cấu hình mặc định không an toàn. Danh sách trên trang là bản **2018**. |
| Cập nhật firmware | [NIST – Software Update](https://pages.nist.gov/IoT-Device-Cybersecurity-Requirement-Catalogs/technical/update/) | Cập nhật bởi chủ thể được phép và xác minh nguồn cập nhật. |
| WPA3 | [Wi-Fi Alliance – Giới thiệu Wi-Fi CERTIFIED WPA3](https://www.globenewswire.com/news-release/2018/06/26/1529297/0/en/Wi-Fi-Alliance-introduces-Wi-Fi-CERTIFIED-WPA3-security.html) | Tính năng và mục tiêu bảo vệ của WPA3. |
| SAE và WPA3 | [Android Open Source Project – WPA3 and Wi-Fi Enhanced Open](https://source.android.com/docs/core/connect/wifi-wpa3-owe) | Giải thích WPA3-Personal dùng SAE thay cho PSK. |
| Phân đoạn và giới hạn luồng IoT | [NIST SP 1800-15 – Securing Small-Business and Home IoT Devices](https://csrc.nist.gov/pubs/sp/1800/15/final) | Ví dụ về kiểm soát liên lạc, firewall/flow rules và mạng riêng cho thiết bị rủi ro. |
| Mô tả luồng mạng hợp lệ của thiết bị | [RFC 8520 – Manufacturer Usage Description](https://www.rfc-editor.org/info/rfc8520/) | Cơ sở tham khảo để xây dựng danh sách đích/giao thức mà thiết bị được phép dùng. |
| Đưa thiết bị vào mạng an toàn | [NIST SP 1800-36](https://csrc.nist.gov/pubs/sp/1800/36/final) | Tham khảo thêm về xác minh thiết bị và quản lý vòng đời khi kết nối mạng. |
| Phân tích gói tin | [Wireshark User’s Guide](https://www.wireshark.org/docs/wsug_html/) | Cách quan sát lưu lượng và dùng bộ lọc hiển thị. |
| Nhật ký và cảnh báo IDS | [Suricata – EVE JSON Format](https://docs.suricata.io/en/suricata-8.0.2/output/eve/eve-json-format.html) | Các trường trong bản ghi sự kiện/cảnh báo để mô tả phương án giám sát. |

## 5. Kịch bản phân tích và tiêu chí đánh giá

Chọn 2–3 kịch bản để cùng dùng trong phần thiết kế, đánh giá và sau này là phần trình bày:

1. **Thiết bị IoT truy cập máy người dùng:** ACL giữa mạng IoT và mạng người dùng có chặn được luồng chủ động này không? Log có ghi nhận lần bị chặn không?
2. **Camera kết nối đến đích lạ:** hệ thống có nhận biết đích mới, lưu lượng tăng đột biến hoặc cảnh báo từ IDS không? Ai nhận cảnh báo và xử lý thế nào?
3. **Thiết bị có firmware cũ hoặc mật khẩu mặc định:** nhóm xác định rủi ro, biện pháp khắc phục và cách kiểm tra trạng thái sau khắc phục ra sao?

Với mỗi biện pháp, nên đánh giá cả **tác dụng**, **giới hạn** và **khả năng triển khai** trong mô hình giả định. Ví dụ: phân đoạn mạng giảm khả năng thiết bị IoT truy cập sang mạng người dùng, nhưng cần định nghĩa đúng các luồng hợp lệ để thiết bị vẫn hoạt động.

## 6. Phân công cho nhóm 3 thành viên

| Thành viên | Phần phụ trách | Đầu ra chuẩn bị |
| --- | --- | --- |
| 1 | Nền tảng WLAN/IoT; mật khẩu mặc định, firmware cũ, xác thực yếu | Sơ đồ kiến trúc cơ bản; bảng nguy cơ → nguyên nhân → hậu quả → biện pháp |
| 2 | WPA2/WPA3, SSID/VLAN, ACL và thiết kế mạng | Sơ đồ mạng đề xuất; bảng quy tắc truy cập và lý do cho từng quy tắc |
| 3 | Giám sát lưu lượng, hành vi bất thường và đánh giá | Kịch bản kiểm tra; nguồn log; tiêu chí phát hiện và phương án xử lý |

Cả nhóm cùng chốt một danh sách thiết bị giả định, một sơ đồ mạng, thuật ngữ thống nhất và 2–3 kịch bản trước khi làm slide/report để các phần nối với nhau.

## 7. Thứ tự thực hiện tiếp theo

1. Đọc các nguồn trong phần 4, ghi lại luận điểm và vị trí trích dẫn cụ thể.
2. Chốt phạm vi, thiết bị và sơ đồ mạng giả định.
3. Lập bảng rủi ro và bảng luồng truy cập được phép.
4. Xây dựng 2–3 kịch bản đánh giá có tiêu chí quan sát rõ ràng.
5. Sau khi nội dung thống nhất, mới chuyển thành slide báo cáo và report nộp.
