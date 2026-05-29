# 01 — Individual Problem Scan

## Scan rộng


| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Pain từ người khác | Người lớn tuổi bán hàng nhỏ lẻ không rành công nghệ, gặp khó khăn khi tính tiền và nhớ giá sản phẩm thay đổi liên tục. | Tiểu thương cao tuổi (Mẹ mình) | Tính chậm và dễ tính nhầm tiền cho khách khi đông và nhiều sản phẩm dòng hàng mới ra mắt gây khó khăn khi nhớ giá |
| 2 | Pain từ người khác | Người lớn tuổi bán hàng mất nhiều thời gian tính toán, cộng dồn doanh thu cuối ngày từ các trang sổ tay ghi chép thô sơ, dễ sai sót do chữ viết tay nguệch ngoạc hoặc ghi thiếu. | Tiểu thương cao tuổi (Mẹ mình) | Cuối ngày mất 30-45 phút ngồi bấm máy tính Casio, đôi khi lệch số không tìm ra nguyên nhân |
| 3 | Pain từ người khác | Tài xế không kịp cập nhật các lỗi phạt nguội mới, biển báo giao thông hoặc tuyến đường vì đổi mới liên tục | Tài xế lái xe đường dài/đô thị trung niên (Ba mình) | Bị phạt nguội bất ngờ, mất thêm 30 phút đến 1 tiếng do đi nhầm vào đường mới cấm hoặc đổi chiều, căng thẳng khi vừa lái xe đường dài vừa phải chú ý biển báo vừa tìm đường |
| 4 | Lặp lại | Mua trùng (duplicate) các món goods/merch do không nhớ chính xác mình đã mua khi nào | Fan KPop (Mình) | Thỉnh thoảng bị double item, phải tốn công đăng bài pass lại (cần 2-5 ngày để bán lại, ship hàng, chịu lỗ). |
| 5 | Tốn thời gian | Fan Kpop mất quá nhiều thời gian trong các hội nhóm Facebook, Threads, X để tìm kiếm, so sánh giá goods/merch và kiểm tra uy tín của seller. | Fan KPop (Mình) | Mất 1-2 tiếng để so giá, săn deal, dễ bị scam do không biết seller đã bị cảnh báo hoặc mua hớ |
| 6 | Tốn thời gian | Fresher IT tìm việc phải check nhiều platform (LinkedIn, TopCV, ITviec…) mỗi ngày, khó lọc JD phù hợp với profile và hay bỏ lỡ deadline apply | Sinh viên, người đang tìm việc | Check nhiều tab/platform mỗi ngày, bỏ lỡ JD thực sự match với profile data của mình |
| 7 | Lặp lại | Ứng viên phải viết lại cover letter/email apply cho từng JD, nội dung na ná nhau nhưng vẫn cần cá nhân hóa theo từng vị trí | Người đang apply nhiều job 1 lúc | Mỗi cover letter mất ~20-30 phút; lặp lại nhiều lần/tuần trong giai đoạn job hunting |
| 8 | AI có thể tốt hơn | Người tìm việc ôn phỏng vấn kỹ thuật từ nhiều nguồn rời rạc (LeetCode, Kaggle, Medium, YouTube), khó biết mình đang yếu mảng nào | Người đang chuẩn bị phỏng vấn | Lài liệu rải rác nhiều nền tảng, không có cách đo mức độ sẵn sàng theo từng mảng (SQL, Python, ML, case study) |


## Top 3


| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Tính doanh thu từ sổ tay | Workflow rõ, mất nhiều thời gian, có metric tốt | Nhiều cách viết tên SKU khác nhau |
| 2 | Cập nhật biển báo/lỗi giao thông hoặc tuyến đường mới | Impact lớn liên quan đến chi phí là tiền phạt và tâm lý người lái xe | Nguồn dữ liệu luật/biển báo mới cần chuẩn xác và real-time. |
| 3 | Người tìm việc IT check nhiều platform, khó lọc JD match profile | Giải quyết trực tiếp painpoint của người tìm việc | Cào dữ liệu từ các web có khả thi không |

## Problem Card #1 — Tính doanh thu từ sổ tay

**Problem 1 câu:**  
Mỗi cuối ngày các tiểu thương cao tuổi mất từ 30-45 phút để thủ công tính toán, cộng dồn doanh thu từ sổ tay ghi chép thô sơ, dễ dẫn đến tình trạng sai sót, lệch số do chữ viết tay nguệch ngoạc hoặc ghi thiếu.

**Actor:**  
Tiểu thương cao tuổi không rành công nghệ, ghi chép doanh thu bằng sổ tay, tổng kết bằng máy tính cuối ngày.

**Thời điểm / bối cảnh:**  
Cuối ngày sau khi đóng cửa, chuẩn bị tổng kết tiền mặt thu được, thường mệt và dễ tính nhầm hơn.

**Current workflow:**

```text
1. Người bán gom tất cả các trang sổ tay đã ghi chép các đơn hàng trong ngày.
2. Dò tìm và sử dụng máy tính bấm cộng tay từng dòng một.
3. Ghi tổng số tiền tính được vào một trang tổng kết cuối sổ.
4. Đếm lại cục tiền mặt thực tế thu được trong ngày (có thể dùng máy đếm tiền).
5. Đối soát giữa số tiền mặt thực tế và số tiền trên sổ xem có khớp hay không.
```

**Bottleneck:**  
Bước 2 — Sử dụng máy tính bấm cộng tay từng dòng. Chữ viết tay lúc đông khách thường rất nguệch ngoạc, ghi tắt hoặc ghi thiếu thông tin, dẫn đến việc bấm nhầm số, mất thời gian tính đi tính lại.

**Impact:**  
Mất 30-45 phút mỗi ngày trong trạng thái mệt mỏi sau cả ngày bán hàng. Đôi khi số liệu bị lệch phải làm lại từ đầu hoặc bị lệch mà không tìm ra nguyên nhân, gây tâm lý ức chế, lo lắng.

**Success metric:**  
Giảm thời gian tổng kết cuối ngày từ 30–45 phút xuống dưới 5 phút; số lần lệch số = 0.

**Non-AI alternative:**  
App ghi chép đơn giản (Google Sheets, sổ điện tử) có thể tự cộng dồn — không cần AI. 

**AI hypothesis:**  
Chụp ảnh trang sổ → AI nhận dạng chữ (OCR) + tổng hợp doanh thu → hiển thị kết quả rõ ràng. Người bán chỉ cần chụp và confirm số cuối.

**Quick gut:**  
Workflow — OCR + tính tổng là pipeline rõ ràng. AI cần thiết ở bước đọc chữ tay, bước tính toán là rule đơn giản. 

### Draft current workflow

```text
CURRENT STATE — ~40 phút

[1 Bán hàng xong, lấy sổ tay ra: 5-10']
→ [2 Đọc từng dòng chữ tay: 10']
→ [3 Bấm máy tính cộng từng dòng: 15']
→ [4 Tổng hợp vào Docs: 15']
→ [5 Lệch số → làm lại từ đầu: 10']  <-- bottleneck
→ [6 Ghi tổng vào sổ (hoặc nhớ): 5']
```

### Draft future workflow

```text
FUTURE STATE — 5 phút

[1 Bán hàng xong, lấy điện thoại: 1']
→ [2 Chụp ảnh trang sổ tay → AI đọc chữ (OCR): 1']
→ [3 AI tổng hợp và tính tổng → hiển thị từng dòng + tổng rõ ràng: 1']
→ [4 Người bán xem và confirm: 2']  <-- human boundary
→ [5 Lưu tự động, có lịch sử theo ngày: 1']

Fallback:  OCR đọc sai chữ tay → người bán nhập lại dòng đó bằng tay hoặc nhờ người khác kiểm tra
```

## Problem Cards #2 và #3 — tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| Cập nhật biển báo/lỗi giao thông hoặc tuyến đường mới | Tài xế lái xe đường dài | Thông tin phạt nguội mới, đường cấm/đổi chiều rải rác trên nhiều nguồn (group Facebook, Cục CSGT, app bản đồ) — không có chỗ tổng hợp đơn giản theo tuyến đường cụ thể | Số lần bị phạt nguội bất ngờ → 0; số lần đi sai đường do cấm/đổi mới → 0 | Workflow | Non-AI alternative mạnh (Waze/Google Maps quá popular) |
| Người tìm việc IT check nhiều platform, khó lọc JD match profile | Người đang trong giai đoạn tìm việc cao điểm | Phải đọc và tự đánh giá match từng JD trên từng platform riêng lẻ — không có cách gom và so với profile nhanh, dễ miss deadline vì bookmark thủ công| Phải đọc và tự đánh giá match từng JD trên từng platform riêng lẻ — không có cách gom và so với profile nhanh, dễ miss deadline vì bookmark thủ công | Workflow | Crawl dữ liệu từ các platform có thể bị giới hạn về mặt kỹ thuật/pháp lý |
