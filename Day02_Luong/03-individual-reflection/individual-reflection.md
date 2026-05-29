# 03 — Individual Reflection

## Vai trò chính

Tôi phụ trách chính phần **operations workflow và metric**. Trong nhóm, tôi đưa ra 3 candidate:

1. VinFast Service Center tổng hợp báo cáo hiệu suất sửa chữa từ CRM, SAP và hệ thống kỹ thuật.
2. CSKH VinID kiểm tra lịch sử điểm thưởng và điều kiện khuyến mại.
3. Quản lý VinPearl tổng hợp yêu cầu phòng/dịch vụ từ PMS, email, chat để lập kế hoạch cuối tuần.

Vai trò của tôi là giúp nhóm nhìn các bài toán vận hành có workflow rõ, nguồn dữ liệu rõ và metric thời gian cụ thể.

---

## Tôi đã tham gia vào phần nào?

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng |
|---|---|---|
| Scan cá nhân | Tôi đưa ra 3 problem vận hành trong VinFast Service Center, VinID CSKH và VinPearl resort. | Nhóm có thêm các candidate có metric và workflow vận hành rõ. |
| Pitch Problem Card | Tôi pitch bài VinFast Service Center weekly report vì có baseline 90 phút/tuần. | Bài này được vào shortlist vì impact đo được. |
| Challenge bài của bạn khác | Tôi hỏi candidate VinFast route planning đo metric thế nào nếu chưa có dữ liệu thật. | Nhóm thêm pilot mô phỏng 2-3 tuyến đường. |
| Gom trùng / cluster | Tôi giúp tách nhóm operations nội bộ khỏi customer journey. | Nhóm thấy #7 mạnh về metric nhưng khó access data nội bộ. |
| Chọn candidate problem | Tôi đồng ý chọn bài chủ xe VinFast vì dễ validate ngoài hệ thống nội bộ hơn. | Nhóm không bị kẹt ở CRM/SAP/PMS khó truy cập. |
| Validation / research | Tôi đề xuất đo thời gian lập kế hoạch và số nguồn/app phải kiểm tra. | Metric của bài VinFast cụ thể hơn. |
| Workflow nhóm | Tôi góp ý current workflow cần tách bước tìm trạm và bước tính thời gian sạc. | Bottleneck được xác định rõ ở bước 3-6. |
| Problem Statement | Tôi góp ý success metric không chỉ là "nhanh hơn" mà phải có số. | PS v1 có target dưới 5 phút và số nguồn giảm về 1. |
| Rule / Workflow / Agent | Tôi chỉ ra phần tính pin/quãng đường nên dùng rule trước. | Nhóm không để AI xử lý phần tính toán cứng một cách mơ hồ. |
| Decision | Tôi ủng hộ pilot nhỏ với dữ liệu mẫu. | Decision có cách đo pilot cụ thể. |

---

## Bảng dùng AI

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Gợi ý problem operations trong hệ sinh thái Vin. | Giúp nhớ thêm Service Center, CSKH, resort ops. | Một số ý quá phụ thuộc hệ thống nội bộ. | Tôi chọn ý có workflow và metric rõ. |
| Workflow | Nhờ AI chuyển mô tả VinFast route planning thành before/after flow. | Giúp sắp xếp bước theo thứ tự. | AI gộp bước tìm trạm và tính sạc. | Tôi tách ra vì đây là hai bottleneck khác nhau. |
| Metric | Hỏi AI gợi ý success metrics. | Có thêm số nguồn/app, thời gian lập kế hoạch, số lần đổi kế hoạch. | Một số metric khó đo ngay. | Tôi chọn metric đo được trong pilot. |
| Problem Statement | Nhờ AI kiểm metric còn mơ hồ không. | Giúp sửa từ "nhanh hơn" thành dưới 5 phút. | AI tự tin với baseline chưa có. | Tôi ghi rõ baseline cần validate. |
| Decision | Hỏi AI về pilot nhỏ nhất. | Gợi ý mô phỏng tuyến đường. | Chưa đủ chi tiết về exit criteria. | Tôi thêm điều kiện rollback. |

---

## Reflection

Tôi học được rằng workflow vận hành thường rất dễ có metric, nhưng không phải lúc nào cũng phù hợp để làm trong lab nếu cần data nội bộ. Bài VinFast Service Center của tôi có baseline tốt, nhưng cần CRM, SAP và hệ thống kỹ thuật nên nhóm khó kiểm chứng trong thời gian ngắn.

Tôi đóng góp mạnh nhất ở phần workflow và metric. Với bài VinFast đi đường dài, nếu chỉ nói "giúp lập lịch trình" thì vẫn mơ hồ. Khi tách thành các bước kiểm pin, nhập điểm đến, tìm trạm, ước lượng pin, chọn trạm và tính thời gian sạc, nhóm thấy rõ bottleneck nằm ở đâu.

Nếu làm lại, tôi sẽ chuẩn bị một bảng đo thử cho một tuyến đường cụ thể để có baseline thật hơn: mất bao lâu, mở bao nhiêu nguồn, có bao nhiêu điểm quyết định cần tự tính.

---

## Tự kiểm

- [x] Có nêu vai trò operations/workflow/metric.
- [x] Có đóng góp vào shortlist và score.
- [x] Có metric cụ thể.
- [x] Có nói rõ vì sao không chọn candidate của mình.
