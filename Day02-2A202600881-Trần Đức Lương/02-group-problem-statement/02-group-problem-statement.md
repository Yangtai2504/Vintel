# 02 - Group Problem Statement

## 1. Group convergence

### 1.1 Candidate problems

Nhóm đã tập hợp 10 candidate từ top 3 mỗi người, tập trung vào vấn đề vận hành trong hệ sinh thái Vin: VinFast Service, VinID CSKH, VinPearl resort, VinMart+ và VinUniversity.

### 1.2 Cluster / gom trùng

| Cluster | Candidates included | Pattern chung |
|---|---|---|
| Reporting / Summary | Weekly service report, resort operation plan, procurement checklist | Tổng hợp dữ liệu từ nhiều nguồn để làm report/quyết định. |
| Customer support | VinID points lookup, warranty status check | Xác thực thông tin khách hàng nhanh, giảm thời gian chờ. |
| Process onboarding | Onboarding nhân viên VinMart+, policy lookup | Tài liệu phân tán, dễ hỏi lại. |

### 1.3 Shortlist

| Candidate | Vì sao vào shortlist | Rủi ro / điều chưa rõ |
|---|---|---|
| Weekly operation report VinFast | Workflow rõ, nhiều nguồn dữ liệu, impact đo được | Có thể trùng với báo cáo nội bộ hiện tại của IT. |
| VinID points/khuyến mại lookup | Nhiều khách chờ, có evidence thực tế từ CSKH | Cần quyền truy cập hệ thống và rule rõ. |
| Resort operation plan VinPearl | Dễ validate với data khách và event | Dữ liệu đa nguồn, nhưng scope có thể mở rộng quá lớn. |

### 1.4 Score để đồng thuận

| Candidate | Actor rõ | Workflow rõ | Pain evidence | Impact đo được | Làm trong lab | So sánh R/W/A | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Weekly operation report VinFast | 5 | 5 | 4 | 5 | 5 | 5 | 5 | 34 |
| VinID points lookup | 4 | 4 | 4 | 4 | 4 | 4 | 4 | 28 |
| VinPearl operation plan | 4 | 4 | 3 | 4 | 4 | 4 | 4 | 27 |

**Candidate nhóm chọn:**
Weekly operation report cho VinFast Service Center.

**Vì sao chọn:**
- Data nguồn rõ ràng: CRM, SAP, service logs.
- Bottleneck cụ thể ở phần viết narrative.
- Impact có thể đo bằng thời gian và mức độ hỏi lại report.
- Có thể làm prototype workflow nhỏ trong lab.

**Vì sao không chọn candidate khác:**
- VinID points lookup cần truy cập hệ thống và rule phức tạp, dễ lan sang bài data integration.
- VinPearl plan scope rộng và phụ thuộc quá nhiều vào yêu cầu sự kiện cụ thể.

**Nếu có disagreement, nhóm xử lý thế nào:**
Nhóm sẽ ưu tiên candidate có workflow rõ nhất và có thể prototype bằng tài liệu/phiên bản bán tự động trong 30 phút. Nếu hai candidate giống nhau, chọn candidate có bằng chứng pain trực tiếp hơn.

## 2. Quick validation + research

### 2.1 Quick validation

| Nguồn | Số người / mẫu | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---|---|---|---|
| Interview nội bộ | 3 quản lý Service | 2/3 nói lab report mất nhiều thời gian, cần insight định lượng + chất lượng | 1 người dùng dashboard riêng đã đủ | Thu hẹp scope chỉ vào bước draft narrative, không làm toàn bộ data extraction. |
| Mini poll nội bộ | 5 người | 4/5 từng tự tổng hợp thông tin từ nhiều hệ thống | 1 người cho rằng process hiện tại đã có template | Bổ sung non-AI option template + dashboard. |

### 2.2 Research giải pháp đã có

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học |
|---|---|---|---|---|---|
| Jira/Confluence report templates | https://www.atlassian.com | Tự động pull số liệu và chuẩn hóa format | Giảm thời gian chuẩn bị dữ liệu | Không tự động sinh narrative insight | Cần AI chỉ cho phần wording chứ không thay thế báo cáo. |
| Slack AI summary | https://slack.com/intl/vi-vn/ai | Tóm tắt cuộc hội thoại và request | Good cho nguồn text rời | Chỉ một nguồn dữ liệu | Có thể dùng như input cho workflow. |
| Google Gemini in Drive | https://support.google.com/drive/answer/15141241 | Draft summary từ docs | Tốt để tạo bản nháp nhanh | Cần human review | Hướng tới workflow AI draft + human verify. |

## 3. Workflow nhóm

### 3.1 Current workflow

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---|---|---|---|---|---|
| 1 | Quản lý Service | CRM repair orders | Báo cáo raw data | 15' / tuần | Nhiều export thủ công. |
| 2 | Quản lý Service | SAP tồn kho phụ tùng | Số liệu inventory | 15' / tuần | Mất thời gian tìm tab đúng. |
| 3 | Quản lý Service | Service logs | Ghi chú kỹ thuật | 20' / tuần | Dữ liệu text khó tổng hợp. |
| 4 | Quản lý Service | Raw data | Excel/Docs tổng hợp | 10' / tuần | Thao tác ghép dữ liệu thủ công. |
| 5 | Quản lý Service | Dữ liệu tổng hợp | Narrative + insight | 30' / tuần | Bottleneck chính. |
| 6 | Quản lý Service | Draft report | Report hoàn chỉnh | 5' / tuần | Kiểm soát lần cuối. |
| 7 | Quản lý Service | Report | Gửi leadership | 5' / tuần | |

**Bottleneck chính:**
Viết narrative từ dữ liệu ghép rời rạc, phải suy ra insight, issue và action.

### 3.2 Future workflow

| Bước | Actor | Input | Output | Dạng hỗ trợ | Ghi chú |
|---|---|---|---|---|---|
| 1 | Script / IT | CRM/SAP/logs | Data input chuẩn | Rule/script | Tự động kéo dữ liệu tuần. |
| 2 | AI | Data input | Structured summary | Workflow | AI chuyển data thành cấu trúc. |
| 3 | AI | Structured summary | Draft narrative | Workflow | AI viết insight và đề xuất. |
| 4 | Quản lý Service | Draft narrative | Final report | Human review | Kiểm soát chất lượng. |
| 5 | Quản lý Service | Final report | Send | Human | Gửi cho leadership. |

**Before / after impact:**

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---|---|---|
| Số bước | 7 | 5 | Giảm thao tác thủ công. |
| Tổng thời gian | 90 phút | 30 phút | Target giảm 66%. |
| Số bước thủ công | 7/7 | 2/5 | Chỉ review + gửi giữ người thật kiểm. |
| Bottleneck chính | Viết narrative | Review/edit | AI hỗ trợ phần tự động. |
| Risk mới | Không có AI | Hallucination/narrative sai | Cần review có checklist. |

## 4. Problem Statement v0

| Field | Nội dung |
|---|---|
| Actor | Quản lý vận hành VinFast Service Center cần làm báo cáo tuần cho leadership. |
| Workflow | Export CRM, lấy SAP, đọc service logs, gộp dữ liệu, viết narrative, review, gửi. |
| Bottleneck | Viết narrative từ dữ liệu nhiều nguồn mất 30 phút và dễ thiếu insight quan trọng. |
| Impact | 90 phút/tuần, report dễ trễ, leadership không có bối cảnh kịp thời. |
| Success Metric | Giảm tổng thời gian xuống dưới 30 phút; không tăng số câu hỏi cần làm lại/thêm thông tin. |
| Boundary | Không tự động gửi report; không thay thế người ra quyết định; chỉ hỗ trợ phần draft narrative từ dữ liệu đã có. |

## 5. Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| Rule | Template report + script pull data | Đủ nếu chỉ cần số liệu chuẩn | Không giải quyết phần narrative insight | Không |
| Workflow | Script pull + AI cấu trúc + AI draft + human review | Đủ vì workflow rõ và bước AI nằm ở phần ngôn ngữ | Hallucination, draft nhạt | Có |
| Agent | Agent tự lấy, phân tích, hỏi thêm, và gửi report | Chỉ cần nếu cần tự động quyết định quá nhiều nguồn | Phức tạp, permission, rủi ro tự động gửi sai | Không |

**Mức chọn:**
Workflow.

**Vì sao chọn:**
- Dữ liệu extraction có thể rule hóa.
- Narrative là phần AI hỗ trợ tốt nhất.
- Human review giữ boundary an toàn.

**Vì sao không chọn mức đơn giản hơn:**
Rule không đủ do phần narrative vẫn phải viết thủ công.

## 6. Problem Statement v1

| Field | Nội dung |
|---|---|
| Actor | Quản lý vận hành VinFast Service Center chịu trách nhiệm weekly operation report. |
| Workflow | Export CRM/SAP/logs → gộp dữ liệu → AI draft narrative → human review → gửi. |
| Bottleneck | Viết narrative từ dữ liệu rời rạc mất 30 phút và dễ thiếu insight. |
| Impact | 90 phút/tuần; thiếu bối cảnh khiến leadership gặp khó khi đánh giá hoạt động. |
| Success Metric | Giảm tổng thời gian xuống dưới 30 phút; giữ số câu hỏi/lần chỉnh sửa report không tăng. |
| Boundary | Không tự động gửi; AI không được tự bịa số liệu; người quản lý phải xác nhận nội dung. |
| AI intervention point | Sau khi dữ liệu được gom lại, trước khi human review. |
| Mức chọn | Workflow. |
| Rủi ro & người thật kiểm tra | Risk: AI viết sai, thiếu chi tiết. Review bởi quản lý Service với checklist kiểm tra số liệu và issue. |

## 7. Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | Candidate cụ thể, actor rõ. |
| Baseline và success metric đã đo được chưa? | Yes | 90 phút vs 30 phút. |
| Có data/input đủ dùng chưa? | Not Yet | Cần mẫu data CRM/SAP/logs thực tế để test. |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes | Chỉ bản nháp, human review. |
| Có người review/owner vận hành không? | Yes | Quản lý Service là người kiểm. |
| Có cách non-AI đơn giản hơn không? | Yes | Template + dashboard; nhưng không giải quyết narrative. |

**Decision:**
Go với scope nhỏ.

**Lý do:**
Problem rõ, workflow đủ, AI can hỗ trợ phần draft narrative, và human review tiếp tục đảm bảo chất lượng.

**Pilot nhỏ nhất:**
- Lấy 2 tuần data sample từ CRM/SAP/logs.
- Tạo prompt chuẩn để AI draft narrative từ data có cấu trúc.
- Đo thời gian review/edit và số lỗi phải sửa.

**Nếu Not Yet, cần validate gì trước:**
- Lấy dữ liệu thật mẫu.
- Kiểm chứng với quản lý Service về nội dung report cần có. 

**Nếu No-Go, nên làm gì thay AI:**
- Dùng template report chuẩn + script pull data để giảm thời gian gộp thủ công.
