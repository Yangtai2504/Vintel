# 02 - Group Problem Statement

## Tóm tắt giả lập nhóm

- Nhóm chọn candidate problem từ top 3 của mỗi thành viên.
- Người thực hiện: HoThaiDuc, mã sinh viên 2A202600968.
- Bản cuối cùng chọn: **Tổng hợp báo cáo tiến độ hàng tuần và draft narrative từ nhiều nguồn dữ liệu**.
- Lý do chọn: workflow rõ, bottleneck cụ thể, metric đo được, có thể xử lý bằng workflow AI hỗ trợ.

## 01 - Group convergence

### Candidate cluster

- Báo cáo/tổng hợp thông tin: Weekly report, monthly update, meeting recap.
- Review/tóm tắt: PRD review, tài liệu kỹ thuật, email summary.
- Search/decision: tìm quyết định cũ trong Slack, tìm tài liệu onboarding.

### Shortlist

| Candidate | Actor rõ | Workflow rõ | Pain evidence | Impact đo được | Làm trong lab | So sánh R/W/A | Hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Weekly report | 5 | 5 | 4 | 5 | 5 | 5 | 5 | 34 |
| Review PRD | 4 | 5 | 3 | 3 | 5 | 4 | 4 | 28 |
| Slack decision search | 4 | 4 | 4 | 4 | 3 | 4 | 4 | 27 |

### Giải thích chọn Weekly report

- Có workflow chuỗi rõ ràng.
- Bottleneck dễ xác định: viết narrative từ raw data.
- Metric hiện trạng và mục tiêu cụ thể.
- Scope đủ nhỏ để làm demo workflow trong lab.

## 02 - Quick validation

### Phương pháp
- Hỏi nhanh 3 PM/PO làm việc trong nhóm hoặc quen biết.
- Hỏi: "Bạn có phải tổng hợp báo cáo/tóm tắt dữ liệu định kỳ không? Bước nào tốn thời gian nhất?"

### Kết quả

| Nguồn | Số người | Xác nhận | Phản bác | Điều chỉnh problem |
|---|---|---|---|---|
| Người quen | 3 | 2/3 thấy tốn nhất ở phần viết narrative | 1/3 dùng dashboard nội bộ khá đầy đủ | Thu hẹp scope: focus vào phần "draft narrative từ data có sẵn" |
| Mini poll nội bộ | 6 | 4/6 từng tự viết update tuần/tháng | 2/6 dùng template đã sẵn | Thêm non-AI alternative: template + dashboard |

### Insight

Pain chính không chỉ là thu thập số liệu. Pain nằm ở việc chuyển dữ liệu rời rạc thành narrative đủ rõ cho người khác quyết định.

## 03 - Research giải pháp

| Nguồn / case | Link | Phần giải quyết | Điểm mạnh | Khoảng trống | Bài học |
|---|---|---|---|---|---|
| Jira reporting | https://www.atlassian.com/software/jira/features/reports | Auto-pull số liệu | Tốt cho số liệu structured | Không viết narrative theo context | Data collection có thể dùng rule/script |
| Slack AI summary | https://slack.com/help/articles/25076892548883 | Tóm tắt conversation | Tốt cho recap | Không gom Jira/Sheets | AI nên dùng như bước input summary |
| Google Gemini trong Drive | https://support.google.com/drive/answer/15141241 | Tóm tắt file | Tốt cho tóm tắt văn bản | Cần kiểm nguồn | Ai draft cần review người thật |
| Fellow AI meeting notes | https://fellow.ai/features/ai | Bullet summary, action items | Có pattern draft + review | Không tự động pull Jira/Sheets | Workflow AI hỗ trợ từng bước hợp lý |

### Research takeaway

- Không cần build agent toàn bộ.
- Workflow tốt hơn: auto lấy dữ liệu, AI cấu trúc input, AI draft narrative, PM review.
- Cần rõ boundary: AI không tự gửi, không bịa insight, chỉ dùng data được cung cấp.

## 04 - Workflow before/after

### Current workflow

CURRENT STATE — 90 phút

[1 Export Jira: 10'] → [2 Lấy metrics Sheets: 10'] → [3 Đọc Slack recap: 15'] → [4 Tổng hợp vào Docs: 15'] → [5 Viết narrative: 25'] <-- bottleneck → [6 Review + format: 10'] → [7 Gửi email: 5']

### Future workflow

FUTURE STATE — 25 phút

[1 Auto-pull Jira/Sheets: 3'] → [2 AI cấu trúc dữ liệu: 4'] → [3 AI draft narrative: 5'] → [4 PM review + edit: 12'] → [5 Gửi: 1']

Fallback:
- AI draft nhạt/sai → PM dùng outline và chỉnh sửa hoặc viết lại.

Bottleneck mới:
- Review/edit vẫn là bước quan trọng để đảm bảo chất lượng.

## 05 - Problem Statement v0

| Field | Nội dung |
|---|---|
| Actor | Junior PM chịu trách nhiệm gửi weekly report cho leader. |
| Workflow | Export Jira → lấy số từ Sheets → đọc Slack recap → tổng hợp → viết narrative → review → gửi. |
| Bottleneck | Viết narrative từ raw data mất khoảng 25 phút và dễ bị blank page. |
| Impact | 90 phút/tuần cho 1 PM; report dễ trễ và thiếu bối cảnh cho leadership. |
| Success Metric | Giảm tổng thời gian xuống dưới 30 phút; không tăng số câu hỏi lại từ leader. |
| Boundary | AI không tự gửi report, không bịa số liệu, không thay PM approve. |

## 06 - Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| Rule | Template report + auto-pull metrics | Đủ nếu chỉ cần số liệu định kỳ | Không giải quyết narrative hằng tuần | Không chọn làm toàn bộ |
| Workflow | Script lấy data → AI cấu trúc → AI draft → PM review | Hợp vì narrative cần ngôn ngữ và review người thật | Draft sai/nhạt, cần review | Chọn |
| Agent | Agent tự động lấy nhiều nguồn và tự quyết | Chỉ cần nếu cần tự động hóa nhiều công cụ | Quá rộng, nhiều permission/risk | Chưa chọn |

### Lý do chọn
- Data collection có thể dùng rule/script.
- Narrative cần AI hỗ trợ ngôn ngữ.
- PM review giữ chất lượng và hạn chế hallucination.

## 07 - Problem Statement v1

| Field | Nội dung |
|---|---|
| Actor | Junior PM chịu trách nhiệm weekly report cho leadership. |
| Workflow | Export Jira → lấy metrics Sheets → đọc Slack → tổng hợp → viết narrative → review → gửi. |
| Bottleneck | Viết narrative từ raw data mất 25 phút và dễ trễ deadline. |
| Impact | 90 phút/tuần/PM; leadership thiếu context trước sync. |
| Success Metric | Giảm tổng thời gian xuống dưới 30 phút; không tăng câu hỏi lại từ CEO/EM. |
| Boundary | AI không tự gửi, không bịa insight, không thay PM quyết định cuối. |
| AI intervention point | Sau khi dữ liệu được gom lại, trước PM viết narrative. |
| Mức chọn | Workflow: rule/script lấy data, AI draft narrative, PM review. |
| Rủi ro & kiểm tra | Risk: hallucination, thiếu insight, narrative nhạt. PM review với data và chỉnh lại trước khi gửi. |

## 08 - Final decision

- Quyết định: **Go với scope nhỏ**.
- Pilot nhỏ nhất: dùng data mẫu từ 2 tuần gần nhất.
- Triển khai bán thủ công: PM paste dữ liệu/summary vào prompt chuẩn, AI draft narrative, PM review.

### Tại sao
- Scope rõ, có metric và boundary.
- Giải pháp workflow kiểm soát được rủi ro AI.
- Không chọn agent vì chưa cần tự động hóa đầu-cuối.
