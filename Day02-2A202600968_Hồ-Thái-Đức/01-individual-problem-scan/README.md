# 01 - Individual Problem Scan

## Người làm
- Tên: Hồ Thái Đức
- Mã sinh viên: 2A202600968
- Mục tiêu: Làm đầy đủ phần scan cá nhân với 10 problem và chọn top 3 Problem Cards.

## Phase 1 - Scan rộng 10 problems

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại, Tốn thời gian | Viết báo cáo tiến độ hàng tuần từ Jira, Sheets, Slack | PM, leader | Mất 2-3 giờ/tuần, hay trễ deadline gửi report |
| 2 | Tốn thời gian, AI có thể tốt hơn | Review PRD / tài liệu kỹ thuật dài 10-15 trang | Reviewer, PM | Mất 45-60 phút mỗi lần đọc và ghi chú |
| 3 | Tốn thời gian, Pain từ người khác | Tìm lại quyết định cũ trong Slack/Teams khi làm tiếp task | Dev, PM | Mất 10-20 phút mỗi lần tìm, đôi khi gặp thông tin cũ trái chiều |
| 4 | Lặp lại, Tốn thời gian | Chuẩn hóa meeting notes sau họp cross-team | Người tham gia họp | Mất 15-25 phút/buổi để viết và gửi notes |
| 5 | AI có thể tốt hơn | Chuyển dữ liệu Google Sheets vào slide báo cáo định kỳ | PM, analyst | Dễ sai số, mất 20-30 phút cho định dạng và kiểm tra |
| 6 | Lặp lại, Tốn thời gian | Hỏi lại quy trình onboarding nội bộ cho task mới | Người mới, intern | Hỏi 2-3 lần cùng một câu, trì hoãn 10-15 phút mỗi lần |
| 7 | Tốn thời gian, Pain từ người khác | Soạn email cập nhật trạng thái cho stakeholders | PM, leader | Mất 15-20 phút mỗi lần sửa câu, lo thiếu context |
| 8 | AI có thể tốt hơn | So sánh nhiều đề xuất giá/proposal để chọn phương án tốt nhất | PM, sales | Mất 30-45 phút đọc và gạch ý chính |
| 9 | Lặp lại, Tốn thời gian | Nhập liệu dữ liệu khách hàng từ form vào CRM | Nhân viên sales | Mất 10-20 phút/lần, dễ lỗi nhập tay |
| 10 | Tốn thời gian, AI có thể tốt hơn | Chuẩn bị checklist công việc hàng ngày từ nhiều nguồn | Cá nhân, nhóm | Dành 10-15 phút mỗi sáng tổng hợp thông tin từ Trello/Slack |

## Phase 2 - Top 3 Problem Cards

### Problem Card #1

Problem 1 câu:
- Mỗi tuần PM mất nhiều thời gian tổng hợp báo cáo tiến độ từ Jira, Google Sheets và Slack, và bước viết narrative là bottleneck lớn nhất.

Ai đang đau?
- Junior PM / PM chịu trách nhiệm gửi update cho leader.

Thời điểm / bối cảnh:
- Cuối tuần hoặc đầu tuần, trước buổi sync leadership.

Current workflow:
1. Export dữ liệu Jira.
2. Lấy số từ Google Sheets/Excel.
3. Đọc recap Slack/Teams.
4. Tổng hợp vào Google Docs/slide.
5. Viết narrative insight, highlight, risk, next action.
6. Review và định dạng.
7. Gửi cho stakeholders.

Bottleneck:
- Bước 5 viết narrative mất 25-30 phút và gây tình trạng blank page.

Impact:
- Tốn 2-3 giờ/tuần, dễ trễ deadline, leadership không có bối cảnh kịp.

Success metric:
- Giảm tổng thời gian xuống còn ≤ 30 phút/tuần; không tăng số câu hỏi lại từ leader.

Non-AI alternative:
- Dùng template báo cáo, checklist dữ liệu và dashboard Jira.

AI hypothesis:
- AI có thể hỗ trợ cấu trúc dữ liệu đầu vào và draft narrative, PM chỉ cần review/edit.

Quick gut:
- [x] Workflow
- [ ] Rule
- [ ] Agent
- [ ] No AI
- [ ] Chưa biết

#### Draft workflow hiện tại

CURRENT STATE — 120 phút

[1 Export Jira: 15'] → [2 Lấy metrics Sheets: 20'] → [3 Đọc Slack: 20'] → [4 Tổng hợp vào Docs: 15'] → [5 Viết narrative: 30'] <-- bottleneck → [6 Review: 15'] → [7 Gửi: 5']

#### Draft workflow tương lai

FUTURE STATE — 30 phút

[1 Auto-pull data: 5'] → [2 AI cấu trúc dữ liệu: 3'] → [3 AI draft narrative: 5'] → [4 PM review + edit: 15'] → [5 Gửi: 2']

Fallback:
- AI draft không đủ, PM dùng outline có sẵn và viết thủ công.

---

### Problem Card #2

Problem 1 câu:
- Reviewer mất nhiều thời gian đọc và hiểu PRD/tài liệu kỹ thuật dài để đưa ra nhận xét chính xác.

Ai đang đau?
- Reviewer, design lead, PM.

Thời điểm / bối cảnh:
- Trước review sprint, trước khi chốt scope feature.

Current workflow:
1. Mở PRD/tài liệu.
2. Đọc toàn bộ tài liệu.
3. Ghi chú điểm chưa rõ.
4. Soạn nhận xét và gửi lại.

Bottleneck:
- Đọc hiểu nội dung dài mất 45-60 phút.

Impact:
- Review chậm, quyết định feature trễ, dễ bỏ sót rủi ro.

Success metric:
- Giảm thời gian đọc/tóm tắt xuống còn ≤ 20 phút; vẫn giữ độ chính xác thông tin.

Non-AI alternative:
- Đọc thô, dùng checklist/summary bằng tay.

AI hypothesis:
- AI có thể tóm tắt nhanh nội dung, highlight phần thiếu hoặc mâu thuẫn.

Quick gut:
- [x] Workflow
- [ ] Rule
- [ ] Agent
- [ ] No AI
- [ ] Chưa biết

#### Draft workflow hiện tại

CURRENT STATE — 60 phút

[1 Mở PRD: 5'] → [2 Đọc và gạch chân: 40'] → [3 Ghi chú: 10'] → [4 Soạn feedback: 5']

#### Draft workflow tương lai

FUTURE STATE — 25 phút

[1 AI tóm tắt nội dung: 10'] → [2 Reviewer đọc summary + check chi tiết: 10'] → [3 Soạn nhận xét: 5']

Fallback:
- AI tóm tắt sai, reviewer đọc lại đoạn gốc và sửa nội dung.

---

### Problem Card #3

Problem 1 câu:
- Khi làm task tiếp theo, nhóm tốn quá nhiều thời gian tìm lại quyết định cũ trong Slack/Teams vì thông tin rời rạc.

Ai đang đau?
- Dev, PM, QA.

Thời điểm / bối cảnh:
- Bắt đầu task mới, chuẩn bị họp tiếp theo, đi vào giai đoạn phát triển.

Current workflow:
1. Nhớ hoặc tìm keyword.
2. Search Slack/Teams.
3. Đọc thread.
4. Xác nhận quyết định với người liên quan.

Bottleneck:
- Tìm kiếm và đọc thread mất 10-20 phút; đôi khi thông tin không rõ.

Impact:
- Delay task, đưa ra quyết định sai, phải hỏi lại người cũ.

Success metric:
- Giảm thời gian tìm quyết định xuống dưới 5 phút/lần.

Non-AI alternative:
- Dùng ghi chú chung, tài liệu quyết định rõ ràng.

AI hypothesis:
- AI có thể tóm tắt nhanh thread và nêu ra quyết định chính.

Quick gut:
- [x] Workflow
- [ ] Rule
- [ ] Agent
- [ ] No AI
- [ ] Chưa biết

#### Draft workflow hiện tại

CURRENT STATE — 20 phút

[1 Search keyword: 5'] → [2 Đọc thread: 10'] → [3 Xác nhận ý chính: 5']

#### Draft workflow tương lai

FUTURE STATE — 8 phút

[1 AI scan thread: 3'] → [2 AI tóm tắt quyết định: 3'] → [3 Người làm check lại: 2']

Fallback:
- AI bỏ sót thông tin, người dùng đọc lại thread gốc.
