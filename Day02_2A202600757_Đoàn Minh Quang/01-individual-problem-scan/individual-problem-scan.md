# 01 — Individual Problem Scan

## Scan rộng 10 problems

| # | Lăng kính | Problem quan sát được | Đối tượng                                                     | Kiểm chứng                                                                                            |
|---|---|---|----------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| 1 | Pain từ người khác, lặp lại | Cư dân Vinhomes khi có yêu cầu liên quan nhiều dịch vụ không biết gửi đúng kênh nào: ban quản lý, app cư dân, VinFast, Vinmec, Vinschool hay CSKH chung. | Cư dân Vinhomes, đặc biệt gia đình dùng nhiều dịch vụ Vin.     | Có thể hỏi cư dân/nhóm cư dân: lần gần nhất gửi phản ánh mất bao lâu, có bị chuyển sai bộ phận không. |
| 2 | Tốn thời gian, AI có thể tốt hơn | Nhân viên CSKH phải đọc nhiều lịch sử tương tác trước khi hiểu khách hàng đang dùng những dịch vụ nào trong hệ sinh thái. | Nhân viên CSKH, khách hàng cần hỗ trợ nhanh.                   | Có thể đo thời gian đọc context trước mỗi ticket và số lần hỏi lại khách thông tin đã cung cấp.       |
| 3 | AI có thể tốt hơn | Khách hàng mới trong hệ sinh thái không biết gói/quyền lợi/dịch vụ nào phù hợp với nhu cầu gia đình. | Khách hàng mới mua nhà, mua xe hoặc mới chuyển vào khu Vinhomes. | Có thể survey: khách có biết quyền lợi liên quan VinFast, Vinmec, Vinschool, Vinpearl không.          |
| 4 | Lặp lại, tốn thời gian, AI có thể tốt hơn | Chủ xe VinFast phải tự kiểm tra nhiều nguồn khi lên lịch trình đi đường dài: % pin còn lại, quãng đường, trạm sạc nên dừng, thời gian sạc và lịch trình cụ thể. | Chủ xe VinFast đi đường dài/đi tỉnh.                            | Có thể đo thời gian lên kế hoạch chuyến đi, số app/nguồn phải kiểm tra, số lần đổi kế hoạch sạc.       |
| 5 | Pain từ người khác | Phụ huynh Vinschool nhận nhiều thông báo về học tập, lịch, y tế, hoạt động nhưng khó biết việc nào cần xử lý ngay. | Phụ huynh có con học Vinschool.                                | Có thể hỏi số thông báo bị bỏ lỡ hoặc số lần phải hỏi lại giáo viên/admin.                            |
| 6 | Tốn thời gian | Khách đặt chuyến đi Vinpearl phải tự ghép lịch di chuyển, khách sạn, vui chơi, ưu đãi, thông tin gia đình. | Gia đình đi du lịch Vinpearl.                                  | Có thể đo số lần chuyển app/web hoặc liên hệ tư vấn trước khi chốt booking.                           |
| 7 | Lặp lại | Người dùng app hệ sinh thái phải nhập lại thông tin cá nhân/nhu cầu khi chuyển giữa các dịch vụ. | Khách hàng dùng nhiều dịch vụ Vin.                             | Có thể kiểm số form/kênh yêu cầu nhập lại thông tin đã có.                                            |
| 8 | AI có thể tốt hơn | Người dùng khó tìm lại chính sách/điều kiện ưu đãi đúng thời điểm vì thông tin nằm trong nhiều thông báo, app, website. | Khách hàng có điểm thưởng/quyền lợi trong hệ sinh thái.        | Có thể đo thời gian tìm chính sách và số câu hỏi CSKH lặp lại.                                        |
| 9 | Pain từ người khác | Ban quản lý khu đô thị khó phân loại phản ánh cư dân nếu mô tả không rõ hoặc liên quan nhiều bên. | Ban quản lý, bộ phận vận hành đô thị.                          | Có thể đo tỷ lệ ticket bị chuyển lại/chuyển sai.                                                      |
| 10 | Tốn thời gian | Người dùng Vinmec cần chuẩn bị giấy tờ/lịch sử trước khi khám nhưng thông tin nằm rải rác trong lịch hẹn, hồ sơ cũ, bảo hiểm, app. | Bệnh nhân/khách hàng Vinmec.                                   | Có thể phỏng vấn nhanh bệnh nhân: trước khi khám phải chuẩn bị gì, mất bao lâu.                       |

---

## Chọn Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Chủ xe VinFast phải tự kiểm tra nhiều nguồn khi lên lịch trình đi đường dài: % pin, trạm sạc, thời gian dừng và lịch trình cụ thể. | Actor rõ, workflow hiện tại có thể vẽ được, bottleneck nằm ở việc tự ghép nhiều nguồn thông tin, metric đo được bằng thời gian lập kế hoạch và số lần phải kiểm tra lại. | Chưa có dữ liệu realtime về tình trạng trạm sạc, giao thông, thời tiết và mức tiêu hao thực tế từng xe. |
| 2 | Nhân viên CSKH phải đọc nhiều lịch sử tương tác để hiểu context khách hàng đa dịch vụ. | AI có thể hỗ trợ tóm tắt context, impact vận hành rõ, đo được bằng thời gian xử lý ticket. | Cần biết dữ liệu các dịch vụ có được phép kết nối không. |
| 3 | Phụ huynh Vinschool khó theo dõi thông báo và việc cần hành động. | Actor cụ thể, có pain lặp lại hằng ngày/tuần, có thể dùng rule/workflow trước khi dùng AI. | Rủi ro privacy/trẻ em cao, cần boundary rất chặt. |

---

## Problem Card #1 — Chủ xe VinFast lập lịch trình đi đường dài

**Problem 1 câu:**  
Chủ xe VinFast khi đi đường dài phải tự kiểm tra nhiều nguồn để quyết định lịch trình: % pin còn lại, quãng đường, trạm sạc nên dừng, thời gian sạc và thời điểm tiếp tục di chuyển.

**Actor:**  
Chủ xe VinFast đi đường dài, đi tỉnh hoặc đi đến điểm đến xa hơn phạm vi di chuyển thường ngày.

**Thời điểm / bối cảnh:**  
Trước chuyến đi hoặc trong lúc đang di chuyển, khi tài xế cần biết xe có đủ pin đến điểm đến/trạm sạc tiếp theo không, nên dừng sạc ở đâu, sạc bao lâu và lịch trình có bị trễ không.

**Current workflow 7 bước:**

1. Chủ xe kiểm tra % pin hiện tại trên xe/app.
2. Nhập điểm đến trên bản đồ để xem quãng đường và thời gian di chuyển.
3. Tìm trạm sạc VinFast trên hoặc gần tuyến đường.
4. Tự ước lượng xe có đủ pin đến trạm sạc/điểm đến không.
5. Tự chọn trạm sạc phù hợp theo vị trí, khoảng cách và mức an toàn pin.
6. Tự ước lượng nên sạc bao lâu/sạc đến bao nhiêu %.
7. Điều chỉnh lịch trình nếu trạm sạc xa, không tiện, đông hoặc phát sinh thay đổi trên đường.

**Bottleneck:**  
Bước 3-6: chủ xe phải tự ghép nhiều nguồn thông tin và tự tính kế hoạch sạc. Đây là phần gây lo lắng nhất vì nếu tính sai có thể phải đổi lộ trình, dừng sạc không tối ưu hoặc mất thời gian giữa đường.

**Impact:**  
Người dùng mất thời gian chuẩn bị chuyến đi, thường xuyên phải mở nhiều app/nguồn để kiểm tra lại, cảm giác không chắc chắn khi đi xa bằng xe điện tăng lên. Trải nghiệm VinFast bị ảnh hưởng dù xe và hạ tầng sạc có thể đáp ứng được.

**Success metric:**  
Giảm thời gian lập kế hoạch chuyến đi từ 20-30 phút xuống dưới 5 phút; giảm số nguồn/app phải kiểm tra từ 3-4 xuống 1; giảm số lần phải điều chỉnh kế hoạch sạc giữa đường; tăng tỷ lệ chuyến đi có kế hoạch sạc rõ trước khi xuất phát.

**Non-AI alternative:**  
Bản đồ trạm sạc + rule tính quãng đường/pin an toàn + checklist thủ công trước chuyến đi.

**AI hypothesis:**  
Workflow/AI có thể nhận điểm đi, điểm đến, % pin hiện tại, loại xe, mức pin an toàn mong muốn và ưu tiên của tài xế để đề xuất lịch trình: đi tuyến nào, dừng sạc ở đâu, nên sạc đến bao nhiêu %, dự kiến mất bao lâu và khi nào cần điều chỉnh.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 20-30 phút lập kế hoạch trước chuyến đi

[1 Kiểm tra % pin hiện tại: 1']
→ [2 Nhập điểm đến trên bản đồ: 2']
→ [3 Tìm trạm sạc trên/gần tuyến đường: 5-10']  <-- bottleneck
→ [4 Tự ước lượng pin có đủ không: 5']
→ [5 Chọn trạm dừng sạc: 5']
→ [6 Tự tính thời gian sạc/lịch trình: 5-10']   <-- bottleneck
→ [7 Kiểm tra lại khi có thay đổi trên đường]
```

### Draft future workflow

```text
FUTURE STATE — dưới 5 phút lập kế hoạch

[1 Nhập điểm đến + % pin + loại xe: 1']
→ [2 Rule tính quãng đường, ngưỡng pin an toàn, trạm sạc phù hợp: <1']
→ [3 Workflow/AI đề xuất 1-3 lịch trình dễ hiểu: 1']
→ [4 Tài xế chọn phương án: 1']
→ [5 App theo dõi và nhắc nếu cần điều chỉnh: liên tục]

Human boundary:
- Tài xế vẫn quyết định cuối cùng.
- Hệ thống không cam kết tuyệt đối về tình trạng trạm sạc, giao thông, thời tiết hoặc mức tiêu hao thực tế.
- Khi dữ liệu realtime không chắc chắn, app phải hiển thị mức độ tin cậy và phương án dự phòng.

Fallback:
Nếu dữ liệu trạm sạc/giao thông không đủ tin cậy, dùng rule an toàn hơn: chọn trạm gần hơn, giữ buffer pin cao hơn, hoặc khuyến nghị tài xế kiểm tra lại thủ công.
```

---

## Problem Card #2 — CSKH đọc context khách hàng đa dịch vụ

**Problem 1 câu:**  
Nhân viên CSKH mất thời gian đọc nhiều lịch sử tương tác để hiểu khách hàng đang dùng những dịch vụ nào trong hệ sinh thái trước khi hỗ trợ.

**Actor:**  
Nhân viên CSKH hoặc vận hành tuyến đầu.

**Thời điểm / bối cảnh:**  
Khi nhận ticket từ khách hàng có nhiều quan hệ với Vingroup: cư dân Vinhomes, chủ xe VinFast, phụ huynh Vinschool, khách Vinmec/Vinpearl.

**Current workflow 5 bước:**

1. Nhận ticket.
2. Tìm thông tin khách ở từng hệ thống/kênh.
3. Đọc lịch sử tương tác.
4. Hỏi lại khách nếu thiếu context.
5. Trả lời hoặc chuyển bộ phận.

**Bottleneck:**  
Bước 2-3: tìm và đọc context rải rác.

**Impact:**  
Thời gian xử lý ticket tăng, khách phải lặp lại thông tin, chất lượng trả lời không đồng đều.

**Success metric:**  
Giảm thời gian đọc context trước khi trả lời từ 8-12 phút xuống dưới 3 phút; giảm số câu hỏi lại khách về thông tin đã có.

**Non-AI alternative:**  
CRM thống nhất, tag khách hàng, checklist thông tin.

**AI hypothesis:**  
AI tóm tắt lịch sử tương tác và highlight thông tin liên quan. Nhân viên vẫn là người trả lời.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 15-30 phút/ticket

[Nhận ticket]
→ [Tra cứu khách ở nhiều hệ thống]
→ [Đọc lịch sử tương tác]  <-- bottleneck
→ [Hỏi lại khách nếu thiếu]
→ [Trả lời/chuyển bộ phận]
```

### Draft future workflow

```text
FUTURE STATE — 8-15 phút/ticket

[Nhận ticket]
→ [Rule lấy hồ sơ liên quan]
→ [AI tóm tắt context + rủi ro]
→ [Nhân viên kiểm tra và trả lời]  <-- human boundary
→ [Cập nhật ticket]
```

---

## Problem Card #3 — Phụ huynh Vinschool theo dõi thông báo

**Problem 1 câu:**  
Phụ huynh Vinschool nhận nhiều thông báo về học tập, lịch, y tế, sự kiện nhưng khó biết thông báo nào cần hành động ngay.

**Actor:**  
Phụ huynh có con học Vinschool.

**Thời điểm / bối cảnh:**  
Hằng ngày hoặc hằng tuần khi trường gửi thông báo, lịch học, sự kiện, yêu cầu xác nhận, y tế hoặc đóng phí.

**Current workflow 5 bước:**

1. Nhận nhiều thông báo qua app/email/nhóm lớp.
2. Đọc từng thông báo.
3. Tự lọc việc cần làm.
4. Hỏi lại giáo viên/admin nếu không rõ.
5. Ghi nhớ deadline.

**Bottleneck:**  
Bước 2-3: đọc và phân loại việc cần hành động.

**Impact:**  
Phụ huynh bỏ lỡ deadline, hỏi lại nhiều, trải nghiệm kém.

**Success metric:**  
Giảm thời gian kiểm tra thông báo mỗi ngày từ 15 phút xuống dưới 5 phút; giảm số thông báo bị bỏ lỡ.

**Non-AI alternative:**  
Tag thông báo bằng rule: cần xác nhận, cần đóng phí, chỉ đọc, khẩn cấp.

**AI hypothesis:**  
AI tóm tắt thông báo, trích deadline, phân loại action item. Không tự trả lời thay phụ huynh.

**Quick gut:**  
Rule/Workflow.

### Draft current workflow

```text
CURRENT STATE — 10-20 phút/ngày

[Nhận thông báo]
→ [Đọc từng nội dung]
→ [Tự lọc việc cần làm]  <-- bottleneck
→ [Hỏi lại nếu không rõ]
→ [Tự nhớ deadline]
```

### Draft future workflow

```text
FUTURE STATE — dưới 5 phút/ngày

[Nhận thông báo]
→ [Rule phân loại loại thông báo]
→ [AI tóm tắt + trích deadline nếu có]
→ [Phụ huynh xác nhận/đánh dấu đã xử lý]
```

---

## Card muốn pitch nhất

Card tôi muốn pitch nhất:

```text
Chủ xe VinFast phải tự kiểm tra nhiều nguồn khi lên lịch trình đi đường dài: % pin còn lại, trạm sạc nên dừng, thời gian sạc và lịch trình cụ thể.
```

Vì sao:

```text
Problem này cụ thể hơn và gần với trải nghiệm thật của chủ xe điện, đánh đúng vào tâm lý khi sử dụng xe điện đi đường dài. Khi đi đường dài, người lái không chỉ cần biết điểm đến mà còn cần biết % pin hiện tại, trạm sạc nào nằm trên tuyến đường, nên dừng ở đâu, sạc bao lâu và có phương án dự phòng không.

Problem này dễ đạt tiêu chí điểm: actor rõ, workflow vẽ được, bottleneck cụ thể, metric có thể đo bằng thời gian lập kế hoạch/số lần kiểm tra lại/số lần đổi kế hoạch, và có thể so sánh rõ Rule/Workflow/Agent. AI cũng có boundary rõ: chỉ đề xuất lịch trình, tài xế vẫn quyết định cuối cùng.
```

Câu hỏi tôi muốn nhóm challenge:

```text
1. Chủ xe VinFast hiện đã có công cụ nào giải quyết đủ tốt việc lập kế hoạch sạc chưa?
2. Rule tính quãng đường/pin/trạm sạc có đủ cho 70-80% case không, hay cần AI để giải thích và cá nhân hóa lịch trình?
3. Dữ liệu realtime về trạm sạc, giao thông, thời tiết và mức tiêu hao có đủ tin cậy không?
4. Nếu hệ thống đề xuất sai trạm sạc hoặc sai thời gian sạc, hậu quả là gì và fallback nên như thế nào?
```
