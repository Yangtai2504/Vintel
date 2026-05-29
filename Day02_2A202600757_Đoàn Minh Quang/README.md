# Day 02 Lab — Tìm Đúng Bài Toán Cho AI

## Thông tin học viên

- Họ tên: Đoàn Minh Quang
- Mã học viên: 2A202600757
- Lab: Day 02 — Tìm Đúng Bài Toán Cho AI

## Chủ đề bài làm

**Các vấn đề em thấy trong hệ sinh thái Vingroup — VinFast hỗ trợ chủ xe lập lịch trình đi đường dài có tính đến pin và trạm sạc.**

Bài làm đào sâu vấn đề: chủ xe VinFast khi đi đường dài phải tự kiểm tra nhiều nguồn để lập lịch trình, gồm % pin còn lại, quãng đường, trạm sạc nên dừng, thời gian sạc và thời điểm tiếp tục di chuyển. Trọng tâm không phải "xây AI agent tự quyết định thay tài xế", mà là làm rõ workflow lập kế hoạch sạc, bottleneck ghép nhiều nguồn dữ liệu, metric, boundary và mức AI phù hợp.

Kết luận chính: chọn **Workflow** thay vì Agent. Quyết định cuối là **Not Yet cho triển khai thật, Go pilot nhỏ sau khi có baseline từ chủ xe và dữ liệu mẫu về tuyến đường/trạm sạc**.

## Cấu trúc bài nộp

Repo này gồm 3 phần:

1. `01-individual-problem-scan/`  
   Phần scan vấn đề cá nhân, gồm danh sách các vấn đề quan sát được, Top 3 Problem Cards và workflow draft.

2. `02-group-problem-statement/`  
   Bản nộp nhóm, gồm quá trình chọn vấn đề, validation/research, workflow hiện tại, workflow sau tối ưu, Problem Statement, metric, boundary, lựa chọn Rule / Workflow / Agent và quyết định cuối.

3. `03-individual-reflection/`  
   Reflection cá nhân về cách dùng AI, vai trò trong nhóm, bài học rút ra và điều sẽ cải thiện nếu làm lại.

## Tóm tắt quyết định

- Actor chính: chủ xe VinFast đi đường dài/đi tỉnh.
- Bottleneck: tự kiểm tra % pin, tuyến đường, trạm sạc, thời gian sạc và tự ghép thành lịch trình.
- Metric chính: thời gian lập kế hoạch, số nguồn/app phải kiểm tra, số lần đổi kế hoạch sạc, mức tự tin trước chuyến đi.
- Mức AI chọn: Workflow.
- Boundary: AI không tự quyết định thay tài xế, không cam kết tuyệt đối tình trạng trạm/giao thông/pin, phải hiển thị độ không chắc chắn và phương án dự phòng.
