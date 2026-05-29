# 01 — Individual Problem Scan

> **Cá nhân làm.** Problem first, AI second. Vẽ workflow trước khi chọn bất kỳ giải pháp nào.
>
> Góc nhìn: người dùng hệ sinh thái Vin — không phải nhân viên, không phải vận hành nội bộ.

---

## Phase 1 — Bảng Scan (10 problems)

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Tốn thời gian | Nhận kết quả xét nghiệm từ Vinmec, các chỉ số dùng thuật ngữ y tế khó hiểu, phải tự tra Google nhưng vẫn không chắc hiểu đúng | Bệnh nhân / thân nhân nhận kết quả | 20-30 phút/lần tra; lo lắng dù kết quả bình thường; phải chờ gặp bác sĩ mới dám chắc |
| 2 | Tốn thời gian | Đặt lịch khám Vinmec phải tự chọn đúng chuyên khoa và bác sĩ dù không biết triệu chứng của mình thuộc chuyên khoa nào | Người dùng app MyVinmec | 10-15 phút/lần; hay chọn nhầm chuyên khoa; không có gợi ý từ triệu chứng |
| 3 | Tốn thời gian | Lên kế hoạch đi Vinpearl phải tra giá phòng, vé VinWonders, nhà hàng, di chuyển từ 4-5 trang/app riêng lẻ rồi tự tổng hợp | Khách cá nhân / nhóm bạn muốn đi Vinpearl | 45-60 phút/lần; mở 4-5 tab; hay bỏ sót gói combo tiết kiệm hơn đặt lẻ |
| 4 | Lặp lại | Điểm VinID tích lũy từ Xanh SM, WinMart, Vinmec,… nhưng không biết tổng điểm là bao nhiêu và có thể đổi gì có giá trị nhất | Người dùng VinID dùng nhiều dịch vụ | Điểm hay hết hạn không dùng; không biết dùng vào đâu; phải browse danh sách đổi điểm dài |
| 5 | Lặp lại | Đặt xe Xanh SM xong phải nhìn vào app liên tục theo dõi tài xế vì ước tính thời gian đến hay sai thực tế | Người dùng Xanh SM | "3 phút" có khi thành 10 phút; phải xem màn hình liên tục khi chờ; không có thông báo đẩy chính xác |
| 6 | AI có thể tốt hơn | Cư dân Vinhomes muốn báo sự cố (thang máy, điện, nước) phải gọi hotline, chờ máy, nhắc lại vấn đề, không theo dõi được tiến độ xử lý | Cư dân Vinhomes | Hotline bận giờ cao điểm; không biết sự cố đã được nhận chưa; phải gọi lại hỏi tiến độ |
| 7 | Tốn thời gian | Người dùng xe VinFast muốn tìm trạm sạc trống gần nhất khi pin gần hết nhưng app không hiển thị realtime tình trạng trạm (trống/bận/hỏng) | Chủ xe VinFast | Đến trạm rồi mới biết đầy; range anxiety khi đi đường dài; phải gọi hỏi trực tiếp |
| 8 | Pain từ người khác | Phụ huynh có con học ở VinUni / VinSchool cần theo dõi thông báo từ trường nhưng thông báo đến từ nhiều kênh (app, email, Zalo, bảng tin) không tổng hợp vào một nơi | Phụ huynh, học sinh | Hay bỏ sót thông báo quan trọng; phải check 3-4 nơi mỗi ngày |
| 9 | AI có thể tốt hơn | Sau chuyến nghỉ Vinpearl không có tóm tắt trải nghiệm và gợi ý cá nhân hóa cho lần đi tiếp dựa trên lịch sử phòng đã ở, hoạt động đã làm | Khách Vinpearl quay lại | Mỗi lần đặt lại từ đầu; không nhớ phòng nào đã ở; không biết có hoạt động mới phù hợp không |
| 10 | Lặp lại | Mua sắm ở WinMart không biết trước sản phẩm nào đang giảm giá hôm nay, phải đi loanh quanh hoặc tra từng sản phẩm trong app | Người mua sắm WinMart | Hay bỏ sót ưu đãi ngay hôm đó; mua xong mới thấy giá rẻ hơn; không có view "ưu đãi theo ngày" |

---

## Phase 2 — Top 3 Problem Cards

### Tiêu chí chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Kết quả xét nghiệm Vinmec khó hiểu (#1) | Workflow rõ nhất; metric thời gian đo được; AI intervention point rõ (giải thích ngôn ngữ y tế, không chẩn đoán); boundary an toàn | Ranh giới "giải thích" vs "chẩn đoán" cần thiết kế rất cẩn thận |
| 2 | Lên kế hoạch đi Vinpearl (#3) | Workflow lặp lại mỗi lần đặt; metric thời gian rõ; đã từng trải qua pain này thật | Dữ liệu giá/phòng/vé thay đổi realtime, cần API sống chứ không phải dữ liệu tĩnh |
| 3 | Điểm VinID rải rác (#4) | Lặp lại thường xuyên; ảnh hưởng trực tiếp vì dùng nhiều dịch vụ Vin; metric (tỷ lệ điểm hết hạn) đo được | Cần truy cập dữ liệu giao dịch cá nhân — privacy/permission phức tạp |

---

### Problem Card #1 — Kết quả xét nghiệm Vinmec khó hiểu

```
┌──────────────────────────────────────────────────────────┐
│ PROBLEM CARD #1                                          │
│                                                          │
│ Problem 1 câu: Bệnh nhân nhận kết quả xét nghiệm        │
│ Vinmec phải tra Google 20-30 phút vì thuật ngữ y tế      │
│ khó hiểu mà vẫn không dám chắc mình hiểu đúng.          │
│                                                          │
│ Ai đang đau? Bệnh nhân / thân nhân nhận kết quả          │
│                                                          │
│ Workflow hiện tại:                                       │
│ 1. Nhận PDF → 2. Đọc chỉ số → 3. Thấy ↑↓               │
│ → 4. Tra Google → 5. Thông tin không nhất quán          │
│ → 6. Chờ gặp bác sĩ hỏi lại                             │
│                                                          │
│ Bước nghẽn nhất: Tra Google từng chỉ số (20-30')         │
│                                                          │
│ Đo thành công bằng gì?                                   │
│ Giảm thời gian hiểu kết quả từ 20-30' → dưới 3'         │
│                                                          │
│ Quick gut: □ No AI □ Rule  ■ Workflow                    │
│            □ Agent □ Chưa biết                           │
└──────────────────────────────────────────────────────────┘
```

**Problem 1 câu:**
Bệnh nhân nhận kết quả xét nghiệm Vinmec phải tra Google 20-30 phút để hiểu từng chỉ số y tế, nhưng thông tin rời rạc và không nhất quán khiến vẫn không dám chắc hiểu đúng.

**Actor:**
Bệnh nhân hoặc thân nhân nhận file kết quả xét nghiệm từ Vinmec (qua app MyVinmec hoặc quầy).

**Thời điểm / bối cảnh:**
Ngay sau khi nhận kết quả xét nghiệm, trước buổi tư vấn kết quả với bác sĩ — thường có khoảng thời gian chờ từ vài giờ đến vài ngày.

**Current workflow:**
1. Nhận file PDF kết quả từ app MyVinmec hoặc quầy lấy kết quả
2. Mở file, đọc danh sách chỉ số (HbA1c, WBC, ALT, Creatinine,...)
3. Thấy chỉ số có mũi tên ↑ hoặc ↓ → lo lắng
4. Mở Google, tìm từng tên chỉ số
5. Đọc nhiều trang khác nhau, thông tin không nhất quán, nhiều trang quảng cáo bán thuốc
6. Vẫn không chắc hiểu đúng → chờ gặp bác sĩ để hỏi lại từ đầu

**Bottleneck:**
Bước 4-5 — tự tra Google từng chỉ số mất 20-30 phút, kết quả rời rạc và đôi khi gây lo lắng không cần thiết (chỉ số hơi cao mà đọc bài viết bệnh nặng).

**Impact:**
20-30 phút/lần; stress tâm lý không cần thiết; bác sĩ mất thêm 5-10 phút giải thích lại kết quả từng chỉ số thông thường thay vì đi thẳng vào điều trị.

**Success metric:**
Giảm thời gian "nhận kết quả → hiểu ý nghĩa cơ bản" từ 20-30 phút xuống dưới 3 phút; giảm tần suất bác sĩ phải giải thích lại từng chỉ số thông thường (chỉ tập trung vào chỉ số thật sự bất thường).

**Non-AI alternative:**
Vinmec đính kèm file glossary giải thích thuật ngữ. Đã có ở một số bệnh viện, nhưng không cá nhân hóa theo kết quả từng người và không highlight chỉ số nào cần chú ý nhất.

**AI hypothesis:**
AI đọc file kết quả, giải thích từng chỉ số bất thường bằng ngôn ngữ thông thường, đồng thời tạo danh sách câu hỏi nên hỏi bác sĩ. AI không được chẩn đoán bệnh, không được kết luận tình trạng sức khỏe.

**Quick gut:**
- [ ] No AI / process fix
- [ ] Rule
- [x] Workflow
- [ ] Agent
- [ ] Chưa biết

**Draft Current Workflow:**

```text
CURRENT STATE — 20-30 phút

[1 Nhận PDF kết quả: 1']
→ [2 Đọc danh sách chỉ số: 5']
→ [3 Thấy chỉ số ↑↓ → lo lắng: 1']
→ [4 Tra Google từng chỉ số: 15-20']  <-- bottleneck
→ [5 Đọc nhiều trang, kết quả không nhất quán: 5']
→ [6 Không chắc hiểu đúng → chờ gặp bác sĩ]
```

**Draft Future Workflow:**

```text
FUTURE STATE — 3-5 phút

[1 Nhận PDF kết quả: 1']
→ [2 AI đọc file + tóm tắt chỉ số bất thường bằng ngôn ngữ thông thường: 1']
→ [3 Người dùng đọc tóm tắt + danh sách câu hỏi nên hỏi bác sĩ: 2-3']  <-- human boundary
→ [4 Gặp bác sĩ với câu hỏi rõ ràng thay vì hỏi lại từng chỉ số]

Fallback: AI không đọc được file PDF → hiện link đặt lịch tư vấn với bác sĩ Vinmec
```

---

### Problem Card #2 — Lên kế hoạch đi Vinpearl

```
┌──────────────────────────────────────────────────────────┐
│ PROBLEM CARD #2                                          │
│                                                          │
│ Problem 1 câu: Người dùng lên kế hoạch đi Vinpearl      │
│ phải tra 4-5 trang riêng lẻ (phòng, vé, ăn, di          │
│ chuyển) rồi tự tổng hợp, mất 45-60 phút và hay          │
│ bỏ sót gói combo tiết kiệm hơn đặt lẻ.                  │
│                                                          │
│ Ai đang đau? Khách cá nhân / nhóm bạn                   │
│                                                          │
│ Workflow hiện tại:                                       │
│ 1. Tìm phòng → 2. Tìm vé → 3. Tra nhà hàng             │
│ → 4. Tính tổng chi phí → 5. Đặt từng thứ lẻ            │
│                                                          │
│ Bước nghẽn nhất: Gom + tính tổng thủ công (20-30')      │
│                                                          │
│ Đo thành công bằng gì?                                   │
│ Từ 45-60' → dưới 10' có plan + ước tính chi phí         │
│                                                          │
│ Quick gut: □ No AI □ Rule  ■ Workflow                    │
│            □ Agent □ Chưa biết                           │
└──────────────────────────────────────────────────────────┘
```

**Problem 1 câu:**
Người muốn đi Vinpearl phải tra giá phòng, vé VinWonders, nhà hàng và di chuyển từ 4-5 trang riêng lẻ rồi tự tổng hợp, mất 45-60 phút và hay bỏ sót gói combo rẻ hơn đặt lẻ.

**Actor:**
Người dùng cá nhân hoặc nhóm bạn muốn lên kế hoạch nghỉ dưỡng tại Vinpearl Resort hoặc tham quan VinWonders.

**Thời điểm / bối cảnh:**
Khi bắt đầu lên kế hoạch, thường 1-2 tuần trước ngày đi, cần quyết định ngân sách, loại phòng và lịch trình hoạt động.

**Current workflow:**
1. Vào vinpearl.com tìm giá phòng theo ngày, so sánh loại phòng
2. Sang vinwonders.com tìm giá vé vào cổng và các hoạt động đặc biệt
3. Google tìm nhà hàng/quán ăn quanh khu Vinpearl
4. Kiểm tra giá vé máy bay/xe khách đến địa điểm
5. Tự cộng tổng chi phí trên giấy hoặc Excel
6. Quay lại đặt từng dịch vụ trên từng trang riêng lẻ

**Bottleneck:**
Bước 1-5 — gom thông tin từ 4-5 nguồn thủ công mất 45-60 phút; các trang không hiển thị gói combo rõ ràng; giá thay đổi theo ngày dễ bị nhầm.

**Impact:**
45-60 phút/lần lập kế hoạch; hay bỏ sót gói combo tiết kiệm 15-20% so với đặt lẻ; mở nhiều tab cùng lúc dễ nhầm thông tin.

**Success metric:**
Giảm thời gian từ "bắt đầu tìm → có kế hoạch chi tiết kèm ước tính chi phí" từ 45-60 phút xuống dưới 10 phút.

**Non-AI alternative:**
Gọi hotline Vinpearl để tư vấn gói. Nhưng phải chờ, chỉ giờ hành chính, không có bản so sánh trực quan để tự quyết định.

**AI hypothesis:**
AI gom thông tin phòng, vé, ưu đãi theo ngày, ước tính di chuyển → tổng hợp thành 2-3 plan kèm ước tính chi phí. Người dùng chọn plan và confirm đặt.

**Quick gut:**
- [ ] No AI / process fix
- [ ] Rule
- [x] Workflow
- [ ] Agent
- [ ] Chưa biết

**Draft Current Workflow:**

```text
CURRENT STATE — 45-60 phút

[1 Tìm giá phòng vinpearl.com: 15']
→ [2 Tìm vé VinWonders: 10']
→ [3 Google nhà hàng + di chuyển: 15']
→ [4 Tự tính tổng chi phí thủ công: 10']  <-- bottleneck
→ [5 Quay lại đặt từng thứ lẻ trên từng trang: 10']
```

**Draft Future Workflow:**

```text
FUTURE STATE — 8-10 phút

[1 Nhập: ngày đi, điểm đến, số người, ngân sách: 2']
→ [2 AI tổng hợp gói phòng + vé + ưu đãi hiện có + ước tính di chuyển: 1']
→ [3 Người dùng xem + so sánh 2-3 lựa chọn: 5']  <-- human boundary
→ [4 Xác nhận và chuyển sang trang đặt chính thức: 2']

Fallback: Thông tin giá hết hạn hoặc hết phòng → báo rõ và chuyển đến trang đặt chính thức
```

---

### Problem Card #3 — Điểm VinID rải rác không biết dùng gì

```
┌──────────────────────────────────────────────────────────┐
│ PROBLEM CARD #3                                          │
│                                                          │
│ Problem 1 câu: Điểm VinID tích lũy từ nhiều dịch vụ    │
│ nhưng người dùng không biết tổng điểm là bao nhiêu       │
│ và nên đổi thành gì phù hợp nhất với thói quen mình.    │
│                                                          │
│ Ai đang đau? Người dùng VinID dùng nhiều dịch vụ Vin    │
│                                                          │
│ Workflow hiện tại:                                       │
│ 1. Mở app → 2. Kiểm tra điểm → 3. Browse danh          │
│ sách dài → 4. Không chắc chọn gì → bỏ qua              │
│                                                          │
│ Bước nghẽn nhất: Browse danh sách đổi điểm (8-10')      │
│                                                          │
│ Đo thành công bằng gì?                                   │
│ Tăng tần suất đổi điểm từ <1 lần/quý → ≥1 lần/tháng   │
│                                                          │
│ Quick gut: □ No AI □ Rule  ■ Workflow                    │
│            □ Agent □ Chưa biết                           │
└──────────────────────────────────────────────────────────┘
```

**Problem 1 câu:**
Điểm VinID tích lũy từ Xanh SM, WinMart, Vinmec,… nhưng người dùng không biết tổng điểm đang là bao nhiêu và có thể đổi gì có giá trị nhất — dẫn đến điểm hết hạn lãng phí.

**Actor:**
Người dùng VinID đã dùng ít nhất 2-3 dịch vụ trong hệ sinh thái Vin và tích lũy được điểm thưởng.

**Thời điểm / bối cảnh:**
Bất kỳ lúc nào muốn dùng điểm — hoặc khi nhận được thông báo "điểm sắp hết hạn" mà không biết nên đổi gì.

**Current workflow:**
1. Mở app VinID
2. Tìm mục điểm thưởng — thấy con số tổng nhưng không rõ đến từ dịch vụ nào
3. Click vào danh sách đổi điểm — dài, không được sắp xếp theo thói quen dùng dịch vụ của mình
4. Browse không biết chọn gì — nhiều ưu đãi không liên quan đến dịch vụ mình hay dùng
5. Bỏ qua hoặc chọn đại một thứ không thật sự cần

**Bottleneck:**
Bước 3-4 — danh sách đổi điểm không cá nhân hóa, không gợi ý dựa trên lịch sử dùng dịch vụ → mất 8-10 phút browse mà không ra quyết định.

**Impact:**
Điểm thưởng hết hạn lãng phí; người dùng mất cảm giác được thưởng dù dùng nhiều dịch vụ; giảm động lực tiếp tục dùng hệ sinh thái Vin.

**Success metric:**
Tăng tần suất người dùng chủ động đổi điểm từ ít hơn 1 lần/quý lên ít nhất 1 lần/tháng; giảm tỷ lệ điểm hết hạn không dùng.

**Non-AI alternative:**
Email/notification "bạn có X điểm sắp hết hạn". Đã có, nhưng không gợi ý cụ thể nên dùng vào đâu — người dùng vẫn phải tự browse.

**AI hypothesis:**
AI phân tích lịch sử dùng dịch vụ của người dùng → gợi ý top 3 cách dùng điểm phù hợp nhất với thói quen (ví dụ: hay đi Xanh SM → gợi ý đổi voucher Xanh SM). Người dùng chọn và confirm.

**Quick gut:**
- [ ] No AI / process fix
- [ ] Rule
- [x] Workflow
- [ ] Agent
- [ ] Chưa biết

**Draft Current Workflow:**

```text
CURRENT STATE — 10-15 phút (thường kết thúc mà không đổi)

[1 Mở app VinID: 1']
→ [2 Kiểm tra số điểm — không rõ breakdown: 2']
→ [3 Browse danh sách đổi điểm dài, không cá nhân hóa: 8-10']  <-- bottleneck
→ [4 Không chắc chọn gì → bỏ qua hoặc chọn đại]
```

**Draft Future Workflow:**

```text
FUTURE STATE — 2-3 phút

[1 Mở app VinID: 1']
→ [2 AI gợi ý top 3 cách dùng điểm dựa trên lịch sử dùng dịch vụ: 1']
→ [3 Người dùng chọn ưu đãi phù hợp và confirm: 1-2']  <-- human boundary

Fallback: Không có gợi ý phù hợp → hiển thị danh sách toàn bộ như hiện tại
```

---

## Card muốn pitch nhất

**Card tôi muốn pitch nhất:**

```text
Problem Card #1 — Kết quả xét nghiệm Vinmec khó hiểu
```

**Vì sao:**

```text
Workflow rõ nhất trong 3 card: có điểm bắt đầu (nhận PDF), điểm nghẽn cụ thể (tra Google),
và điểm kết thúc (hiểu đủ để gặp bác sĩ). Metric đo được (thời gian). AI intervention point
rõ: giải thích ngôn ngữ y tế, không chẩn đoán. Boundary cũng rõ: AI không được ra kết luận
về tình trạng sức khỏe.
```

**Câu hỏi tôi muốn nhóm challenge:**

```text
Ranh giới giữa "giải thích kết quả" và "chẩn đoán bệnh" thiết kế thế nào cho an toàn?
Nếu AI giải thích sai một chỉ số — ai chịu trách nhiệm và fallback là gì?
```

---

*Day 02 Lab — Nguyễn Thái Dương — 2A202600823*
