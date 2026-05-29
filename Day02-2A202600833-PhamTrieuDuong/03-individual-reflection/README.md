# 03 — Individual Reflection

> Reflection cá nhân về quá trình scan problem, chọn candidate, phản biện trong nhóm và những gì tôi học được khi dùng AI để suy nghĩ thay vì để AI quyết định thay mình.

## 1. Tôi đã đóng góp gì trong lab này

Tôi không đi theo hướng chỉ chọn một ý tưởng rồi cố bảo vệ nó từ đầu. Tôi chủ động giữ 2 candidate mạnh nhất trong đầu là:

- Telegram cron job bot đọc timeseries invoices để phát hiện multiple outlier và trích insight theo custom nghiệp vụ.
- AI Sale Agent đa kênh để giảm tải phản hồi đầu và sàng lọc lead.

Trong nhóm, tôi thiên về việc đẩy mạnh phần problem framing và workflow hơn là nhảy ngay sang solution. Cách này giúp nhóm nhìn rõ hơn đâu là bài toán có workflow thật, đâu là bài toán chỉ nghe có vẻ hay nhưng chưa đủ chặt.

## 2. Tôi đã dùng AI như thế nào

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì |
|---|---|---|---|---|
| Scan | Gợi ý thêm các product idea khác nhau | Giúp tôi mở rộng góc nhìn nhanh | AI hay đẩy ý tưởng quá chung hoặc quá tham vọng | Tôi lọc lại những ý có workflow thật |
| Telegram bot idea | Gợi ý cách mô tả outlier, insight, rule custom | Giúp tôi diễn đạt rõ hơn về multiple outlier | AI thường chỉ nói tới dashboard hoặc thống kê mean/max | Tôi chỉnh lại để nhấn vào outlier, không phải report tĩnh |
| Sale Agent | Gợi ý workflow trước/sau và các metric | Dễ chuyển thành flow rõ ràng | AI có xu hướng chọn Agent quá nhanh | Tôi kiểm lại boundary và human-in-the-loop |
| Reflection | Gợi ý cấu trúc câu trả lời | Tiết kiệm thời gian viết nháp | Nếu để nguyên thì văn bị khá công thức | Tôi viết lại theo giọng của mình |

## 3. Bài học từ hai candidate mạnh nhất

### Telegram cron job bot phân tích outlier invoices

- Tôi nhận ra rằng dữ liệu tốt không tự biến thành insight. Nếu chỉ nhìn thống kê tổng quát như mean, mode, avg, max thì rất dễ bỏ qua tín hiệu thật.
- Điều quan trọng là phát hiện multiple outlier và hiểu outlier đó có ý nghĩa gì trong từng context khách hàng.
- Custom business rule là phần quyết định sản phẩm có dùng được hay không. Một threshold chung không đủ cho mọi khách hàng.
- Nếu làm sản phẩm này, AI nên đứng ở bước giải thích và tổng hợp insight, còn rule nghiệp vụ phải cho phép cấu hình theo từng khách hàng.

### AI Sale Agent

- Tôi thấy bài toán sales chat rất hợp để tách workflow trước/sau vì bottleneck rõ.
- Không phải chỗ nào cũng cần Agent. Nhưng riêng bài toán phản hồi đầu và sàng lọc lead thì AI giúp được nhiều.
- Tôi học được cách đặt giới hạn: AI được trả lời, hỏi thêm, phân loại, nhưng không tự chốt những việc nhạy cảm.
- Việc handoff cho sale là bắt buộc, không phải optional.

## 4. Tôi đã challenge nhóm như thế nào

- Tôi nhấn mạnh rằng không nên chọn bài toán chỉ vì nghe “AI” hơn.
- Tôi hỏi lại: workflow có thật không, metric có đo được không, phần nào là rule, phần nào là workflow, phần nào mới thật sự cần AI.
- Với candidate Telegram bot, tôi đặc biệt muốn nhóm nhìn vào outlier và custom rule, vì nếu chỉ làm report mean/max thì sản phẩm sẽ rất mỏng.
- Với Sale Agent, tôi đồng ý đây là bài mạnh, nhưng vẫn cần giữ boundary rõ để tránh biến nó thành một chatbot ôm hết mọi việc.

## 5. Điều tôi học được

- Problem tốt không phải problem nghe hoành tráng nhất.
- Một bài toán tốt phải có actor rõ, workflow rõ, bottleneck rõ và metric đo được.
- AI nên đứng đúng chỗ của nó: chỗ cần ngôn ngữ, suy luận ngữ cảnh, hoặc phát hiện pattern phức tạp.
- Nếu rule hoặc workflow giải được bài toán với ít rủi ro hơn thì nên chọn cái đó.
- Reflection tốt là chỗ mình nói thật AI đã giúp gì, và cũng nói thật nó đã làm mình lệch hướng ở đâu.

## 6. Nếu làm lại

Nếu làm lại, tôi sẽ làm sớm hơn một bước xác nhận với người dùng thật cho candidate Telegram bot. Tôi muốn biết rõ hơn:

- Outlier nào là outlier có ý nghĩa nhất với họ.
- Họ muốn bot cảnh báo theo kiểu nào: ngay lập tức, theo ngày, hay theo tuần.
- Rule custom của từng khách hàng khác nhau ra sao.
- Cảnh báo nào nên là hard alert, cảnh báo nào chỉ là insight mềm.

Tôi cũng sẽ giữ bài Sale Agent ở scope chặt hơn ngay từ đầu để không bị kéo sang quá nhiều tính năng phụ.

## 7. Tóm tắt ngắn

Tôi học được rằng làm AI product không bắt đầu từ model, mà bắt đầu từ problem thật và workflow thật. Trong lab này, hai candidate tốt nhất của tôi đều có đặc điểm chung: có dữ liệu, có workflow, có bottleneck, và có chỗ để AI hỗ trợ mà không thay thế hoàn toàn con người.

---

*Day 02 Lab v2 — Individual Reflection*