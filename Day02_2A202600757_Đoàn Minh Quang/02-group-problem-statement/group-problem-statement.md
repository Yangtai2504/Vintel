# 02 — Group Problem Statement

## Candidate nhóm chọn

Nhóm chọn đào sâu candidate:

```text
Chủ xe VinFast khi đi đường dài phải tự kiểm tra nhiều nguồn để lập lịch trình: % pin còn lại, quãng đường, trạm sạc nên dừng, thời gian sạc và thời điểm tiếp tục di chuyển.
```

Lý do chọn candidate này:

- Actor rõ: chủ xe VinFast đi đường dài/đi tỉnh.
- Workflow hiện tại vẽ được từ trước chuyến đi đến lúc điều chỉnh giữa đường.
- Bottleneck cụ thể: chủ xe phải tự ghép thông tin về pin, tuyến đường, trạm sạc, thời gian sạc và buffer an toàn.
- Metric đo được: thời gian lập kế hoạch, số nguồn/app phải kiểm tra, số lần đổi kế hoạch, mức độ tự tin trước chuyến đi.
- Có thể so sánh No AI / Rule / Workflow / Agent.
- Gắn trực tiếp với hệ sinh thái Vingroup qua VinFast và hạ tầng trạm sạc.

---

## Group convergence

Giả định nhóm có 9-12 candidates từ các thành viên. Các candidates được gom thành 4 cluster:

| Cluster | Candidates included | Pattern chung | Ghi chú |
|---|---|---|---|
| A. VinFast / mobility | Lập lịch trình sạc khi đi đường dài, tìm trạm sạc phù hợp, kết hợp Xanh SM/VinBus khi cần di chuyển tiếp | Người dùng phải ghép tuyến đường, pin, trạm sạc và thời gian | Cluster rõ workflow nhất |
| B. Hỗ trợ khách hàng đa dịch vụ | Cư dân Vinhomes gửi yêu cầu sai kênh, CSKH đọc context khách đa dịch vụ | Ma sát ở handoff giữa nhiều đơn vị | Tốt nhưng phụ thuộc dữ liệu vận hành nội bộ |
| C. Education / parent workflow | Phụ huynh Vinschool lọc thông báo, theo dõi deadline | Nhiều thông báo cần hành động | Có rủi ro privacy/trẻ em |
| D. Travel / healthcare planning | Khách Vinpearl/Vinmec chuẩn bị lịch, giấy tờ, quyền lợi | Cần checklist cá nhân hóa | Dễ chạm tư vấn nhạy cảm |

## Shortlist

| Candidate | Vì sao vào shortlist | Rủi ro / điều chưa rõ |
|---|---|---|
| Chủ xe VinFast lập lịch trình đi đường dài | Actor rõ, workflow rõ, metric dễ đo, gắn với VinFast | Cần dữ liệu realtime về trạm sạc, giao thông, mức tiêu hao |
| Cư dân Vinhomes gửi yêu cầu đa dịch vụ | Thể hiện rõ hệ sinh thái, có bottleneck routing | Cần log ticket hoặc data nội bộ |
| CSKH tóm tắt context khách hàng đa dịch vụ | AI fit mạnh, impact vận hành rõ | Phụ thuộc quyền truy cập dữ liệu nhiều hệ thống |

## Score để đồng thuận

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Chủ xe VinFast lập lịch trình đi đường dài | 5 | 5 | 4 | 5 | 5 | 5 | 4 | 33 |
| Cư dân Vinhomes gửi yêu cầu đa dịch vụ | 5 | 5 | 3 | 5 | 5 | 5 | 4 | 32 |
| CSKH tóm tắt context khách hàng đa dịch vụ | 4 | 5 | 3 | 5 | 4 | 5 | 3 | 29 |

Candidate nhóm chọn:

```text
Chủ xe VinFast lập lịch trình đi đường dài có tính đến pin và trạm sạc.
```

Vì sao không chọn các candidate còn lại:

- Cư dân Vinhomes gửi yêu cầu đa dịch vụ: tốt nhưng cần dữ liệu ticket/CSKH nội bộ để chứng minh baseline.
- CSKH tóm tắt context khách hàng đa dịch vụ: AI fit mạnh nhưng phụ thuộc data access và quyền riêng tư.

Nếu có disagreement, nhóm xử lý thế nào:

```text
Nhóm không vote ngay mà so theo 7 tiêu chí: actor, workflow, evidence, impact, scope lab, khả năng so sánh Rule/Workflow/Agent và mức hiểu domain. Candidate VinFast thắng vì workflow người dùng rõ hơn, metric dễ đo hơn và có thể validate bằng phỏng vấn chủ xe hoặc mô phỏng một chuyến đi.
```

---

## Quick validation

Do chưa có dữ liệu nội bộ VinFast, nhóm dùng validation nhẹ:

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Phỏng vấn nhanh chủ xe VinFast/xe điện | 3 người dự kiến hỏi | Hỏi lần gần nhất đi xa: có phải kiểm pin, trạm sạc, tuyến đường không; mất bao lâu; có lo lắng không | Nếu app hiện tại đã gợi ý đủ tốt thì pain yếu | Thu hẹp vào case đi đường dài, không phải di chuyển hằng ngày |
| Micro survey trong lớp/Discord | 5-10 người dự kiến hỏi | Người dùng xe điện có cần kế hoạch sạc trước khi đi xa không | Một số người ít đi xa nên pain không thường xuyên | Tập trung vào nhóm chủ xe hay đi tỉnh/đi du lịch |
| Mô phỏng chuyến đi | 2 tuyến giả định | Đo số nguồn cần mở và thời gian để lập kế hoạch | Dữ liệu công khai có thể không đủ realtime | Ghi rõ pilot cần data chính thức từ app/trạm sạc |

Insight sau validation giả định:

```text
Pain không phải "không biết có trạm sạc hay không". Pain nằm ở việc chủ xe phải tự nối nhiều biến số: pin hiện tại, quãng đường, trạm sạc phù hợp, thời gian dừng, buffer an toàn và thay đổi trên đường. AI chỉ có ích nếu biến các dữ liệu đó thành lịch trình dễ hiểu và có phương án dự phòng.
```

---

## Research giải pháp và bối cảnh

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| VinFast charging / charging station ecosystem | https://vinfastauto.com | Cung cấp thông tin về xe điện và hệ sinh thái sạc VinFast | Xác nhận bối cảnh xe điện/trạm sạc | Không đủ để chứng minh pain lập lịch trình | Cần kết hợp dữ liệu xe + trạm + tuyến đường |
| Google Maps / bản đồ điều hướng | https://maps.google.com | Tính tuyến đường và thời gian di chuyển | Mạnh về route/navigation | Không luôn biết chính xác % pin, tiêu hao xe, nhu cầu sạc | Route map là input, chưa phải toàn bộ solution |
| EV route planning pattern | https://abetterrouteplanner.com | Lập kế hoạch tuyến đường cho xe điện theo pin và sạc | Pattern rất gần bài toán | Có thể chưa tối ưu cho dữ liệu VinFast/VinFast charging tại Việt Nam | Hướng đúng là route planning có dữ liệu EV, không phải chatbot chung chung |
| Vingroup business areas | https://www.vingroup.net/en/business | Xác nhận VinFast là mảng quan trọng trong hệ sinh thái Vingroup | Bối cảnh hệ sinh thái | Không nói workflow người dùng cụ thể | Bài toán nên gắn vào một hành trình cụ thể của khách hàng VinFast |

Research takeaway:

```text
Không nên build một agent tự quyết mọi thứ cho tài xế. Hướng hợp lý hơn là Workflow: rule tính toán quãng đường, pin an toàn, trạm sạc và ràng buộc; AI dùng để giải thích lịch trình, so sánh các phương án và hỏi thêm preference của tài xế.
```

---

## Current workflow bản nhóm

```text
CURRENT STATE — 7 bước, 20-30 phút lập kế hoạch trước chuyến đi

[1 Chủ xe kiểm tra % pin hiện tại]
Input: thông tin pin trên xe/app
Output: % pin ban đầu
Thời gian: 1 phút

→ [2 Nhập điểm đến trên bản đồ]
Input: điểm đi, điểm đến
Output: tuyến đường, quãng đường, thời gian dự kiến
Thời gian: 2-3 phút

→ [3 Tìm trạm sạc trên hoặc gần tuyến]
Input: bản đồ trạm sạc/app VinFast/nguồn khác
Output: danh sách trạm có thể dừng
Thời gian: 5-10 phút
Bottleneck: phải tự tìm và lọc trạm phù hợp

→ [4 Ước lượng pin có đủ đến trạm/điểm đến không]
Input: % pin, quãng đường, kinh nghiệm tiêu hao
Output: quyết định cần dừng sạc hay không
Thời gian: 3-5 phút

→ [5 Chọn trạm dừng sạc]
Input: vị trí trạm, khoảng cách, tiện ích, độ an toàn pin
Output: trạm sạc dự kiến
Thời gian: 5 phút

→ [6 Tính thời gian sạc và lịch trình]
Input: % pin cần thêm, công suất sạc, lịch cá nhân
Output: lịch trình đi - dừng - sạc - đi tiếp
Thời gian: 5-10 phút
Bottleneck: phải tự tính và dễ thiếu buffer

→ [7 Kiểm tra lại khi có thay đổi trên đường]
Input: pin thực tế, giao thông, trạm sạc
Output: điều chỉnh kế hoạch
```

| Bước | Actor | Input | Output | Thời gian/tần suất | Ghi chú |
|---|---|---|---|---|---|
| 1 | Chủ xe | % pin | Pin ban đầu | 1 phút | Input quan trọng nhất |
| 2 | Chủ xe | Điểm đến | Route/quãng đường | 2-3 phút | Dùng bản đồ |
| 3 | Chủ xe | Danh sách trạm | Trạm khả thi | 5-10 phút | Bottleneck |
| 4 | Chủ xe | Pin + quãng đường | Ước lượng đủ/không | 3-5 phút | Dựa nhiều vào kinh nghiệm |
| 5 | Chủ xe | Trạm khả thi | Trạm chọn | 5 phút | Cần so sánh nhiều yếu tố |
| 6 | Chủ xe | Công suất sạc/lịch trình | Thời gian dừng | 5-10 phút | Bottleneck |
| 7 | Chủ xe | Dữ liệu thực tế | Điều chỉnh | Trong chuyến đi | Cần fallback |

Bottleneck chính:

```text
Bottleneck nằm ở bước 3-6: chủ xe phải tự tìm trạm, tự ước lượng pin, tự chọn điểm dừng và tự tính thời gian sạc. Đây là workflow nhiều dữ liệu nhưng quyết định cuối vẫn thuộc về tài xế.
```

---

## Future workflow bản nhóm

```text
FUTURE STATE — dưới 5 phút để có lịch trình sạc ban đầu

[1 Chủ xe nhập điểm đến hoặc chọn lịch trình]
Input: điểm đi, điểm đến, thời gian mong muốn
Output: nhu cầu chuyến đi
Thời gian: 1 phút

→ [2 App lấy % pin, loại xe và dữ liệu tuyến đường]
Input: xe, app, bản đồ
Output: pin ban đầu, route, quãng đường
Thời gian: <1 phút

→ [3 Rule tính ngưỡng pin an toàn và trạm khả thi]
Input: pin, route, trạm sạc, buffer
Output: danh sách trạm phù hợp
Thời gian: <1 phút

→ [4 Workflow/AI đề xuất 1-3 lịch trình dễ hiểu]
Input: danh sách trạm + preference tài xế
Output: phương án nhanh nhất, an toàn nhất, ít dừng nhất
Thời gian: 1 phút

→ [5 Tài xế chọn phương án]
Input: các phương án
Output: lịch trình được chọn
Thời gian: 1 phút

→ [6 App theo dõi và nhắc khi cần điều chỉnh]
Input: pin thực tế, giao thông, trạng thái trạm nếu có
Output: cảnh báo/đề xuất điều chỉnh
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Thời gian lập kế hoạch | 20-30 phút | Dưới 5 phút | Metric chính |
| Số nguồn/app phải kiểm tra | 3-4 | 1 | Giảm ma sát |
| Số lần tự tính pin/thời gian sạc | Nhiều lần | 0-1 lần | Rule/workflow tính giúp |
| Số lần đổi kế hoạch giữa đường | Chưa có baseline | Giảm 30-50% trong pilot | Cần đo thực tế |
| Mức tự tin trước chuyến đi | Chưa đo | Tăng qua survey 1-5 | Metric cảm nhận |
| Risk mới | Tài xế tự chịu trách nhiệm | Hệ thống đề xuất sai/thiếu realtime | Cần boundary và fallback |

Boundary:

- AI không cam kết tuyệt đối xe chắc chắn đến được trạm/điểm đến.
- AI không thay tài xế quyết định lái xe, dừng xe hay tiếp tục đi.
- AI không được che giấu độ không chắc chắn của dữ liệu trạm sạc, giao thông, thời tiết hoặc mức tiêu hao.
- Nếu thiếu dữ liệu realtime, hệ thống phải dùng phương án an toàn hơn và nói rõ cần kiểm tra lại.
- Các cảnh báo an toàn phải ưu tiên rule rõ ràng hơn là câu trả lời linh hoạt của AI.

---

## Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Chủ xe VinFast đi đường dài/đi tỉnh. |
| **Workflow** | Trước chuyến đi, chủ xe kiểm tra % pin, nhập điểm đến, tìm trạm sạc, ước lượng có đủ pin không, chọn trạm dừng, tính thời gian sạc và điều chỉnh nếu có thay đổi. |
| **Bottleneck** | Chủ xe phải tự ghép nhiều nguồn thông tin và tự tính kế hoạch sạc, đặc biệt ở bước tìm trạm, chọn điểm dừng và tính thời gian sạc. |
| **Impact** | Mất 20-30 phút chuẩn bị, phải kiểm tra nhiều app/nguồn, dễ lo lắng hoặc đổi kế hoạch giữa đường. |
| **Success Metric** | Giảm thời gian lập kế hoạch xuống dưới 5 phút; giảm số nguồn/app phải kiểm tra xuống 1; giảm số lần đổi kế hoạch sạc giữa đường. |
| **Boundary** | AI không tự quyết định thay tài xế, không cam kết tuyệt đối về trạm/giao thông/pin, phải có phương án dự phòng khi dữ liệu không chắc chắn. |

Điểm còn yếu của v0:

- Chưa có baseline thật từ chủ xe VinFast.
- Chưa biết app hiện tại đã hỗ trợ lập kế hoạch sạc đến mức nào.
- Chưa tách rõ phần rule tính toán và phần AI giải thích/cá nhân hóa.

---

## Ma trận độ phù hợp với AI

Bài toán của nhóm nằm ở ô:

```text
Độ mơ hồ trung bình, độ phức tạp trung bình.
```

Vì sao:

- Mơ hồ trung bình: tài xế có nhiều preference khác nhau, ví dụ nhanh nhất, an toàn pin nhất, ít dừng nhất, dừng ở nơi có tiện ích.
- Phức tạp trung bình: cần nối nhiều dữ liệu như pin, route, trạm sạc, thời gian, buffer an toàn.
- Tuy nhiên bài toán vẫn có workflow tuyến tính, chưa cần agent tự lập kế hoạch mở rộng hoặc tự gọi nhiều công cụ không kiểm soát.

---

## So sánh No AI / Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI / process fix** | Hướng dẫn/checklist trước chuyến đi, danh sách trạm sạc, tips giữ pin | Đủ nếu người dùng ít đi xa hoặc đã quen | Vẫn bắt người dùng tự tính và tự ghép nguồn | Không chọn làm toàn bộ |
| **Rule** | Tính quãng đường, pin an toàn, trạm gần tuyến, cảnh báo pin thấp theo ngưỡng cố định | Đủ cho case đơn giản, dữ liệu rõ | Khó giải thích phương án, khó cá nhân hóa theo ưu tiên tài xế | Dùng làm nền |
| **Workflow** | Rule tính dữ liệu cứng → AI/UX giải thích 1-3 phương án → tài xế chọn → app theo dõi và nhắc điều chỉnh | Phù hợp vì workflow rõ, AI hỗ trợ diễn giải/cá nhân hóa | Đề xuất sai nếu dữ liệu realtime thiếu | Chọn |
| **Agent** | Agent tự theo dõi chuyến đi, tự đổi route, tự chọn trạm, tự đặt lịch/dịch vụ liên quan | Chỉ cần nếu có nhiều công cụ và nhiều bước động cần tự quyết | Rủi ro an toàn, permission và trách nhiệm pháp lý | Chưa chọn |

Mức chọn:

```text
Workflow.
```

Vì sao chọn:

```text
Workflow phù hợp nhất vì phần tính toán cứng nên dùng rule, còn AI chỉ nên giúp giải thích phương án, hỏi preference và trình bày lịch trình dễ hiểu. Tài xế vẫn chọn phương án cuối cùng.
```

Vì sao không chọn mức đơn giản hơn:

```text
Rule đủ để tính pin/quãng đường/trạm sạc trong case đơn giản, nhưng chưa giải quyết tốt phần người dùng phải hiểu và so sánh phương án. Chủ xe có thể ưu tiên nhanh nhất, ít dừng nhất hoặc an toàn pin nhất; AI/Workflow giúp diễn giải và cá nhân hóa.
```

Vì sao không chọn Agent:

```text
Agent quá rộng và rủi ro cho pilot, vì liên quan an toàn di chuyển. Chưa nên để AI tự đổi lịch trình hoặc tự quyết định thay tài xế khi dữ liệu realtime có thể không chắc chắn.
```

---

## Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Chủ xe VinFast đi đường dài/đi tỉnh, đặc biệt là người chưa quen lập kế hoạch sạc hoặc đi tuyến mới. |
| **Workflow** | Kiểm tra % pin → nhập điểm đến → xem tuyến đường → tìm trạm sạc → ước lượng có đủ pin không → chọn trạm dừng → tính thời gian sạc → điều chỉnh khi có thay đổi. |
| **Bottleneck** | Bước tìm trạm sạc, ước lượng pin và tính lịch trình sạc mất thời gian vì chủ xe phải tự ghép nhiều nguồn dữ liệu. |
| **Impact** | Mất 20-30 phút lập kế hoạch; phải kiểm tra 3-4 nguồn/app; tăng lo lắng khi đi xa; dễ phải đổi kế hoạch sạc giữa đường. |
| **Success Metric** | Giảm thời gian lập kế hoạch xuống dưới 5 phút; giảm số nguồn/app phải kiểm tra xuống 1; giảm số lần đổi kế hoạch sạc giữa đường; tăng điểm tự tin trước chuyến đi qua survey 1-5. |
| **Boundary** | AI không tự quyết định thay tài xế, không cam kết tuyệt đối tình trạng trạm/giao thông/pin, không che giấu độ không chắc chắn, phải có fallback an toàn. |
| **AI intervention point** | Sau khi có điểm đến, % pin, loại xe và tuyến đường: workflow/rule tính dữ liệu cứng, AI diễn giải 1-3 phương án lịch trình và hỏi preference nếu thiếu. |
| **Mức chọn** | Workflow: rule tính pin/trạm/route, AI giải thích và cá nhân hóa lịch trình, tài xế chọn. |
| **Rủi ro & người thật kiểm tra** | Rủi ro: dữ liệu trạm sạc không realtime, mức tiêu hao thay đổi do tốc độ/thời tiết/tải xe, đề xuất sai trạm. Người kiểm tra: tài xế xác nhận phương án; app hiển thị độ tin cậy và phương án dự phòng. |

---

## Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? | Yes | Chủ xe VinFast đi đường dài, workflow sạc rõ |
| Baseline và success metric đã đo được chưa? | Not Yet | Có metric đề xuất nhưng cần phỏng vấn/mô phỏng chuyến đi |
| Có data/input đủ dùng chưa? | Not Yet | Cần dữ liệu xe, trạm sạc, route, trạng thái trạm nếu có |
| Nếu AI sai, hậu quả có chấp nhận được không? | Yes, nếu giới hạn scope | AI chỉ đề xuất; tài xế quyết định; dùng fallback an toàn |
| Có người review/owner vận hành không? | Yes | Chủ xe là người chọn phương án; VinFast/app là owner sản phẩm |
| Có cách non-AI đơn giản hơn không? | Yes, nhưng chưa đủ | Rule tính toán là nền bắt buộc, nhưng cần workflow/AI để diễn giải/cá nhân hóa |

Decision:

```text
Not Yet → Go pilot nhỏ sau khi validate với chủ xe và dữ liệu mẫu.
```

Lý do:

```text
Bài toán rõ và phù hợp Workflow, nhưng chưa nên Go triển khai thật nếu chưa có baseline từ chủ xe và dữ liệu realtime về trạm sạc/tuyến đường. Quyết định hợp lý là Not Yet cho production, nhưng Go pilot nhỏ với dữ liệu mô phỏng hoặc dữ liệu mẫu.
```

Pilot nhỏ nhất:

```text
1. Chọn 2-3 tuyến đường dài phổ biến, ví dụ Hà Nội - Hạ Long, Hà Nội - Ninh Bình, TP.HCM - Vũng Tàu.
2. Thu input mẫu: loại xe, % pin xuất phát, điểm đi, điểm đến, mức pin an toàn mong muốn.
3. Tạo rule tính trạm sạc khả thi và buffer pin.
4. Cho workflow/AI đề xuất 1-3 lịch trình: nhanh nhất, an toàn nhất, ít dừng nhất.
5. Nhờ 3-5 chủ xe hoặc người hiểu xe điện đánh giá: dễ hiểu không, có tin tưởng không, có cần kiểm tra thêm nguồn khác không.
6. Đo thời gian lập kế hoạch, số nguồn phải kiểm tra lại, tỷ lệ phương án được chấp nhận.
```

Exit / rollback:

```text
- Nếu phương án được đánh giá đúng/hợp lý dưới 80%, chỉ dùng rule + bản đồ trạm sạc, chưa dùng AI giải thích.
- Nếu dữ liệu trạm sạc không đủ tin cậy, tăng buffer pin và buộc hiển thị cảnh báo kiểm tra lại.
- Nếu chủ xe vẫn phải kiểm tra 3-4 nguồn sau khi dùng workflow, problem chưa được giải quyết.
```
