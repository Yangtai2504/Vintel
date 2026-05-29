# 03 — Individual Reflection

## Tôi đã tham gia vào phần nào?

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng |
|---|---|---|
| Scan cá nhân | Tôi scan các vấn đề trong hệ sinh thái Vingroup, gồm Vinhomes, VinFast, Vinmec, Vinschool, Vinpearl. | Có 10 candidate problems từ nhiều góc nhìn, không bắt đầu bằng solution AI. |
| Pitch Problem Card | Tôi pitch problem chủ xe VinFast phải tự kiểm tra nhiều nguồn khi lên lịch trình đi đường dài. | Candidate này được chọn vì actor rõ, workflow rõ, metric đo được và có bottleneck cụ thể. |
| Challenge bài của bạn khác | Tôi đặt câu hỏi liệu các bài khác có quá phụ thuộc data nội bộ, privacy hoặc quyền truy cập hệ thống không. | Nhóm ưu tiên bài VinFast vì có thể mô phỏng/validate dễ hơn trong lab. |
| Gom trùng / cluster | Tôi gom các vấn đề thành nhóm: VinFast/mobility, hỗ trợ khách hàng đa dịch vụ, education, travel/healthcare. | Nhóm thấy bài VinFast thuộc cluster mobility và có workflow rõ nhất. |
| Chọn candidate problem | Tôi ủng hộ candidate chủ xe VinFast lập lịch trình sạc khi đi đường dài. | Nhóm có bài toán đủ cụ thể để viết workflow, metric và boundary. |
| Validation / research | Tôi đề xuất phỏng vấn nhanh chủ xe/xe điện và mô phỏng một số tuyến đường dài. | Nhóm có hướng kiểm chứng pain bằng thời gian lập kế hoạch, số app phải kiểm tra và mức tự tin trước chuyến đi. |
| Workflow nhóm | Tôi đóng góp workflow current/future: kiểm pin, nhập điểm đến, tìm trạm, ước lượng pin, chọn điểm dừng, tính thời gian sạc. | Workflow giúp nhóm thấy AI chỉ nên vào bước lập kế hoạch/diễn giải, không thay tài xế quyết định. |
| Problem Statement | Tôi giúp viết PS v0/v1 với actor, bottleneck, impact, success metric, boundary và AI intervention point. | Problem Statement rõ hơn, có metric và giới hạn trách nhiệm của AI. |
| Rule / Workflow / Agent | Tôi lập luận chọn Workflow thay vì Agent. | Nhóm thống nhất rule tính dữ liệu cứng, AI giải thích/cá nhân hóa lịch trình, tài xế chọn. |
| Decision | Tôi đề xuất Not Yet cho triển khai thật, nhưng Go pilot nhỏ sau khi validate với chủ xe và dữ liệu mẫu. | Quyết định có điều kiện, không solution-first. |

---

## Bảng dùng AI trong reflection

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Gợi ý thêm problem trong hệ sinh thái Vingroup theo 4 lăng kính. | Giúp mở rộng từ hỗ trợ cư dân sang VinFast, Vinschool, Vinmec, Vinpearl. | AI dễ gợi ý quá rộng kiểu "trợ lý AI cho toàn bộ hệ sinh thái". | Tôi giữ lại những problem có actor, workflow và metric đo được. |
| Problem Card | Nhờ AI phản biện actor, bottleneck, metric và AI-fit. | Giúp thấy bài VinFast mạnh vì có input rõ: % pin, điểm đến, trạm sạc, thời gian. | AI có xu hướng biến bài toán thành agent tự quyết lịch trình. | Tôi hạ scope về Workflow: AI đề xuất, tài xế quyết định. |
| Workflow | Nhờ AI hỗ trợ chuyển mô tả thành before/after workflow. | Giúp tách rõ các bước trước chuyến đi và trong chuyến đi. | AI ban đầu gộp phần rule tính toán và AI giải thích vào một bước. | Tôi tách rule tính pin/trạm/route và AI diễn giải phương án. |
| Research | Dùng AI/search để tìm pattern tương tự như EV route planning. | Giúp nhận ra bài toán gần với route planning cho xe điện hơn là chatbot. | Nguồn công khai không chứng minh chủ xe VinFast thật sự mất bao lâu. | Tôi ghi rõ cần phỏng vấn hoặc mô phỏng tuyến đường để có baseline. |
| Problem Statement | Nhờ AI kiểm xem field nào còn mơ hồ. | Giúp bổ sung success metric và boundary. | AI có thể viết quá chắc dù thiếu dữ liệu realtime. | Tôi đổi decision thành Not Yet → Go pilot nhỏ. |
| Rule / Workflow / Agent | Dùng AI để so sánh Rule/Workflow/Agent. | Giúp thấy Rule là nền bắt buộc cho pin/trạm/route, còn AI chỉ nên cá nhân hóa và giải thích. | AI dễ đề xuất Agent vì nghe hiện đại hơn. | Tôi chọn Workflow vì an toàn hơn và phù hợp pilot. |
| Decision | Nhờ AI phản biện Go/Not Yet/No-Go. | Giúp thêm exit/rollback cho pilot. | AI đôi khi xem nhẹ rủi ro an toàn khi dữ liệu trạm sạc không realtime. | Tôi thêm fallback: tăng buffer pin, hiển thị độ không chắc chắn, tài xế xác nhận cuối. |

---

## Reflection câu hỏi mở

### Tôi học được gì khi nghe top 3 problems của các bạn khác?

Tôi học được rằng problem tốt không nhất thiết là problem rộng nhất. Bài "AI cho toàn bộ hệ sinh thái Vingroup" nghe lớn nhưng khó đo. Bài VinFast đi đường dài hẹp hơn, nhưng lại rõ actor, rõ workflow và dễ biết AI nên hỗ trợ ở đâu.

### Nhóm có lúc nào bị solution-first không?

Có. Lúc đầu tôi dễ nghĩ đến một agent tự lập lịch trình, tự đổi route và tự quyết định điểm sạc. Sau khi bám worksheet, tôi nhận ra như vậy quá rủi ro vì liên quan an toàn di chuyển và dữ liệu realtime. Nhóm kéo lại về problem: chủ xe phải tự ghép nhiều nguồn thông tin khi lên kế hoạch sạc.

### Tôi có thay đổi ý kiến sau khi bị challenge không?

Có. Ban đầu tôi nghĩ AI có thể tự đề xuất gần như toàn bộ lịch trình. Sau khi bị challenge về tình trạng trạm sạc, giao thông, thời tiết và mức tiêu hao thực tế, tôi đồng ý rằng AI chỉ nên đề xuất phương án và giải thích, còn tài xế quyết định cuối cùng.

### Tôi đóng góp gì thật sự vào artifact cuối?

Tôi đóng góp hướng domain VinFast, Problem Card chính, workflow before/after và lập luận chọn Workflow thay vì Agent. Tôi cũng đề xuất decision Not Yet cho triển khai thật vì chưa có baseline thật, nhưng vẫn có thể Go pilot nhỏ với 2-3 tuyến đường mô phỏng và input mẫu.

### Điều khó nhất khi viết Problem Statement là gì?

Khó nhất là boundary. Nếu chỉ nói "AI lập lịch trình sạc" thì dễ bị hiểu là AI chịu trách nhiệm thay tài xế. Tôi phải viết rõ AI không cam kết tuyệt đối, không thay quyết định lái xe, không che giấu độ không chắc chắn của dữ liệu và phải có phương án dự phòng.

### Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?

Nếu làm lại, tôi sẽ challenge mạnh hơn ở phần evidence. Tôi muốn phỏng vấn ít nhất 3 chủ xe VinFast hoặc người dùng xe điện, hỏi họ lần gần nhất đi xa mất bao lâu để lên kế hoạch, mở bao nhiêu app, có phải đổi trạm sạc giữa đường không. Khi có baseline thật, decision sẽ chắc hơn.

---

## Tự kiểm cuối bài

- [x] Cá nhân có 5+ problems và top 3 Problem Cards.
- [x] Có scan rộng hơn yêu cầu: 10 problems.
- [x] Có Problem Card rõ actor, workflow, bottleneck, impact, metric.
- [x] Có draft workflow trước/sau cho top 3.
- [x] Nhóm có nhật ký hội tụ từ candidates về 1 bài.
- [x] Nhóm có validation/research, nhưng ghi rõ phần nào còn là giả định.
- [x] Nhóm có workflow trước/sau.
- [x] Nhóm có Problem Statement v0/v1 với metric và boundary.
- [x] Nhóm có so sánh No AI / Rule / Workflow / Agent.
- [x] Nhóm có decision Not Yet → Go pilot nhỏ và lý do rõ.
- [x] Reflection cá nhân nói rõ vai trò, cách dùng AI, điểm AI sai/hời hợt và điều tôi tự sửa.

---

## Kết luận cá nhân

Qua lab này, tôi hiểu rằng tìm đúng bài toán cho AI không phải là chọn use case nghe hiện đại nhất, mà là chọn workflow có pain thật, bottleneck rõ và metric đo được. Với VinFast, bài toán lập lịch trình đi đường dài có nhiều dữ liệu như pin, route, trạm sạc và thời gian, nhưng không có nghĩa là cần Agent ngay.

Bài học quan trọng nhất của tôi là: dùng rule cho phần tính toán cứng, dùng AI cho phần giải thích/cá nhân hóa, và để con người quyết định ở điểm có rủi ro. Nếu chưa có baseline và dữ liệu realtime đủ chắc, quyết định trung thực nhất là Not Yet cho production, Go pilot nhỏ để học thêm.
