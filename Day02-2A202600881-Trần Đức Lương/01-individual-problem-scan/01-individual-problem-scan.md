# 01 - Individual Problem Scan

## Mục tiêu
- Scan ít nhất 5 problems từ trải nghiệm thật trong hệ sinh thái Vin.
- Chọn top 3 Problem Cards.
- Mỗi top problem có workflow hiện tại, bottleneck, impact, metric, non-AI alternative, AI hypothesis và draft workflow before/after.

## 1. Scan problems

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | Mỗi tuần VinFast Service Center phải tổng hợp báo cáo hiệu suất sửa chữa từ CRM, SAP và hệ thống báo cáo kỹ thuật. | Quản lý vận hành Service Center | Mất 90 phút/tuần, nhiều lần phải hỏi lại số liệu từ 3 nguồn khác nhau. |
| 2 | Tốn thời gian | Nhân viên VinID chăm sóc khách hàng mất nhiều thời gian kiểm tra lịch sử điểm thưởng và hợp lệ khuyến mại. | CSKH VinID | 15-20 phút/lần, khách chờ lâu, dễ xảy ra sai sót. |
| 3 | AI có thể tốt hơn | Quản lý VinPearl cần tổng hợp yêu cầu phòng và dịch vụ từ PMS, email, chat với khách để lập kế hoạch vận hành cuối tuần. | Quản lý resort | Tốn 40 phút/buổi, phải đọc nhiều nguồn rời rạc. |
| 4 | Pain từ người khác | Nhân viên VinMart+ mới được hỏi đi hỏi lại quy trình nhập hàng và kiểm kho do tài liệu phân tán. | Nhân viên cửa hàng | Hỏi lại 2-3 lần mỗi ca, onboarding chậm. |
| 5 | Lặp lại | Đội Procurement VinGroup phải kiểm tra hồ sơ nhà cung cấp theo chuẩn nội bộ cho mỗi hợp đồng mới. | Procurement officer | Mỗi hợp đồng 30 phút, dễ bỏ sót checklist. |
| 6 | Tốn thời gian | Giám sát tại VinUniversity phải đọc nhiều tài liệu tổ chức để trả lời câu hỏi sinh viên về học bổng và deadline. | Sinh viên + admin | 20 phút/lần tìm, nhiều câu trả lời chưa chính xác. |

## 2. Top 3 Problem Cards

### Problem Card #1

**Problem 1 câu:**
VinFast Service Center cần ghép dữ liệu từ CRM, SAP và báo cáo kỹ thuật để làm weekly operation report, nhưng bước tổng hợp narrative và insight tốn nhiều thời gian.

**Actor:**
Quản lý vận hành VinFast Service Center.

**Thời điểm / bối cảnh:**
Mỗi thứ Hai, trước cuộc họp tuần với giám đốc khu vực.

**Current workflow 3-7 bước:**
1. Export dữ liệu repair order từ CRM.
2. lấy số liệu chi phí, tồn kho phụ tùng từ SAP.
3. đọc báo cáo kỹ thuật từ system service logs.
4. gộp dữ liệu vào Excel/Google Sheet.
5. viết narrative insight, trend, issue, và action.
6. review với team.
7. gửi report cho giám đốc.

**Bottleneck:**
Bước 5 - viết narrative và insight từ dữ liệu rời rạc mất 30 phút và dễ bị thiếu thông tin quan trọng.

**Impact:**
Tối thiểu 90 phút/tuần, dễ khiến report trễ và leadership không có bối cảnh đúng lúc.

**Success metric:**
Giảm tổng thời gian từ 90 phút xuống dưới 30 phút mà vẫn đảm bảo nội dung không bị hỏi lại.

**Non-AI alternative:**
Dùng template báo cáo chuẩn và checklist insight, nhưng vẫn cần người phân tích thủ công.

**AI hypothesis:**
AI có thể chuyển dữ liệu và ghi chú từ nhiều nguồn thành draft narrative; người quản lý chỉ việc review/edit.

**Quick gut:** [ ] No AI / [ ] Rule / [x] Workflow / [ ] Agent / [ ] Chưa biết

**Draft current workflow:**

```text
CURRENT STATE — 90 phút
[Export CRM data: 15']
→ [Lấy SAP + tồn kho: 15']
→ [Đọc service logs: 20']
→ [Gộp vào sheet: 10']
→ [Viết narrative: 30']  <-- bottleneck
→ [Review: 5']
→ [Gửi: 5']
```

**Draft future workflow:**

```text
FUTURE STATE — 30 phút
[Auto-pull CRM/SAP: 5']
→ [AI cấu trúc dữ liệu: 5']
→ [AI draft narrative: 5']
→ [Manager review + edit: 12']
→ [Gửi: 3']

Fallback: AI draft kém → manager tự viết lại.
```

### Problem Card #2

**Problem 1 câu:**
Nhân viên CSKH VinID phải xác thực tình trạng điểm thưởng và điều kiện khuyến mại thủ công từ nhiều hệ thống, khiến khách chờ lâu.

**Actor:**
Nhân viên Chăm sóc Khách hàng VinID.

**Thời điểm / bối cảnh:**
Khi khách gọi/hỏi qua live chat tìm thông tin điểm thưởng và ưu đãi.

**Current workflow 3-7 bước:**
1. mở CRM VinID.
2. kiểm tra account và điểm thưởng.
3. so sánh điều kiện khuyến mại từ dashboard marketing.
4. trả lời khách.

**Bottleneck:**
Bước 2-3 - xác thực điểm và điều kiện giảm giá cần mở nhiều hệ thống và đọc nhiều quy tắc.

**Impact:**
15-20 phút/lần, làm giảm trải nghiệm khách và tăng tỷ lệ chuyển lại support.

**Success metric:**
Giảm thời gian xác thực xuống dưới 5 phút và giảm số case phải chuyển lên cấp 2.

**Non-AI alternative:**
Xây tool lookup chung hoặc checklist nội bộ.

**AI hypothesis:**
AI có thể đọc nhanh điều kiện chương trình khuyến mại và khớp với tài khoản khách.

**Quick gut:** [ ] No AI / [ ] Rule / [x] Workflow / [ ] Agent / [ ] Chưa biết

**Draft current workflow:**

```text
CURRENT STATE — 15-20 phút
[Open CRM: 5']
→ [Check points: 5']
→ [Find promotion rules: 5']
→ [Compose response: 5']
```

**Draft future workflow:**

```text
FUTURE STATE — 6 phút
[Lookup account + points: 2']
→ [AI summarize promotion eligibility: 2']
→ [CSKH review & reply: 2']
```

### Problem Card #3

**Problem 1 câu:**
Quản lý VinPearl phải tổng hợp yêu cầu phòng, sự kiện và dịch vụ từ PMS, email và chat để lên kế hoạch vận hành cuối tuần.

**Actor:**
Quản lý vận hành resort VinPearl.

**Thời điểm / bối cảnh:**
Trước thực hiện kế hoạch cuối tuần vì lượng khách lưu trú và sự kiện tăng.

**Current workflow 3-7 bước:**
1. xem booking từ PMS.
2. đọc email request khách.
3. đọc chat nội bộ F&B và spa.
4. tổng hợp vào tài liệu.
5. lập plan nhân sự.

**Bottleneck:**
Bước 4 - gộp thông tin từ nhiều nguồn mất nhiều thời gian và dễ sót yêu cầu.

**Impact:**
40 phút/buổi, có thể dẫn đến thiếu nhân sự hoặc dịch vụ sai yêu cầu.

**Success metric:**
Giảm thời gian tổng hợp xuống dưới 15 phút, giảm 1-2 lỗi điều phối mỗi tuần.

**Non-AI alternative:**
Dùng biểu mẫu chuẩn và phân công quy trình góp thông tin.

**AI hypothesis:**
AI có thể tóm tắt request và đề xuất dàn bài kế hoạch vận hành.

**Quick gut:** [ ] No AI / [ ] Rule / [x] Workflow / [ ] Agent / [ ] Chưa biết

**Draft current workflow:**

```text
CURRENT STATE — 40 phút
[Read PMS: 10']
→ [Read email: 10']
→ [Read chat: 10']
→ [Summarize: 10']
```

**Draft future workflow:**

```text
FUTURE STATE — 15 phút
[Collect inputs: 5']
→ [AI draft summary: 5']
→ [Manager review: 5']
```

## 3. Card pitch

**Card tôi muốn pitch nhất:**
Problem Card #1 — Weekly operation report cho VinFast Service Center.

**Vì sao:**
Bài có workflow rõ, bottleneck cụ thể, impact đo được và dữ liệu đến từ nhiều hệ thống trong hệ sinh thái Vin.

**Câu hỏi tôi muốn nhóm challenge:**
- Ai thực sự cần report này và cần insight nào?
- Nếu AI làm draft narrative, kiểm soát chất lượng bằng cách nào?
- Rule/Workflow hiện tại đã đủ chưa nếu chỉ dùng template chuẩn?
