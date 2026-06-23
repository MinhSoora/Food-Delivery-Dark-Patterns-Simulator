# Food Delivery Dark Patterns Simulator

## Nguồn gốc dự án

Food Delivery Dark Patterns Simulator là một dự án mô phỏng tương tác được xây dựng dựa trên một bài đăng lan truyền rộng rãi trên internet, trong đó tác giả tự nhận là một kỹ sư backend từng làm việc cho một nền tảng giao đồ ăn lớn. Bài đăng mô tả những cơ chế nội bộ mà tác giả cho rằng đã được sử dụng để tối ưu hóa lợi nhuận của doanh nghiệp bằng cách khai thác các hành vi tâm lý của khách hàng cũng như dữ liệu hoạt động của tài xế giao hàng.

Theo nội dung bài đăng, những gì người dùng và tài xế nhìn thấy trên giao diện ứng dụng chỉ là lớp bề mặt của một hệ thống phức tạp hơn rất nhiều ở phía sau. Tác giả cho rằng nhiều tính năng được quảng bá là nhằm cải thiện trải nghiệm người dùng thực chất được thiết kế để tăng doanh thu hoặc giảm chi phí vận hành cho công ty.

Bài đăng này chưa được xác minh độc lập và không có bằng chứng công khai xác nhận danh tính tác giả hoặc công ty được nhắc tới. Tuy nhiên, nội dung của nó đã thu hút sự chú ý lớn vì mô tả chi tiết cách các thuật toán có thể được sử dụng để điều hướng hành vi kinh tế của người lao động nền tảng và người tiêu dùng.

Dự án này không nhằm khẳng định bất kỳ công ty cụ thể nào đã hoặc đang áp dụng các cơ chế được mô tả. Thay vào đó, nó sử dụng các ý tưởng trong bài viết như một tình huống giả định để giúp người xem hiểu rõ hơn về các khái niệm như thuật toán phân phối đơn hàng, tối ưu hóa lợi nhuận, thiết kế động lực kinh tế, thao túng hành vi người dùng (behavioral manipulation), dark patterns và các vấn đề đạo đức trong phát triển phần mềm quy mô lớn.

---

## Trích dẫn bài đăng gốc

Bài đăng được sử dụng làm nguồn cảm hứng chính cho dự án mô tả các cáo buộc sau:

> "Priority Delivery" thực chất không làm đơn hàng được giao nhanh hơn.

> Các đơn hàng thông thường bị cố tình làm chậm để tạo cảm giác rằng đơn Priority nhanh hơn.

> Hệ thống tồn tại một chỉ số nội bộ gọi là "Desperation Score" dùng để đánh giá mức độ cần tiền của tài xế.

> Những tài xế bị đánh giá là "tuyệt vọng" sẽ ít được nhận các đơn hàng có thu nhập cao.

> Một số khoản phí được trình bày như nhằm hỗ trợ tài xế thực chất không được chuyển trực tiếp cho tài xế.

> Hệ thống dự đoán khả năng khách hàng tip để giảm mức lương cơ bản phải trả cho tài xế.

Những mô tả này là nền tảng để xây dựng các mô hình và hoạt cảnh trong dự án.

---

## Mục tiêu của dự án

Mục tiêu của Food Delivery Dark Patterns Simulator không phải là tạo ra một ứng dụng giao đồ ăn thực tế mà là mô phỏng những gì có thể xảy ra phía sau một nền tảng giao hàng quy mô lớn nếu các mục tiêu tối đa hóa lợi nhuận được ưu tiên hơn lợi ích của người lao động và người tiêu dùng.

Thông qua các mô hình trực quan, người xem có thể quan sát cách các quyết định tưởng như nhỏ trong thuật toán có thể tạo ra những tác động đáng kể lên:

- Thu nhập của tài xế.
- Chi phí mà khách hàng phải trả.
- Lợi nhuận của công ty.
- Hành vi thị trường.
- Động lực làm việc của người lao động nền tảng.
- Sự minh bạch của các hệ thống công nghệ.

Dự án cũng hướng tới việc giúp sinh viên công nghệ, nhà nghiên cứu UX, nhà nghiên cứu AI, kỹ sư phần mềm và công chúng hiểu rõ hơn về mặt tối tiềm tàng của các hệ thống tối ưu hóa dữ liệu quy mô lớn.

---

## Tổng quan giao diện

Trang web được chia thành hai khu vực chính hoạt động đồng thời.

### Khu vực bên trái: Mô phỏng ứng dụng giao đồ ăn

Phần này hiển thị một chiếc điện thoại ảo mô phỏng trải nghiệm đặt món của khách hàng.

Người dùng có thể:

- Chọn nhà hàng.
- Chọn món ăn.
- Thêm món vào giỏ hàng.
- Chỉnh sửa số lượng.
- Chọn phí giao hàng.
- Bật hoặc tắt Priority Delivery.
- Chọn mức tip.
- Đặt đơn hàng.
- Theo dõi tiến trình giao hàng.

Mọi thao tác tại đây sẽ tác động trực tiếp tới hệ thống mô phỏng phía bên phải.

---

### Khu vực bên phải: Bảng điều khiển thuật toán

Đây là phần quan trọng nhất của dự án.

Thay vì che giấu các quyết định nội bộ như một ứng dụng thật, toàn bộ logic sẽ được hiển thị theo thời gian thực.

Người xem có thể theo dõi:

- Điểm đánh giá tài xế.
- Cách đơn hàng được phân phối.
- Cách lương cơ bản được tính.
- Khoản phí nào đi về phía công ty.
- Khoản phí nào thực sự tới tay tài xế.
- Khoản tiền nào phát sinh từ các chiến lược tối ưu hóa.

Mọi thay đổi đều được biểu diễn bằng biểu đồ, bảng thống kê và hoạt ảnh trực quan.

---

## Mô phỏng Priority Delivery

Một trong những tính năng gây tranh cãi nhất được mô phỏng trong dự án là Priority Delivery.

Trong ứng dụng thực tế, người dùng thường được đề nghị trả thêm một khoản phí để đơn hàng được ưu tiên giao sớm hơn.

Trong mô hình của dự án, người dùng có thể bật hoặc tắt tính năng này và quan sát:

- Phí Priority thu được.
- Thời gian giao hàng dự kiến.
- Thời gian giao hàng thực tế.
- Chênh lệch giữa hai giá trị.

Mô hình sẽ minh họa một kịch bản trong đó hệ thống không thực sự tăng tốc đơn hàng Priority mà thay vào đó làm chậm các đơn hàng thông thường.

Người dùng có thể quan sát cách:

- Trải nghiệm của khách Priority được cải thiện tương đối.
- Chất lượng dịch vụ tiêu chuẩn bị giảm.
- Công ty tăng doanh thu mà không cần tăng chi phí vận hành.

---

## Mô phỏng Desperation Score

Một trong những phần trung tâm của dự án là hệ thống Desperation Score.

Đây là chỉ số giả định phản ánh mức độ sẵn sàng chấp nhận các đơn hàng có thu nhập thấp của tài xế.

Điểm số này được tính dựa trên nhiều yếu tố:

- Tỷ lệ nhận đơn.
- Tỷ lệ từ chối đơn.
- Thời gian hoạt động.
- Tần suất làm việc đêm.
- Mức thu nhập gần đây.
- Thời gian chờ giữa các đơn.

Khi điểm số tăng cao, thuật toán mô phỏng sẽ:

- Giảm xác suất nhận đơn có thu nhập tốt.
- Giảm khả năng tiếp cận khách hàng có tip cao.
- Tăng tần suất xuất hiện các đơn hàng giá thấp.

Người xem có thể quan sát trực tiếp cách thu nhập của tài xế thay đổi theo thời gian chỉ vì sự thay đổi của một chỉ số vô hình.

---

## Mô phỏng Dynamic Base Pay

Phần này mô tả cách một hệ thống dự đoán tiền tip có thể tác động tới mức lương cơ bản.

Mỗi đơn hàng trong mô phỏng đều có:

- Tiền tip thực tế.
- Tiền tip dự đoán.
- Mức lương cơ bản ban đầu.
- Mức lương cơ bản sau điều chỉnh.

Ví dụ:

Nếu hệ thống dự đoán khách hàng sẽ tip nhiều, lương cơ bản có thể bị giảm xuống.

Nếu hệ thống dự đoán khách hàng không tip, lương cơ bản có thể được tăng lên để đảm bảo đơn hàng vẫn được nhận.

Kết quả là:

Tổng số tiền tài xế nhận được có thể giữ nguyên nhưng phần đóng góp của công ty giảm xuống đáng kể.

Dashboard sẽ hiển thị chi tiết số tiền công ty tiết kiệm được từ cơ chế này.

---

## Mô phỏng Driver Benefit Fee

Người dùng có thể bật các loại phí bổ sung như:

- Driver Benefit Fee
- Regulatory Response Fee
- Service Fee
- Platform Fee

Mỗi khoản phí sẽ được hiển thị chi tiết:

- Số tiền khách hàng trả.
- Số tiền tới tay tài xế.
- Số tiền giữ lại bởi công ty.
- Mục đích sử dụng được mô phỏng.

Các luồng tiền sẽ được biểu diễn bằng sơ đồ trực quan để người xem dễ dàng hiểu được dòng chảy tài chính của toàn hệ thống.

---

## Dashboard tài chính thời gian thực

Trang web liên tục cập nhật:

- Doanh thu công ty.
- Thu nhập tài xế.
- Tổng tiền tip.
- Tổng phí dịch vụ.
- Tổng phí Priority.
- Tổng phí Benefit.
- Tiền tiết kiệm từ Dynamic Base Pay.
- Tiền tiết kiệm từ Desperation Score.
- Lợi nhuận ròng mô phỏng.

Người dùng có thể chạy mô phỏng trong nhiều giờ hoặc nhiều ngày ảo để xem ảnh hưởng tích lũy của các thuật toán.

---

## Biểu đồ và trực quan hóa

Dự án sử dụng nhiều loại biểu đồ:

- Revenue Breakdown.
- Driver Income Distribution.
- Company Profit Growth.
- Order Dispatch Flow.
- Priority Fee Revenue.
- Benefit Fee Allocation.
- Driver Desperation Distribution.
- Base Pay Reduction Heatmap.

Các biểu đồ được cập nhật theo thời gian thực khi mô phỏng đang hoạt động.

---

## Giá trị giáo dục

Dự án được thiết kế để hỗ trợ việc học tập và nghiên cứu trong các lĩnh vực:

- Software Engineering
- Platform Economics
- Marketplace Design
- Human Computer Interaction
- Data Science
- Algorithmic Management
- Digital Labor Platforms
- Behavioral Economics
- Dark Pattern Design
- AI Driven Optimization Systems
- Ethics in Technology

---

## Tuyên bố miễn trừ trách nhiệm

Dự án là một mô hình giáo dục và nghiên cứu.

Nội dung mô phỏng dựa trên các cáo buộc được nêu trong một bài đăng công khai trên internet và không được xác minh độc lập.

Không có phần nào của dự án được hiểu là bằng chứng cho thấy bất kỳ công ty cụ thể nào đang áp dụng các cơ chế được mô tả.

Mọi thuật toán, biểu đồ, số liệu và hoạt cảnh trong hệ thống đều được xây dựng nhằm minh họa cách các hệ thống tối ưu hóa lợi nhuận có thể hoạt động trong một kịch bản giả định.

Mục tiêu cuối cùng của dự án là khuyến khích tư duy phản biện về tính minh bạch, trách nhiệm giải trình và đạo đức trong việc thiết kế các nền tảng công nghệ quy mô lớn.
