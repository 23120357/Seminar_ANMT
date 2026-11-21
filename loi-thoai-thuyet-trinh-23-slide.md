# Lời thoại thuyết trình 23 slide — bản nói cho người mới bắt đầu

**Deck Canva:** [Bảo mật Wi-Fi IoT — 23 slide](https://canva.link/iz6qvhl54eh5e6w)
**Thời lượng:** 20 phút, 3 người.
**Cách dùng:** Đây là lời thoại để **tập nói**, không đưa nguyên văn lên slide. Chữ trong ngoặc vuông là chỉ dẫn sân khấu; không đọc thành tiếng. Sau khi tập quen, có thể diễn đạt bằng lời của mình nhưng giữ các ý kỹ thuật và mốc thời gian. Tốc độ nói vừa phải, dừng ngắn sau câu quan trọng.

> **Lưu ý trung thực:** Phòng lab, camera và các dòng log trong bài là tình huống minh họa. Đừng nói “nhóm đã kiểm thử và thu được kết quả” nếu chưa có hệ thống và log thật. Trước buổi báo cáo, kiểm tra lại ảnh ở slide 4: ảnh access point cần đúng thiết bị.

## Người 1 — Kéo người nghe vào câu chuyện (00:00–06:00)

### Slide 1 — Camera Wi-Fi bị xâm nhập có thể mở đường vào mạng? (00:00–00:35)

**Cách thể hiện:** Mở bằng tình huống, không đọc tên đề tài ngay. Nhìn khán giả ở câu hỏi cuối.

> Mọi người thử tưởng tượng trong phòng lab của mình có một chiếc camera Wi-Fi. Bình thường nó chỉ quay hình và gửi dữ liệu về máy chủ. Một hôm, vì mật khẩu quản trị còn mặc định hoặc firmware quá cũ, camera bị người lạ kiểm soát. Câu hỏi là: chuyện đó có dừng ở chiếc camera không, hay nó còn có thể gây rắc rối cho laptop của chúng ta? Đó là vấn đề nhóm mình muốn giải thích hôm nay: bảo mật Wi-Fi cho IoT không chỉ là đặt một mật khẩu Wi-Fi thật dài.

**Nhấn câu:** “Chuyện đó có dừng ở chiếc camera không?”

### Slide 2 — Hôm nay chúng ta trả lời 3 câu hỏi (00:35–01:05)

**Cách thể hiện:** Chỉ lần lượt ba cụm trên slide; mỗi cụm một câu.

> Để dễ theo dõi, mình sẽ đi theo ba câu hỏi. Một: thiết bị IoT yếu ở đâu, và vì sao một lỗi nhỏ có thể thành rủi ro cho cả mạng? Hai: mình tổ chức Wi-Fi và firewall thế nào để camera làm đúng việc của nó nhưng không đi lung tung? Ba: sau khi cấu hình xong, lấy gì chứng minh chính sách đang hoạt động? Cả bài sẽ dùng chung một phòng lab giả định, nên mọi người không phải nhớ nhiều mô hình khác nhau.

### Slide 3 — Phòng lab giả định có 6 loại thiết bị (01:05–01:50)

**Cách thể hiện:** Trỏ vào ảnh theo thứ tự từ hạ tầng đến người dùng; không đọc nhãn theo hàng ngang một cách máy móc.

> Đầu tiên là các nhân vật trong câu chuyện. Đây là access point, thiết bị phát mạng Wi-Fi để camera và điện thoại kết nối. Bên cạnh là router hoặc firewall, giống như chốt kiểm soát khi dữ liệu muốn đi từ khu vực này sang khu vực khác. Camera, cảm biến và ổ cắm là nhóm IoT: chúng thu hình, đo môi trường hoặc nhận lệnh bật tắt. Laptop và điện thoại là nhóm người dùng; server là nơi quản lý thiết bị. Những hình này giúp mình hình dung vai trò, chưa đại diện một mẫu sản phẩm cụ thể. Vì vậy lát nữa nói đến WPA3 hay cổng mạng, mình sẽ không tự gán thông số cho chúng.

**Câu nối:** “Giờ ta nhìn kỹ vào điểm mà các thiết bị không dây gặp nhau.”

### Slide 4 — Access point là điểm kết nối Wi-Fi (01:50–02:30)

**Cách thể hiện:** Chỉ ảnh AP trước, sau đó vẽ bằng tay một đường tưởng tượng từ camera tới AP.

> Access point, gọi tắt là AP, là điểm mà thiết bị không dây bám vào để vào mạng. Camera và điện thoại ở đây được gọi là station. Còn SSID đơn giản là tên Wi-Fi mà mình thấy trong danh sách kết nối, ví dụ “Lab-IoT”. Nhưng có một chỗ dễ nhầm: kết nối được vào AP mới chỉ là bước đầu. Camera có được đi đến server hay laptop hay không còn phụ thuộc mạng phía sau và quy tắc của firewall. Nói ngắn gọn, AP là cửa vào Wi-Fi; nó không tự quyết định mọi quyền đi lại trong tòa nhà.

**Ví dụ đời thường:** AP là cửa vào; firewall là nơi kiểm tra bạn được sang phòng nào.

### Slide 5 — Camera, cảm biến, ổ cắm là station IoT (02:30–03:10)

**Cách thể hiện:** Mỗi ảnh một động từ: camera “gửi hình”, cảm biến “báo sự kiện”, ổ cắm “nhận lệnh”.

> Ba thiết bị này đều thuộc IoT, nhưng cách hoạt động không giống nhau. Camera thường tạo ra luồng hình ảnh. Cảm biến có thể chỉ thỉnh thoảng báo một giá trị nhiệt độ hoặc sự kiện chuyển động. Ổ cắm thông minh lại chủ yếu nhận lệnh bật tắt và báo trạng thái. Chính vì khác chức năng, nhu cầu kết nối mạng của chúng cũng khác. Nếu mình cho cả ba quyền truy cập mọi nơi như nhau, mình đang mở thêm đường mà chúng không cần để làm việc.

**Câu nối:** “Vậy những đường kết nối nào thực sự cần thiết?”

### Slide 6 — Thiết bị trao đổi dữ liệu qua nhiều đích (03:10–03:50)

**Cách thể hiện:** Dẫn mắt theo mũi tên trên sơ đồ, tránh đọc từng nhãn.

> Ta xem đường đi bình thường. Camera kết nối tới AP rồi gửi dữ liệu về server quản lý. Người dùng mở điện thoại để xem hoặc điều khiển qua server. Đôi khi thiết bị còn cần liên lạc với máy chủ cập nhật của nhà sản xuất. Nếu viết ra thành danh sách, mỗi dòng sẽ có ba câu hỏi: ai gửi, gửi tới đâu và để làm gì? Danh sách đó rất quan trọng. Nó giúp mình viết quy tắc cho phép đúng luồng, đồng thời nhận ra khi camera bỗng liên lạc với một nơi chưa từng được duyệt.

### Slide 7 — Bốn điểm yếu tạo ra bề mặt tấn công (03:50–04:35)

**Cách thể hiện:** Nói theo chuỗi nguyên nhân → cơ hội tấn công, không đọc bốn ô như đọc danh sách.

> Bây giờ xét vì sao camera có thể trở thành vấn đề. Mật khẩu quản trị mặc định giống như ổ khóa mà nhiều người biết chìa. Firmware cũ là phần mềm thiết bị chưa được vá khi có lỗi. Xác thực yếu có thể cho người không có quyền thực hiện lệnh. Dịch vụ mở không cần thiết thì giống một cánh cửa ít ai dùng nhưng vẫn để mở. Lưu ý, mật khẩu đăng nhập camera và mật khẩu Wi-Fi là hai lớp khác nhau. Đổi mật khẩu Wi-Fi không làm mật khẩu quản trị camera tự mạnh lên.

**Nói chính xác:** Đây là những **nhóm rủi ro có thể gặp**, không phải khẳng định cả bốn đều có trên camera minh họa.

### Slide 8 — Một camera bị chiếm quyền có thể dò laptop (04:35–05:20)

**Cách thể hiện:** Kể như một câu chuyện ba bước; dừng ngắn trước bước cuối.

> Giả sử điểm yếu ở camera đã bị khai thác. Bước một, người lạ điều khiển được camera. Bước hai, camera đang là một thiết bị hợp lệ ở trong mạng, nên nó có thể thử gửi các kết nối khác với mục đích ban đầu. Bước ba, nó thử tìm laptop ở mạng người dùng. Điều mình lo ở đây là **đường truy cập**, chứ không khẳng định cứ thấy laptop là chiếm được laptop. Nếu camera không có lý do nào để nói chuyện trực tiếp với laptop, thiết kế tốt sẽ chặn đường đó ngay từ đầu.

### Slide 9 — Ba mục tiêu phòng vệ (05:20–06:00)

**Cách thể hiện:** Gom toàn bộ phần mình thành ba động từ để bàn giao tự nhiên.

> Từ câu chuyện trên, nhóm đặt ba mục tiêu. Thứ nhất là **giảm** khả năng bị chiếm quyền: đổi mật khẩu, cập nhật, tắt thứ không cần. Thứ hai là **giới hạn** thiệt hại: nếu camera gặp sự cố, nó vẫn không được tự đi sang laptop. Thứ ba là **phát hiện**: nếu camera đi tới đích lạ hoặc bị chặn, hệ thống phải để lại dấu vết để người quản trị kiểm tra. Vậy ba mục tiêu này được biến thành cấu hình mạng ra sao? Mình mời bạn thứ hai tiếp tục.

## Người 2 — Giải thích bảo vệ theo từng lớp (06:00–13:00)

### Slide 10 — WPA2/WPA3 bảo vệ kết nối thiết bị với AP (06:00–06:50)

**Cách thể hiện:** Chỉ khoảng giữa camera và AP; nói phạm vi trước rồi mới nêu tên chuẩn.

> Cảm ơn bạn. Đầu tiên ta bảo vệ đoạn không dây giữa camera và AP. Hai tên thường gặp là WPA2-Personal và WPA3-Personal. Với WPA2-Personal, cơ chế phổ biến là PSK, tức khóa chia sẻ trước. WPA3-Personal dùng SAE cho bước xác thực. Với người mới, chưa cần nhớ từng phép toán mật mã; điều cần nhớ là WPA3 cải thiện cách thiết bị xác thực khi vào Wi-Fi. Tuy nhiên, đây là bảo vệ cho **liên kết Wi-Fi**. Sau khi camera đã vào mạng hợp lệ, chuyện nó được đi tới đâu là một câu hỏi khác.

**Tránh nói:** “WPA3 chống được mọi cuộc tấn công.”

### Slide 11 — WPA3 không vá firmware camera (06:50–07:35)

**Cách thể hiện:** So sánh hình ổ khóa Wi-Fi và hình firmware cần cập nhật.

> Nhìn hai nửa slide này. Bên trái, kết nối không dây có khóa. Bên phải, phần mềm bên trong camera vẫn cần cập nhật. Ta có thể tưởng tượng cửa nhà rất chắc, nhưng chiếc máy tính bên trong vẫn chạy phần mềm lỗi thời. Cửa chắc không tự sửa được phần mềm đó. Tương tự, WPA3 không đổi mật khẩu quản trị mặc định và không tắt các dịch vụ yếu của camera. Vì vậy, Wi-Fi an toàn phải đi cùng quản lý thiết bị an toàn.

### Slide 12 — Thiết bị cũ cần được kiểm kê theo khả năng Wi-Fi (07:35–08:20)

**Cách thể hiện:** Chỉ ba ảnh, đặt câu hỏi “thiết bị này hỗ trợ gì?” thay vì khẳng định.

> Trong phòng lab, camera có thể là đời mới nhưng cảm biến hoặc ổ cắm có thể là đời cũ. Mình không thể nhìn hình dáng để kết luận nó hỗ trợ WPA3. Việc đúng là kiểm kê theo mẫu cụ thể: thiết bị hỗ trợ WPA2 hay WPA3, firmware đang ở phiên bản nào, còn được cập nhật không, và trên AP nó thực sự kết nối bằng chuẩn nào. Ngay cả khi bật chế độ WPA2/WPA3 hỗn hợp, một thiết bị chỉ hỗ trợ WPA2 vẫn sẽ dùng WPA2. Vì thế chính sách bảo vệ phải xét từng thiết bị.

### Slide 13 — Tách mạng thành ba vùng (08:20–09:15)

**Cách thể hiện:** Dùng ngón tay khoanh ba vùng trên slide, rồi chỉ vào firewall.

> Tiếp theo là bố trí mạng. Nếu để laptop, camera và server ở một vùng không được kiểm soát, camera có thể thử liên lạc trực tiếp với nhiều thiết bị. Nhóm đề xuất tách ba vùng: người dùng, IoT và server quản lý. SSID và VLAN giúp đưa thiết bị vào đúng vùng. Khi dữ liệu muốn đi từ vùng IoT sang vùng người dùng hoặc server, nó phải qua router/firewall để xét quy tắc. Hình dung như phòng lab có ba khu: việc có tên khu khác nhau chưa đủ; cần cửa kiểm soát giữa các khu và quy định ai được qua.

**Lưu ý kỹ thuật:** VLAN không tự động thay thế ACL; phải kiểm tra cấu hình AP, switch và router.

### Slide 14 — Firewall quyết định đường nào được đi qua (09:15–10:05)

**Cách thể hiện:** Chỉ đường xanh trước, đường đỏ sau.

> Đây là quyết định quan trọng nhất trong mô hình. Camera gửi hình hoặc trạng thái về server: có lý do rõ ràng, nên cho phép theo đúng dịch vụ. Camera chủ động mở kết nối tới laptop: không phục vụ chức năng của camera, nên chặn. Firewall giống người gác cổng hỏi “anh là ai, anh định đi đâu, có lý do gì?”. Nếu camera bị chiếm quyền, quy tắc này giúp hạn chế việc nó dùng mạng nội bộ để dò máy người dùng. Nhưng muốn biết có chặn thật không, lát nữa chúng ta sẽ kiểm tra bằng log.

### Slide 15 — ACL định nghĩa nguồn, đích và hành động (10:05–11:10)

**Cách thể hiện:** Giải thích cách đọc một hàng trước; sau đó chỉ nhanh các hàng còn lại.

> ACL là danh sách quy tắc của firewall. Ta đọc một hàng như sau: **nguồn** là camera IoT, **đích** là server quản lý, **điều kiện** là đúng dịch vụ camera cần, **hành động** là cho phép. Hàng khác: nguồn vẫn là IoT nhưng đích là laptop, hành động là chặn. Với đích Internet chưa biết, ta cần xác minh trước khi mở rộng quyền. Bảng trên slide chỉ là chính sách logic; triển khai thật phải thêm địa chỉ, giao thức, cổng và chiều kết nối. Đừng mở một cổng hoặc một dải Internet chỉ vì thấy thiết bị báo lỗi; hãy tìm luồng hợp lệ cụ thể trước.

### Slide 16 — Chỉ mở đúng dịch vụ thiết bị cần (11:10–12:00)

**Cách thể hiện:** Đối chiếu màu xanh và vàng; nói ví dụ cập nhật firmware.

> Ví dụ camera cần lấy bản cập nhật. Cách dễ nhưng rủi ro là cho camera đi tới mọi địa chỉ Internet. Cách có kiểm soát là xác định máy chủ và giao thức cập nhật mà thiết bị thật sự dùng, rồi chỉ mở những luồng cần thiết. Nếu một ngày camera kết nối tới đích chưa có trong danh sách, màu vàng ở đây có nghĩa là **cần kiểm tra**, không có nghĩa chắc chắn bị tấn công. Có thể nhà sản xuất đổi hạ tầng cập nhật; cũng có thể camera hoạt động sai. Mình cần bằng chứng trước khi kết luận.

### Slide 17 — Bốn lớp phòng vệ phối hợp (12:00–13:00)

**Cách thể hiện:** Đi từ trong ra ngoài; kết bằng một câu dễ nhớ.

> Ta có thể nhìn toàn bộ giải pháp thành bốn lớp. **Thiết bị:** cập nhật, đổi mật khẩu và giảm dịch vụ thừa. **Wi-Fi:** chọn WPA2/WPA3 phù hợp từng thiết bị và dùng thông tin kết nối mạnh. **Mạng:** tách vùng, dùng firewall và ACL để giới hạn đường đi. **Vận hành:** kiểm kê, đọc log và xử lý cảnh báo. Một lớp có thể thất bại, nên các lớp còn lại phải giảm hậu quả. Đến đây, nhóm đã có một thiết kế trên giấy; phần tiếp theo trả lời câu hỏi quan trọng hơn: làm sao biết nó chạy đúng ngoài thực tế? Mời bạn thứ ba.

## Người 3 — Biến thiết kế thành thứ kiểm tra được (13:00–20:00)

### Slide 18 — Log là bằng chứng để kiểm tra thiết kế (13:00–14:05)

**Cách thể hiện:** Chỉ rõ nhãn “DỮ LIỆU MINH HỌA” trước khi đọc ba dòng log.

> Cảm ơn bạn. Khi nhìn sơ đồ, ta biết nhóm **muốn** camera được tới server và không được tới laptop. Nhưng sơ đồ không tự chứng minh firewall đã làm đúng. Vì thế ta xem log. Bảng này là dữ liệu minh họa: dòng đầu camera tới server được cho phép, dòng hai camera tới laptop bị chặn, dòng ba camera tới đích lạ được đưa vào diện xem xét. Một bản log hữu ích cần có thời gian, nguồn, đích và hành động. Nó giúp trả lời câu hỏi rất thực tế: camera đã thử đi đâu, và quy tắc nào đã xử lý kết nối đó?

### Slide 19 — Kịch bản 1: Camera không được truy cập laptop (14:05–15:15)

**Cách thể hiện:** Chỉ ba điểm camera → firewall → laptop, rồi nói kết quả kỳ vọng.

> Kịch bản kiểm tra đầu tiên rất đơn giản: từ vùng IoT, ta thử mở kết nối tới laptop ở vùng người dùng. Nếu camera không có chức năng tạo kết nối thử, có thể dùng một máy mô phỏng đặt trong đúng vùng IoT. Mình kỳ vọng kết nối không thiết lập được và firewall ghi một dòng DENY. Nếu chỉ thấy kết nối thất bại mà không có log, còn phải kiểm tra xem thất bại do firewall hay do lý do khác, ví dụ laptop không mở dịch vụ. Nếu kết nối lại thành công, chính sách chưa đạt: cần kiểm tra VLAN, định tuyến và quy tắc ACL.

**Câu chốt:** “Đạt” nghĩa là **bị chặn đúng chỗ và nhìn thấy bằng chứng chặn**.

### Slide 20 — Chặn luồng xấu nhưng giữ luồng tốt (15:15–16:15)

**Cách thể hiện:** Chỉ đường đỏ, rồi chuyển nhanh sang hai đường xanh.

> Nhưng chúng ta chưa thể ăn mừng chỉ vì camera không tới được laptop. Nếu cấu hình sai, firewall có thể đã chặn cả camera tới server. Khi đó an toàn trên giấy nhưng hệ thống không dùng được. Vì vậy ta kiểm tra thêm hai đường xanh: camera vẫn gửi dữ liệu tới server, điện thoại vẫn vào server để xem hoặc điều khiển. Một chính sách tốt phải thỏa mãn cả hai vế: chặn luồng không có lý do và giữ chức năng bình thường. Đây cũng là cách đánh giá công bằng một biện pháp bảo mật: xem cả tác dụng lẫn ảnh hưởng vận hành.

### Slide 21 — Kịch bản 2: Camera đi tới đích lạ (16:15–17:30)

**Cách thể hiện:** Khi nói “đích lạ”, chỉ dấu hỏi vàng, không dùng giọng khẳng định đã bị tấn công.

> Giả sử log cho thấy camera bỗng kết nối đến một địa chỉ Internet chưa nằm trong danh sách đã duyệt. Ta nên làm gì? Bước một, ghi nhận thời điểm, địa chỉ đích và lượng lưu lượng. Bước hai, đối chiếu với tài liệu và cấu hình camera: có thể đây là máy chủ cập nhật hoặc dịch vụ cloud hợp lệ. Bước ba, nếu vẫn không giải thích được, tạm giới hạn kết nối hoặc cô lập camera để kiểm tra. Điều quan trọng là **đích lạ là tín hiệu để điều tra**, chưa phải bằng chứng chắc chắn của mã độc. Cách nói này giúp tránh báo động sai nhưng vẫn không bỏ qua dấu hiệu đáng chú ý.

### Slide 22 — Kịch bản 3: Firmware cũ và mật khẩu mặc định (17:30–18:40)

**Cách thể hiện:** Nói như một quy trình bảo trì có kiểm tra lại, không chỉ liệt kê biện pháp.

> Kịch bản thứ ba quay về chiếc camera ban đầu. Trước tiên ta kiểm kê mẫu thiết bị, firmware và trạng thái tài khoản quản trị. Nếu firmware cũ, lấy bản cập nhật từ nguồn chính thức; nếu mật khẩu còn mặc định, đổi sang thông tin riêng đủ mạnh. Sau đó kiểm tra lại: phiên bản đã đổi chưa, mật khẩu cũ còn đăng nhập được không, camera còn gửi dữ liệu bình thường không? Bước kiểm tra lại quan trọng vì “đã bấm cập nhật” chưa chắc bằng “đã cập nhật thành công”. Nếu nhà sản xuất không còn hỗ trợ, nhóm phải xem xét cô lập chặt hơn hoặc thay thiết bị.

### Slide 23 — Cho phép đúng luồng. Quan sát sai lệch. (18:40–20:00)

**Cách thể hiện:** Nói chậm hơn ở ba câu cuối; nhìn khán giả thay vì nhìn màn hình.

> Nhìn lại toàn bộ mô hình: camera đi qua AP, mạng được chia vùng, firewall kiểm soát đường sang server hoặc laptop, và log ghi lại những gì đã xảy ra. Không có một nút bấm nào giải quyết hết mọi vấn đề. WPA2/WPA3 bảo vệ kết nối Wi-Fi nhưng không vá firmware. ACL giới hạn đường đi nhưng phải viết đúng nhu cầu của thiết bị. Log giúp phát hiện sai lệch nhưng cần người xác minh và xử lý. Vì vậy, thông điệp cuối cùng của nhóm mình là ba việc rất dễ nhớ: **cấu hình thiết bị an toàn, chỉ cho phép đúng luồng, và quan sát được khi thiết bị làm khác dự kiến**. Với một mạng IoT nhỏ, làm tốt ba việc này sẽ giúp giảm rủi ro rõ rệt mà vẫn giữ thiết bị hoạt động. Nhóm em xin cảm ơn thầy cô và các bạn.

## Mẹo nói để người mới vẫn theo kịp

1. **Nêu tác dụng trước thuật ngữ.** Ví dụ: “thiết bị phát Wi-Fi — gọi là AP”; “danh sách quy tắc cho phép/chặn — gọi là ACL”.
2. **Mỗi slide chỉ có một câu cần nhớ.** Nếu khán giả chỉ nhớ một ý, đó phải là headline của slide.
3. **Chỉ vào hình trước khi giải thích.** Mũi tên xanh là luồng có lý do; đỏ là luồng cần chặn; vàng là luồng phải xác minh.
4. **Dừng 1 giây sau câu chốt.** Đặc biệt ở slide 1, 8, 14, 20 và 23. Đừng lấp khoảng dừng bằng “ừm” hoặc đọc thêm chữ.
5. **Không đọc định nghĩa liên tiếp.** Kể camera làm gì, rồi mới giới thiệu station, AP, SSID, VLAN, ACL khi người nghe đã có hình dung.
6. **Không biến ví dụ thành kết quả nghiên cứu.** Khi chưa có lab thật, dùng “giả sử”, “đề xuất”, “kết quả kỳ vọng”, “cần kiểm tra”.

## Mốc tập dượt bắt buộc

| Đồng hồ | Phải đang ở | Điều chỉnh nếu trễ |
| --- | --- | --- |
| 03:00 | Slide 5–6 | Rút phần giải thích station/SSID |
| 06:00 | Kết thúc slide 9 | Người 1 bàn giao ngay |
| 09:00 | Slide 13–14 | Người 2 nói theo mũi tên, bỏ đọc nhãn |
| 13:00 | Kết thúc slide 17 | Người 2 chốt bốn lớp bằng một câu |
| 16:00 | Kết thúc slide 20 | Người 3 giữ tiêu chí kiểm tra, giảm lời mở |
| 20:00 | Kết thúc slide 23 | Dừng, không kéo dài kết luận |

**Tập ít nhất hai lượt cả nhóm:** Lượt 1 đọc gần nguyên văn để đo thời gian; lượt 2 nói tự nhiên hơn và cắt câu thừa. Nếu tổng quá 20 phút, cắt ví dụ phụ ở slide 3, 7, 11, 16 và 22; giữ nguyên ba kịch bản kiểm tra và kết luận.
