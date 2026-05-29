Danh sách 5+ Bài toán (Problems Scan)

## Bảng Phân tích bài toán

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Tự động hóa Marketing | Phải trả lời bình luận thủ công quá nhiều | Chủ Fanpage/Quản lý cộng đồng | Bình luận chưa được trả lời, khách hàng chờ đợi, tỷ lệ engagement thấp |
| 2 | Quản lý môi trường | Sốc nhiệt/hô hấp xảy ra đột ngột | Chủ trang trại/Gia súc | Gia súc bỏ ăn, cút chết, bệnh tật tăng, chi phí điều trị cao |
| 3 | Điều khiển tự động | Chuồng trại quá nóng/ẩm mốc phát triển | Chủ trang trại/Gia súc/Chi phí sản xuất | Làm mát bằng tay không hiệu quả, gia súc bị stress, sản lượng giảm |
| 4 | Bảo trì hạ tầng | Rò rỉ nước không phát hiện kịp | Chủ trang trại | Lãng phí nước ban đêm, nước thải, hóa đơn nước cao |
| 5 | Quản lý chất lượng nước | Oxy hòa tan giảm gây cá ngạt | Chủ ao/hồ câu/Gia cầm nuôi | Cá/gia cầm nổi đầu, chết dạo, tổn thất kinh tế lớn |

## TOP 3 PROBLEM CARDS & DRAFT WORKFLOW

Dưới đây là 3 bài toán tiềm năng và mang lại giá trị cao nhất, được chuẩn hóa theo format Problem Card.

### 1. Problem Card: AI tự đăng bài & Phản hồi Fanpage (Kinh doanh/Bán hàng)

| Thành phần | Nội dung |
|---|---|
| **Actor** | Người bán hàng, Sale, Chủ shop, Quản trị viên Fanpage |
| **Bottleneck** | Bí ý tưởng lên bài; trả lời lặp đi lặp lại một nội dung; thời gian đăng bài bị lỡ; trả lời comment chậm |
| **Impact** | Bỏ lỡ giờ vàng đăng bài làm giảm tương tác; mất lượng khách hàng tiềm năng do chờ đợi lâu |
| **Success Metric** | Giảm 80% thời gian phản hồi các bình luận cơ bản; Thời gian response time < 1 phút |
| **Boundary** | AI chỉ trả lời thông tin đóng (đơn, giá). Tuyệt đối không tự ý mặc cả, không bịa thông tin |
| **Rủi ro & HITL** | Bị thao túng, tài khoản bị đánh spam, vòng lặp bot. $\rightarrow$ HITL: Đặt giới hạn tốc độ (Rate limit); tự động đẩy thông báo cho nhân viên nếu khách hàng tức giận hoặc câu hỏi nằm ngoài phạm vi |

#### Draft Workflow (Trước/Sau)

| Giai đoạn | Quy trình |
|---|---|
| **Trước (Manual)** | Kiểm tra sản phẩm → Nghĩ nội dung → Đăng bài → Khách bình luận → Đọc & phân loại ý định thủ công → Tra cứu tồn kho/giá → Gõ câu phản hồi |
| **Sau (AI & Automation)** | LLM tạo nháp nội dung → Người duyệt & Lên lịch đăng tự động → Khách bình luận → AI Agent phân loại ý định → Nhánh 1: AI trả lời ngay (nếu hỏi giá/đơn) / Nhánh 2: Gửi cảnh báo cho nhân viên (nếu phức tạp/tức giận) |

### 2. Problem Card: Làm mát chuồng trại tự động chống sốc nhiệt (Chăn nuôi)

| Thành phần | Nội dung |
|---|---|
| **Actor** | Chủ trang trại, Nhân viên kỹ thuật/chăm sóc |
| **Bottleneck** | Việc phun sương làm mát dựa hoàn toàn vào cảm tính (thấy nóng thì bật). Bật liên tục gây đọng nước, không kiểm soát được độ ẩm không khí |
| **Impact** | Môi trường quá ẩm làm bùng phát nấm mốc; vật nuôi dễ bị viêm phổi, bệnh đường hô hấp; lãng phí nước và điện |
| **Success Metric** | Duy trì chỉ số THI (Stress nhiệt) ở mức an toàn 24/7; giảm 100% tỷ lệ viêm phổi do độ ẩm chuồng nuôi bão hòa |
| **Boundary** | Hệ thống chỉ can thiệp vào bơm phun sương và quạt hút, không tự ý thay đổi nguồn điện tổng |
| **Rủi ro & HITL** | Cảm biến hỏng hoặc bị bùn đất che lấp dẫn đến đọc sai thông số. → HITL: Đặt cảnh báo qua Zalo nếu thông số vượt ngưỡng chết (VD: độ ẩm > 95% kéo dài) để nhân viên vào kiểm tra cảm biến thủ công |

#### Draft Workflow (Trước/Sau)

| Giai đoạn | Quy trình |
|---|---|
| **Trước (Manual)** | Trời nóng → Nhân viên đi bật máy phun sương → Quên tắt hoặc để quá lâu → Độ ẩm chuồng tăng vọt → Nhân viên phát hiện nền chuồng ướt mới đi tắt |
| **Sau (AI/Logic rule)** | Cảm biến đo Nhiệt độ & Độ ẩm → Vi điều khiển tính chỉ số THI → Nhánh 1 (Nóng + Khô): Bật phun sương → Nhánh 2 (Nóng + Ẩm bão hòa): Tắt phun sương, bật quạt hút gió → Tự động lặp lại liên tục |

### 3. Problem Card: Phát hiện rò rỉ và bục ống nước (Quản lý trang trại)

| Thành phần | Nội dung |
|---|---|
| **Actor** | Quản lý trang trại, Thợ bảo trì hệ thống |
| **Bottleneck** | Trang trại rộng, ống ngầm hoặc bồn nước khuất tầm nhìn, không thể giám sát 24/7 |
| **Impact** | Chuột cắn/bục ống trong đêm gây cháy máy bơm do chạy khan; ngập lụt úng cây hoặc chuồng trại; hóa đơn điện/nước tăng vọt |
| **Success Metric** | Phát hiện sự cố và ngắt nước tự động trong vòng 10 phút kể từ khi dòng chảy bất thường xảy ra |
| **Boundary** | Chỉ can thiệp đóng van từ (solenoid valve) tổng, không ngắt điện toàn trang trại |
| **Rủi ro & HITL** | Đóng nhầm van khi trang trại có nhu cầu sử dụng nước đột xuất vào ban đêm (rửa chuồng khẩn cấp). → HITL: Gửi tin nhắn Zalo kèm nút "Bỏ qua/Mở lại van" để con người có thể chèn quyền (override) bất cứ lúc nào |

#### Draft Workflow (Trước/Sau)

| Giai đoạn | Quy trình |
|---|---|
| **Trước (Manual)** | Sự cố rò rỉ xảy ra lúc 2h sáng → Bơm chạy liên tục bơm nước ra đất → 6h sáng nhân viên đi tuần mới phát hiện → Chạy đi sập cầu dao/khóa van thủ công → Khắc phục hậu quả |
| **Sau (AI/Logic rule)** | Cảm biến lưu lượng ghi nhận có dòng nước chảy liên tục trong khung giờ nghỉ (1h-4h sáng) → Hệ thống nhận diện sự khác biệt với thói quen tiêu thụ thường ngày → Tự động đóng van điện từ tổng → Gửi cảnh báo Zalo cho quản lý → Sáng nhân viên đến vị trí để sửa chữa |