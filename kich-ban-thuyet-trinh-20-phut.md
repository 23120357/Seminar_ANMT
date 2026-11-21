# Kịch bản thuyết trình 20 phút — bản Canva 23 slide

**Bản lời thoại chi tiết để tập nói:** [loi-thoai-thuyet-trinh-23-slide.md](loi-thoai-thuyet-trinh-23-slide.md). File này giữ vai trò dàn ý và mốc thời gian; bản lời thoại có câu nói cụ thể cho từng slide.

**Deck:** [Bảo mật Wi-Fi IoT — 23 slide](https://canva.link/iz6qvhl54eh5e6w)
**Đề tài:** Bảo mật mạng Wi-Fi trong môi trường IoT và thiết bị thông minh
**Nhóm:** 3 người; tình huống xuyên suốt là phòng lab nhỏ **giả định** có camera IP, cảm biến, ổ cắm thông minh, access point (AP), router/firewall, laptop/điện thoại và máy chủ quản lý.
**Nguyên tắc trình bày:** Slide là phần nhìn; đọc **ý chính và giải thích hình**, không đọc lại từng nhãn trên màn hình. Các log trong slide là **dữ liệu minh họa**, không phải kết quả thực nghiệm.

## Phân chia thời gian

| Người | Slide | Mốc thời gian | Tổng | Phần phụ trách |
| --- | --- | --- | ---: | --- |
| 1 | 1–9 | 00:00–06:00 | 6 phút | Bối cảnh, thiết bị, rủi ro |
| 2 | 10–17 | 06:00–13:00 | 7 phút | WPA2/WPA3, phân đoạn, ACL |
| 3 | 18–23 | 13:00–20:00 | 7 phút | Log, kịch bản kiểm tra, kết luận |

**Nhịp nói:** Người 1 chuyển slide nhanh (khoảng 30–50 giây/slide); người 2 khoảng 40–65 giây; người 3 khoảng 55–80 giây. Các mốc dưới đây cộng đúng 20 phút. Hỏi đáp để sau phần trình bày.

## Người 1 — Mô hình và rủi ro (00:00–06:00)

### Slide 1 — Camera Wi-Fi bị xâm nhập có thể mở đường vào mạng? (00:00–00:35)

**Nhìn hình:** Camera và đường đi tiềm năng về phía mạng người dùng.

**Lời nói gợi ý:**

> Chào thầy cô và các bạn. Nhóm em trình bày về bảo mật Wi-Fi trong môi trường IoT. Hãy hình dung một camera trong phòng lab bị chiếm quyền vì cấu hình yếu hoặc firmware cũ. Lúc đó rủi ro không dừng ở hình ảnh camera: nó có thể trở thành điểm xuất phát để tìm các máy khác. Nhóm em sẽ dùng chính camera này làm ví dụ xuyên suốt bài.

**Thông điệp:** Cần xét cả thiết bị lẫn đường đi của nó trong mạng.

### Slide 2 — Hôm nay chúng ta trả lời 3 câu hỏi (00:35–01:05)

**Nhìn hình:** Ba cụm câu hỏi rủi ro, thiết kế, kiểm tra.

**Lời nói gợi ý:**

> Bài trình bày có ba phần. Thứ nhất, thiết bị IoT có những điểm yếu nào và chúng biến thành rủi ro mạng ra sao? Thứ hai, Wi-Fi, phân đoạn mạng và firewall cần phối hợp thế nào? Thứ ba, làm sao kiểm tra rằng luồng nguy hiểm bị chặn, còn chức năng hợp lệ vẫn chạy? Mỗi phần đều quay lại cùng mô hình phòng lab.

### Slide 3 — Phòng lab giả định có 6 loại thiết bị (01:05–01:50)

**Nhìn hình:** Chỉ trực tiếp từng ảnh và nhãn: AP, router/firewall, camera, cảm biến, ổ cắm, laptop, server.

**Lời nói gợi ý:**

> Đây là các thành phần của mô hình giả định. Access point cung cấp kết nối Wi-Fi. Router/firewall điều phối và kiểm soát lưu lượng giữa các vùng mạng. Camera, cảm biến và ổ cắm là thiết bị IoT; laptop và điện thoại đại diện người dùng; server quản lý nhận dữ liệu và lệnh điều khiển. Chúng em chưa gắn mẫu hoặc hãng cụ thể, nên các khả năng như hỗ trợ WPA3 hay dịch vụ cloud sẽ phải xác minh theo thiết bị thực tế.

**Lưu ý trước khi thuyết trình:** Kiểm tra ảnh từng thiết bị trên slide. Ảnh ở **slide 4** từng được Canva gắn metadata không khớp với AP; cần thay bằng ảnh AP đúng nếu ảnh đang hiển thị sai.

### Slide 4 — Access point là điểm kết nối Wi-Fi (01:50–02:30)

**Nhìn hình:** Ảnh AP bên trái, camera/điện thoại kết nối tới AP bên phải.

**Lời nói gợi ý:**

> AP là thiết bị cho camera và điện thoại kết nối vào mạng không dây. Trong thuật ngữ WLAN, các thiết bị kết nối được gọi là station. SSID là tên mạng Wi-Fi mà chúng nhìn thấy khi chọn kết nối. AP đưa lưu lượng của station vào phần mạng phía sau, nhưng việc một station được phép truy cập server hay laptop phụ thuộc cấu hình mạng và firewall, không chỉ phụ thuộc tên Wi-Fi.

### Slide 5 — Camera, cảm biến, ổ cắm là station IoT (02:30–03:10)

**Nhìn hình:** Ba ảnh thiết bị riêng biệt, tên đặt bên dưới.

**Lời nói gợi ý:**

> Ba thiết bị IoT này có chức năng khác nhau. Camera truyền hình ảnh; cảm biến gửi giá trị đo hoặc sự kiện; ổ cắm nhận lệnh bật tắt nguồn. Vì chức năng khác nhau, mỗi thiết bị cũng có nhu cầu liên lạc khác nhau. Ta không nên mặc định tất cả đều được truy cập cùng một danh sách đích, hoặc đều có cùng khả năng bảo mật Wi-Fi.

### Slide 6 — Thiết bị trao đổi dữ liệu qua nhiều đích (03:10–03:50)

**Nhìn hình:** Theo mũi tên camera → AP → server, điện thoại → server, IoT → máy chủ cập nhật.

**Lời nói gợi ý:**

> Một camera không chỉ cần kết nối được với AP. Nó có thể gửi dữ liệu về server quản lý, nhận lệnh từ ứng dụng thông qua server, và đôi khi phải kết nối đến nơi cung cấp bản cập nhật. Mỗi luồng cần biết nguồn là ai, đích là ai, và mục đích gì. Danh sách luồng hợp lệ này là cơ sở để viết ACL và sau đó nhận ra đích lạ.

### Slide 7 — Bốn điểm yếu tạo ra bề mặt tấn công (03:50–04:35)

**Nhìn hình:** Bốn mục: mật khẩu mặc định, firmware cũ, xác thực yếu, dịch vụ mở.

**Lời nói gợi ý:**

> Mật khẩu quản trị mặc định có thể cho người lạ vào giao diện cấu hình. Firmware cũ có thể giữ lại lỗ hổng đã biết. Xác thực yếu làm người không được phép vẫn có thể điều khiển thiết bị. Dịch vụ mạng không cần thiết nhưng vẫn mở tạo thêm cửa để tấn công. Mật khẩu quản trị thiết bị và mật khẩu Wi-Fi là hai thứ khác nhau; đổi một thứ không tự động giải quyết thứ còn lại.

**Nguồn cho ý này:** OWASP IoT Top 10 (2018), NISTIR 8259.

### Slide 8 — Một camera bị chiếm quyền có thể dò laptop (04:35–05:20)

**Nhìn hình:** Ba bước camera bị chiếm → đi qua mạng → dò laptop.

**Lời nói gợi ý:**

> Đây là kịch bản giả định để đánh giá thiết kế. Nếu camera bị chiếm quyền, kẻ tấn công có thể thử tìm và kết nối tới laptop của người dùng. Nếu không có quy tắc chặn phù hợp, một thiết bị IoT yếu có thể mở rộng ảnh hưởng sang vùng người dùng. Chúng em không khẳng định chỉ cần camera bị chiếm là chắc chắn laptop bị chiếm; điều cần kiểm tra là camera có đường kết nối tới laptop hay không.

### Slide 9 — Ba mục tiêu phòng vệ (05:20–06:00)

**Nhìn hình:** Ba biểu tượng: thiết bị, firewall, dashboard.

**Lời nói gợi ý:**

> Từ rủi ro đó, nhóm đặt ba mục tiêu. Một là giảm khả năng camera bị xâm nhập bằng cấu hình an toàn và cập nhật. Hai là giới hạn đường đi: nếu camera gặp sự cố, nó không được chủ động truy cập laptop. Ba là phát hiện sai lệch bằng log và cảnh báo. Phần tiếp theo sẽ đặt từng biện pháp vào đúng vị trí trong kiến trúc mạng.

**Câu bàn giao:** “Mời bạn thứ hai trình bày thiết kế bảo vệ Wi-Fi và kiểm soát truy cập.”

## Người 2 — Thiết kế bảo vệ (06:00–13:00)

### Slide 10 — WPA2/WPA3 bảo vệ kết nối thiết bị với AP (06:00–06:50)

**Nhìn hình:** Thiết bị ↔ AP có biểu tượng khóa.

**Lời nói gợi ý:**

> Lớp đầu tiên là kết nối không dây. WPA2-Personal dùng cơ chế PSK, còn WPA3-Personal dùng SAE cho quá trình xác thực. Đây là các cơ chế bảo vệ liên kết giữa station và AP. Khi camera truyền dữ liệu qua Wi-Fi, cấu hình bảo mật phù hợp giúp giảm rủi ro ở chặng vô tuyến. Tuy nhiên, mức bảo vệ thực tế phụ thuộc thiết bị và cấu hình mà nó đã dùng để kết nối.

### Slide 11 — WPA3 không vá firmware camera (06:50–07:35)

**Nhìn hình:** Bên trái Wi-Fi có khóa; bên phải firmware cần cập nhật.

**Lời nói gợi ý:**

> Một điểm rất dễ nhầm là cho rằng dùng WPA3 thì camera đã an toàn toàn diện. WPA3 cải thiện bảo vệ kết nối Wi-Fi, nhưng không sửa lỗi trong firmware, không đổi mật khẩu quản trị mặc định và không tắt dịch vụ ứng dụng yếu. Vì vậy chúng ta vẫn phải cập nhật firmware, dùng mật khẩu riêng và kiểm tra cấu hình của thiết bị.

### Slide 12 — Thiết bị cũ cần được kiểm kê theo khả năng Wi-Fi (07:35–08:20)

**Nhìn hình:** Camera, cảm biến, ổ cắm; dưới mỗi ảnh là ghi chú “cần kiểm tra mẫu thực tế”.

**Lời nói gợi ý:**

> Trong IoT, không thể giả định mọi thiết bị đều hỗ trợ WPA3. Một số thiết bị cũ chỉ có WPA2. Nhóm cần lập bảng kiểm kê theo từng mẫu: hỗ trợ chuẩn nào, firmware hiện tại là gì, có cập nhật được không, và đang thực sự kết nối bằng chuẩn nào. Nếu AP bật chế độ hỗn hợp WPA2/WPA3, điều đó vẫn không có nghĩa mọi thiết bị đang được bảo vệ ở mức WPA3.

### Slide 13 — Tách mạng thành ba vùng (08:20–09:15)

**Nhìn hình:** Chỉ lần lượt vùng người dùng, vùng IoT, vùng server, rồi router/firewall ở giữa.

**Lời nói gợi ý:**

> Kiến trúc đề xuất có ba vùng. Laptop và điện thoại thuộc vùng người dùng; camera, cảm biến và ổ cắm thuộc vùng IoT; server quản lý ở vùng riêng. SSID và VLAN giúp phân nhóm kết nối. Khi lưu lượng đi giữa các vùng, router/firewall là nơi áp dụng ACL và ghi log. Chỉ tạo hai tên Wi-Fi khác nhau chưa chứng minh được rằng hai vùng đã bị cô lập; cần cấu hình AP, switch và router nhất quán.

### Slide 14 — Firewall quyết định đường nào được đi qua (09:15–10:05)

**Nhìn hình:** Camera → server màu xanh; camera → laptop màu đỏ.

**Lời nói gợi ý:**

> Camera cần gửi dữ liệu tới server, nên luồng đó được cho phép theo đúng dịch vụ. Nhưng camera không có lý do nghiệp vụ để chủ động mở kết nối tới laptop người dùng, nên firewall sẽ chặn. Đây là ý nghĩa chính của phân đoạn: khi camera bị chiếm quyền, nó không tự do di chuyển sang vùng người dùng. Việc chặn phải được kiểm tra bằng kết nối thử và log, không chỉ nhìn vào sơ đồ.

### Slide 15 — ACL định nghĩa nguồn, đích và hành động (10:05–11:10)

**Nhìn hình:** Bảng bốn hàng; chỉ nói các hàng quan trọng, không đọc mọi ô.

**Lời nói gợi ý:**

> ACL là bộ quy tắc quyết định lưu lượng nào được đi qua. Người dùng tới server quản lý được phép để xem và điều khiển. IoT tới server được phép đúng dịch vụ để gửi dữ liệu. IoT tới laptop bị chặn. IoT tới đích Internet chưa biết phải được xem xét. Đây mới là chính sách mẫu: khi triển khai thật, nhóm cần xác định thêm địa chỉ, giao thức, cổng và chiều kết nối của từng thiết bị.

### Slide 16 — Chỉ mở đúng dịch vụ thiết bị cần (11:10–12:00)

**Nhìn hình:** Đích hợp lệ màu xanh, đích lạ màu vàng.

**Lời nói gợi ý:**

> Việc camera cần cập nhật không có nghĩa phải cho nó truy cập toàn bộ Internet. Ta cần xác định đích cập nhật hoặc dịch vụ cloud thực sự cần thiết, rồi giới hạn theo đích và dịch vụ phù hợp. Nếu xuất hiện một đích mới, ta đưa vào diện xác minh: có thể là chức năng hợp lệ, cũng có thể là bất thường. Không nên đoán một số cổng cụ thể trước khi đối chiếu tài liệu và quan sát thiết bị thật.

### Slide 17 — Bốn lớp phòng vệ phối hợp (12:00–13:00)

**Nhìn hình:** Thiết bị → Wi-Fi → mạng → vận hành.

**Lời nói gợi ý:**

> Tóm lại, lớp thiết bị gồm đổi mật khẩu, cập nhật firmware và tắt dịch vụ thừa. Lớp Wi-Fi dùng cấu hình WPA2/WPA3 phù hợp, mật khẩu mạnh và quản lý khả năng của từng station. Lớp mạng dùng VLAN, firewall và ACL để giới hạn đường đi. Lớp vận hành dùng kiểm kê, log và xử lý cảnh báo. Bốn lớp phải phối hợp vì một lớp riêng lẻ không giải quyết toàn bộ rủi ro. Phần cuối sẽ xem có thể kiểm tra thiết kế này như thế nào.

**Câu bàn giao:** “Mời bạn thứ ba trình bày log và ba kịch bản đánh giá.”

## Người 3 — Giám sát, kiểm tra và kết luận (13:00–20:00)

### Slide 18 — Log là bằng chứng để kiểm tra thiết kế (13:00–14:05)

**Nhìn hình:** Dashboard log; chỉ rõ dòng ALLOW, DENY, REVIEW và nhãn “Dữ liệu minh họa”.

**Lời nói gợi ý:**

> Sơ đồ chỉ thể hiện ý định thiết kế; log mới cho thấy hệ thống thực sự xử lý luồng thế nào. Trong bảng minh họa, camera tới server là ALLOW, camera tới laptop là DENY, còn kết nối tới đích lạ là REVIEW. AP/router cho biết thiết bị nào vào mạng; firewall cho biết nguồn, đích và quyết định; server cho biết camera có còn hoạt động. Đây là dữ liệu minh họa để giải thích tiêu chí kiểm tra, chưa phải log từ thí nghiệm của nhóm.

### Slide 19 — Kịch bản 1: Camera không được truy cập laptop (14:05–15:15)

**Nhìn hình:** Camera → firewall → laptop, mũi tên đỏ DENY.

**Lời nói gợi ý:**

> Kịch bản đầu tiên kiểm tra giới hạn đường đi. Từ mạng IoT, thử mở kết nối đến laptop ở mạng người dùng; nếu không thao tác trực tiếp trên camera được, có thể dùng một máy mô phỏng ở cùng vùng IoT. Kết quả kỳ vọng là kết nối không thành công, firewall ghi log chặn với thời gian, nguồn, đích và quy tắc tương ứng. Nếu kết nối thành công, chính sách chưa đạt mục tiêu và phải kiểm tra lại VLAN, định tuyến hoặc ACL.

**Tiêu chí đạt:** Kết nối IoT → laptop thất bại **và** có log chặn phù hợp.

### Slide 20 — Chặn luồng xấu nhưng giữ luồng tốt (15:15–16:15)

**Nhìn hình:** Một đường đỏ camera → laptop; hai đường xanh điện thoại → server và camera → server.

**Lời nói gợi ý:**

> Chặn được kết nối tới laptop vẫn chưa đủ. Một chính sách quá chặt có thể làm camera hoặc ứng dụng quản lý ngừng hoạt động. Vì vậy sau khi kiểm tra đường bị chặn, nhóm còn phải kiểm tra camera vẫn gửi dữ liệu tới server, và điện thoại vẫn truy cập server để xem hoặc điều khiển. Chỉ khi cả luồng bị cấm lẫn luồng hợp lệ đều cho kết quả đúng, ACL mới đáp ứng yêu cầu của mô hình.

### Slide 21 — Kịch bản 2: Camera đi tới đích lạ (16:15–17:30)

**Nhìn hình:** Camera → đích Internet có dấu hỏi; phát hiện → xác minh → cô lập nếu cần.

**Lời nói gợi ý:**

> Kịch bản thứ hai kiểm tra khả năng phát hiện. Nếu camera kết nối tới một đích Internet chưa nằm trong danh sách đã duyệt, firewall hoặc công cụ giám sát cần ghi nhận thời điểm, đích và lượng lưu lượng. Nhưng đích mới không tự chứng minh có tấn công: đó có thể là máy chủ cập nhật hợp lệ. Người quản trị cần đối chiếu tài liệu, cấu hình và hoạt động thực tế. Nếu không giải thích được, có thể tạm giới hạn kết nối, cô lập thiết bị và điều tra sâu hơn.

### Slide 22 — Kịch bản 3: Firmware cũ và mật khẩu mặc định (17:30–18:40)

**Nhìn hình:** Kiểm kê → cập nhật/đổi mật khẩu → kiểm tra lại.

**Lời nói gợi ý:**

> Kịch bản thứ ba tập trung vào bản thân thiết bị. Trước tiên kiểm kê mẫu thiết bị, phiên bản firmware và trạng thái tài khoản quản trị. Sau đó cập nhật từ nguồn chính thức, đổi mật khẩu mặc định và tắt dịch vụ không cần dùng. Cuối cùng phải xác nhận phiên bản, đăng nhập lại bằng thông tin mới và thử chức năng chính. Nếu thiết bị không còn được hỗ trợ cập nhật, cân nhắc cô lập nghiêm ngặt hơn hoặc thay thế.

### Slide 23 — Cho phép đúng luồng. Quan sát sai lệch. (18:40–20:00)

**Nhìn hình:** Sơ đồ tổng hợp IoT → AP → firewall → server và dashboard.

**Lời nói gợi ý:**

> Qua ba kịch bản, nhóm rút ra rằng bảo vệ IoT không nằm ở một tính năng duy nhất. WPA2/WPA3 bảo vệ liên kết Wi-Fi, nhưng không vá firmware. VLAN và ACL giới hạn đường đi, nhưng cần khai báo đúng luồng hợp lệ. Log cho thấy sai lệch và giúp điều tra, nhưng cần người xác minh và xử lý. Với phòng lab giả định, ba việc quan trọng nhất là cấu hình thiết bị an toàn, chỉ cho phép đúng nơi cần đến, và quan sát được các hành vi lệch khỏi thiết kế. Nhóm em xin cảm ơn thầy cô và các bạn.

**Nếu còn 10–15 giây:** Chỉ vào ba nhãn cuối trên slide: **cấu hình an toàn — giới hạn đường đi — giám sát và xử lý**.

## Bảng nhắc nhanh khi tập dượt

| Mốc | Slide cần đạt | Nếu bị trễ |
| --- | ---: | --- |
| 03:00 | Đã xong slide 4–5 | Rút ngắn thuật ngữ station/SSID |
| 06:00 | Xong slide 9, đổi người | Gộp thông điệp slide 8–9 trong 20 giây |
| 09:00 | Đang slide 13 | Bỏ diễn giải lại từng ảnh thiết bị |
| 13:00 | Xong slide 17, đổi người | Nói tóm tắt bốn lớp trong một câu |
| 16:00 | Xong slide 20 | Giữ tiêu chí kiểm tra, giảm lời dẫn |
| 20:00 | Xong slide 23 | Không mở rộng phần kết luận |

**Khi tập:** Bật đồng hồ, mỗi người tập hai lần. Lần thứ nhất đo thời gian thực; lần thứ hai cắt câu thừa. Người sau bắt đầu ngay khi người trước bàn giao, không lặp lại lời chào hoặc tên đề tài.

## Câu hỏi dự phòng

1. **Vì sao không chỉ dùng WPA3?** Vì WPA3 bảo vệ kết nối không dây; firmware, tài khoản quản trị, ứng dụng và luồng giữa các vùng mạng vẫn cần biện pháp riêng.
2. **Thiết bị cũ chỉ dùng WPA2 thì sao?** Kiểm kê rõ, cấu hình WPA2 an toàn phù hợp thiết bị, cô lập vùng IoT và giới hạn ACL; cân nhắc thay thiết bị nếu hết hỗ trợ.
3. **VLAN có tự chặn IoT sang laptop?** VLAN phân vùng; quy tắc định tuyến và ACL/firewall giữa các vùng quyết định luồng nào đi qua.
4. **Đích lạ có chắc là mã độc?** Không. Đó là tín hiệu cần kiểm tra với tài liệu, chức năng và log của thiết bị.
5. **Log minh họa có phải kết quả thực nghiệm?** Không. Chúng thể hiện dữ liệu cần quan sát và kết quả kỳ vọng; chỉ nhận là kết quả thực nghiệm nếu nhóm có triển khai và thu log thật.

## Tài liệu tham khảo chính

- [OWASP IoT Top 10 (2018)](https://owasp.org/projects/Internet-of-things?tab=seek-and-understand) — nhóm rủi ro IoT.
- [NISTIR 8259 Series](https://www.nist.gov/itl/applied-cybersecurity/nist-cybersecurity-iot-program/nistir-8259-series) — năng lực bảo mật thiết bị IoT.
- [NIST SP 1800-15](https://csrc.nist.gov/pubs/sp/1800/15/final) — kiểm soát luồng thiết bị IoT.
- [Wi-Fi Alliance: Wi-Fi CERTIFIED WPA3](https://www.globenewswire.com/news-release/2018/06/26/1529297/0/en/Wi-Fi-Alliance-introduces-Wi-Fi-CERTIFIED-WPA3-security.html) và [Android Open Source Project: WPA3/SAE](https://source.android.com/docs/core/connect/wifi-wpa3-owe) — cơ chế WPA3.
- [RFC 8520: Manufacturer Usage Description](https://www.rfc-editor.org/info/rfc8520/) — tham khảo khi mô tả luồng mạng hợp lệ.
