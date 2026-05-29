# 01 — Individual Problem Scan

> Mục tiêu: scan rộng 5 ý tưởng AI, chọn Top 3 để pitch.

## 1. Danh sách 5 ý tưởng AI (tóm tắt)

| # | Ý tưởng | Người gặp vấn đề | Vấn đề thật | Vì sao đáng xem xét |
|---|---|---|---|---|
| 1 | Telegram cron job bot phân tích outlier invoices | Kế toán / finance / ops | Khó phát hiện outlier ý nghĩa từ invoice timeseries | Dữ liệu timeseries rõ, workflow lặp, cần custom rule |
| 2 | AI Sale Agent đa kênh | Shop online / sale | Tin nhắn nhiều, phản hồi chậm, mất lead | Metric rõ (FRT, conversion), dễ pilot |
| 3 | AI weekly report assistant | PM / team lead | Gom dữ liệu và viết narrative tốn thời gian | Lặp lại hàng tuần, AI tạo draft hữu dụng |
| 4 | AI support ticket triage | Support / ops | Phân loại ticket thủ công chậm, backlog | Có thể route theo intent/priority/SLA |
| 5 | AI meeting action tracker | Team / PM | Action items bị rơi, khó follow-up | Có dấu hiệu thực tế, dễ demo |

## 2. Scan chi tiết (mỗi ý tưởng tóm tắt theo phong cách Problem Card)

### 1) Telegram cron job bot — phân tích outlier invoices

**Problem 1 câu:**
Team finance phải đọc hàng loạt invoice timeseries để tự phát hiện outlier theo ngữ cảnh khách hàng; phương pháp hiện tại chỉ dựa trên thống kê tổng quát nên dễ bỏ sót tín hiệu quan trọng.

**Actor:**
Kế toán, finance lead, ops manager, chủ shop.

**Bối cảnh:**
Bot chạy theo lịch (cron), nhận dữ liệu invoice hoặc batch export, gửi cảnh báo/insight qua Telegram để user review và điều chỉnh nghiệp vụ.

**Dấu hiệu thật:**
- Invoice tăng đột biến hoặc lặp
- Giao dịch lệch khung giờ bất thường
- Một khách hàng có pattern khác biệt so với baseline

**Bottleneck:**
Con người phải nhìn và so sánh nhiều biểu đồ/giá trị, khó tùy biến cho từng khách hàng.

**Impact:**
Bỏ sót alert quan trọng, phát hiện muộn, tốn thời gian giải thích cho business.

**Success metric:**
- Giảm thời gian phát hiện outlier (chuẩn hóa)
- Tăng tỉ lệ outlier có ý nghĩa được phát hiện đúng
- Giảm số case cần review thủ công

**Non-AI alternative:**
Rule-based thresholds trên BI dashboards (hiệu quả hạn chế, khó tùy biến theo ngữ cảnh khách hàng).

**AI hypothesis:**
Kết hợp thuật toán phát hiện bất thường (statistical + ML) với rule-engine tùy chỉnh: AI tóm tắt pattern, giải thích vì sao là outlier, gợi ý rule để áp dụng.

**Quick gut:**
Agent (bot) + rule là hướng khả thi, dễ demo và pilot trên dữ liệu thật.

### 2) AI Sale Agent đa kênh (tóm tắt)

**Problem 1 câu:**
Shop online mất lead vì phản hồi chậm và phải lặp thủ công các câu trả lời cơ bản.

**Actor:**
Shop owner, sales agent.

**Bottleneck:**
Phải xử lý hàng loạt thông điệp thủ công, lọc spam và phân loại intent.

**Metric thành công:**
Giảm First Response Time, giảm missed lead rate, tăng conversion.

### 3) AI Weekly Report Assistant (tóm tắt)

**Problem 1 câu:**
PM mất thời gian gom nhiều nguồn (Jira, Sheets, Slack) để viết weekly report narrative.

**Actor:**
PM, team lead.

**Bottleneck:**
Viết narrative từ raw data, cấu trúc và làm rõ insight.


## 3. Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Telegram cron job bot phân tích outlier invoices | Data rõ, workflow lặp, có thể pilot nhanh | Mức độ chính xác và explainability của AI trên dữ liệu thật |
| 2 | AI Sale Agent đa kênh | Metric rõ, giá trị trực tiếp cho doanh thu | Hand-off giữa AI và sale có mượt không |
| 3 | AI weekly report assistant | Tiết kiệm thời gian lặp, dễ demo | Chất lượng narrative ban đầu cần human-in-loop |


## Problem Card — Telegram cron job bot (chi tiết theo phong cách `NguyenVietDu`)

**Problem 1 câu:**
Mỗi ngày finance phải dò hàng loạt invoice timeseries để tìm tín hiệu bất thường; phương pháp thủ công dễ bỏ sót và tốn thời gian.

**Actor:**
Kế toán, finance lead, ops.

**Thời điểm / bối cảnh:**
Sau khi có dữ liệu ngày/tuần/tháng, user cần rà soát để phát hiện outlier hoặc pattern đáng chú ý và có thể điều chỉnh rule nghiệp vụ.

**Current workflow:**

```text
1. Export/receive invoice data
2. Mở dashboard/Excel để xem thống kê tổng quát
3. So sánh mean/median/max và duyệt từng mục đáng nghi
4. Nếu nghi ngờ, mở chi tiết invoice để xác minh
5. Ghi nhận và trao đổi với bên liên quan
```

**Bottleneck:**
Con người phải đọc nhiều biểu đồ/bảng, tốn thời gian và gặp khó khăn khi cần tuỳ biến theo từng khách hàng.

**Impact:**
Phát hiện muộn, tốn công verify, khó giải thích cho business.

**Success metric:**
- Giảm thời gian detect xuống 1/3 so với hiện tại
- Tăng precision của alerts khi pilot trên 1 khách hàng mẫu

**AI hypothesis:**
AI tổng hợp features timeseries, phát hiện multiple outlier patterns, sinh explanation ngắn gọn và gợi ý rule để áp dụng.

**Quick gut:**
Pilot khả thi với 1-2 khách hàng có dữ liệu sạch; Telegram làm giao diện feedback nhanh.

**Draft current workflow (thời lượng ước tính):**

```text
CURRENT — tốn thời gian
[1 Export data: 5']
→ [2 Mở và scan dashboard: 30']
→ [3 Dò biểu đồ & filter suspicious: 60']  <-- bottleneck
→ [4 Mở invoice chi tiết & verify: 40']
→ [5 Trao đổi + ghi nhận: 15']
```

**Draft future workflow (ước tính):**

```text
FUTURE — tối ưu
[1 Cron job upload data -> bot: 2']
→ [2 AI detect & summarize outliers: 3']
→ [3 User review trên Telegram + confirm/annotate: 10']  <-- human-in-loop
→ [4 AI generate suggested rule / explanation: 2']
→ [5 Apply rule hoặc schedule deeper review: tùy]
```

**Fallback:**
Nếu AI tạo alert sai hoặc thiếu, user có thể mark false-positive; hệ thống sẽ dùng feedback để điều chỉnh rule/threshold.


## 4. Vì sao tôi chọn ý tưởng này để pilot

- Dữ liệu dạng timeseries sẵn có, dễ prepare cho POC.
- Bài toán rõ ràng: detection & explanation.
- Có thể kết hợp rule-engine để tăng độ tin cậy.
- Giao diện Telegram phù hợp cho feedback nhanh và iterative loop.


## 5. Next steps (gợi ý roadmap ngắn)

1. Chọn 1 khách hàng mẫu và lấy dataset export (1 tuần)
2. Xây pipeline tiền xử lý và baseline outlier detection (2 tuần)
3. Tạo Telegram bot pilot, tích hợp feedback loop (1 tuần)
4. Đo metric, refine rule và mở rộng (liên tục)

---

*Day 02 Lab v2 — Individual Problem Scan*