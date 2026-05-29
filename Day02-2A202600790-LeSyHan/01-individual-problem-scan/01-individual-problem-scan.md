# 01 — Individual Problem Scan

## Scan rộng

| #  | Lăng kính         | Problem quan sát được                                                   | Ai đang đau?               | Dấu hiệu thật                                                |
| -- | ----------------- | ----------------------------------------------------------------------- | -------------------------- | ------------------------------------------------------------ |
| 1 | Tốn thời gian     | Phải tìm dataset để phục vụ cho việc chạy experiments                   | Researcher                 | Tốn 1-2 ngày có khi cũng không thấy khi data thuộc dạng hiếm |
| 2 | AI có thể tốt hơn | Không biết model nào thực sự là SOTA cho task rất niche                 | Researcher                 | Benchmark phân tán ở nhiều paper                             |                      |
| 3 | Lặp lại           | Viết meeting notes sau lab meeting hoặc standup                         | Researcher, employee       | 20-30 phút sau mỗi meeting                                   |
| 4 | AI có thể tốt hơn | Không biết nên đọc paper nào trước trong một lĩnh vực mới               | Student, junior researcher | Reading list quá lớn, thiếu định hướng                       |                           |
| 5 | Lặp lại           | Chỉnh CV khác nhau cho từng vị trí apply                                | Student, job seeker        | Chỉ sửa wording nhưng lặp lại liên tục                       |

## Top 3

| Rank | Problem                                     | Vì sao chọn                                                            | Điều còn chưa chắc                                         |
| ---- | ------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------- |
| 1    | Tìm dataset để chạy experiments             | Pain rất thật, xảy ra thường xuyên trong research niche, time-cost cao | Dataset metadata có đủ chuẩn hóa để search semantic không  |
| 2    | Không biết model nào là SOTA cho task niche | Giá trị lớn vì researcher luôn phải scan benchmark/paper mới           | Benchmark giữa các paper thường không đồng nhất            |
| 3    | Không biết nên đọc paper nào trước          | Phù hợp cho AI recommendation/summarization, user base rộng            | “Paper quan trọng” khá subjective theo từng hướng research |


## Problem Card #1 — Finding Dataset for Research

**Problem 1 câu:**
Researcher mất từ vài giờ đến vài ngày để tìm dataset phù hợp cho experiments, đặc biệt khi domain research niche hoặc multi-modal.

**Actor:**
MSc/PhD student, AI researcher, ML engineer.

**Thời điểm / bối cảnh:**
Khi bắt đầu một research direction mới hoặc cần benchmark model mới.

**Current workflow:**

```text
1. Search Google / PapersWithCode / HuggingFace
2. Đọc survey paper liên quan
3. Scan từng paper để xem dataset sử dụng
4. Kiểm tra dataset còn accessible hay không
5. Kiểm tra có labels / metadata phù hợp không
6. Download thử và inspect schema
7. Nếu không phù hợp → quay lại bước 1
```

**Bottleneck:**
Bước 3-5 — phải đọc nhiều paper và manually verify dataset relevance.

**Impact:**
Mất 1-2 ngày chỉ để tìm data trước khi bắt đầu experiments. Research momentum bị chậm và nhiều hướng research bị abandon vì thiếu data.

**Success metric:**
Giảm thời gian tìm dataset từ 1-2 ngày xuống dưới 1 giờ, tăng tỷ lệ tìm được dataset usable ngay lần đầu.

**Non-AI alternative:**
Curated spreadsheet/list dataset theo domain hoặc bookmark thủ công.

**AI hypothesis:**
AI hiểu research intent và semantic similarity để recommend dataset phù hợp từ paper, benchmark, metadata và community usage.

**Quick gut:**
Workflow + discovery.

### Draft current workflow

```text
CURRENT STATE — 1-2 ngày

[1 Search keyword]
→ [2 Đọc survey]
→ [3 Scan paper dataset]
→ [4 Verify accessibility]
→ [5 Check labels/schema]  <-- bottleneck
→ [6 Download thử]
→ [7 Không hợp → loop lại]
```

### Draft future workflow

```text
FUTURE STATE — 30-45 phút

[1 Input research intent]
→ [2 AI semantic dataset search]
→ [3 AI summarize dataset fit]
→ [4 AI rank usable datasets]
→ [5 Researcher inspect top results]
→ [6 Download + start experiment]

Fallback: recommendation chưa đúng → manual search.
```


## Problem Card #2 — Knowing SOTA Models for Niche Tasks

**Problem 1 câu:**
Researcher khó biết model nào thực sự là SOTA cho một task niche vì benchmark và result phân tán ở nhiều paper khác nhau.

**Actor:**
Researcher, graduate student, ML engineer.

**Thời điểm / bối cảnh:**
Khi bắt đầu literature review hoặc chọn baseline/model cho research mới.

**Current workflow:**

```text
1. Search paper theo keyword
2. Đọc benchmark table từng paper
3. So sánh metric thủ công
4. Check publication date
5. Verify dataset consistency
6. Ghi chú model promising
7. Repeat với paper mới
```

**Bottleneck:**
Bước 3-5 — benchmark thường không cùng dataset, metric hoặc experimental setting.

**Impact:**
Mất nhiều giờ để hiểu landscape research. Dễ chọn nhầm baseline cũ hoặc miss paper quan trọng.

**Success metric:**
Giảm thời gian landscape review xuống dưới 1 giờ, tăng confidence khi chọn baseline/model.

**Non-AI alternative:**
Survey paper hoặc PapersWithCode leaderboard.

**AI hypothesis:**
AI aggregate benchmark từ paper và normalize theo dataset/metric/context để suggest model phù hợp thay vì chỉ “best score”.

**Quick gut:**
Knowledge aggregation.

### Draft current workflow

```text
CURRENT STATE — 4-8 giờ

[1 Search papers]
→ [2 Read benchmark]
→ [3 Compare metrics manually]  <-- bottleneck
→ [4 Verify dataset consistency]
→ [5 Note promising models]
→ [6 Repeat for newer papers]
```

### Draft future workflow

```text
FUTURE STATE — 20-30 phút

[1 Input task/domain]
→ [2 AI aggregate benchmarks]
→ [3 AI normalize comparison]
→ [4 AI explain tradeoff]
→ [5 Researcher validate top models]

Fallback: niche task quá mới → manual paper review.
```
## Problem Card #3 — Choosing Which Papers to Read First

**Problem 1 câu:**
Người mới vào một lĩnh vực research không biết nên đọc paper nào trước giữa hàng trăm paper liên quan.

**Actor:**
Undergraduate student, MSc student, junior researcher.

**Thời điểm / bối cảnh:**
Khi bắt đầu thesis, literature review hoặc explore một field mới.

**Current workflow:**

```text
1. Search keyword trên Google Scholar/arXiv
2. Sort theo citation hoặc recency
3. Mở nhiều tab paper
4. Đọc abstract/introduction từng paper
5. Guess paper nào quan trọng
6. Ask senior/lab mate để confirm
```

**Bottleneck:**
Bước 4-5 — thiếu context nên khó biết paper foundational hay chỉ incremental.

**Impact:**
Mất nhiều ngày để build mental map của field. Dễ overwhelm và đọc sai thứ tự.

**Success metric:**
Giảm thời gian onboarding field mới từ vài ngày xuống vài giờ, tăng clarity về research direction.

**Non-AI alternative:**
Đọc survey paper hoặc xin reading list từ advisor.

**AI hypothesis:**
AI build dependency map giữa papers và recommend reading order dựa trên background + research goal của user.

**Quick gut:**
Knowledge navigation.

### Draft current workflow

```text
CURRENT STATE — vài ngày

[1 Search keyword]
→ [2 Open many papers]
→ [3 Read abstracts]
→ [4 Guess importance]  <-- bottleneck
→ [5 Ask senior/advisor]
→ [6 Build reading list manually]
```

### Draft future workflow

```text
FUTURE STATE — 1-2 giờ

[1 Input field + background]
→ [2 AI map research landscape]
→ [3 AI suggest reading order]
→ [4 AI summarize role of each paper]
→ [5 User start reading curated list]

Fallback: user muốn deep understanding → vẫn phải đọc full papers.
```

---