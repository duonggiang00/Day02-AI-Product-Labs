# 02 — Group Problem Statement

## Group convergence

Nhóm 3-4 người, mỗi người share top 3. Tổng cộng khoảng 9-12 candidates.

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Báo cáo / tổng hợp thông tin | Báo cáo tiến độ tuần của lead dev, báo cáo tiến độ thí nghiệm của researcher | Gom thông tin từ nhiều nguồn rồi viết lại cho người khác đọc |
| Tìm kiếm / hỏi đáp tài liệu | Tìm phòng trọ & tiện ích cho học viên, tra cứu tài liệu học tập, trích xuất tài liệu của chương trình | Tìm đúng thông tin trong nhiều nguồn rời rạc |
| Review / feedback | Review chất lượng code, chatbot admin trả lời Q&A học viên | Đọc bản nháp/dữ liệu và chỉ ra thiếu sót hoặc phản hồi |
| Lọc / xử lý dữ liệu | Lọc noise trajectory từ mô phỏng RL | Xử lý dữ liệu thô tự động trước khi đưa vào hệ thống khác |
| Planning / follow-up | Lên kế hoạch tuần và phân chia task | Phân bổ công việc dựa trên năng lực và theo dõi tiến độ |

## Shortlist và score

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| Tìm phòng trọ & tiện ích | 5 | 5 | 5 | 5 | 5 | 5 | 5 | 35 |
| Báo cáo tiến độ tuần | 4 | 5 | 4 | 4 | 4 | 4 | 4 | 29 |
| Lọc noise trajectory | 4 | 4 | 3 | 4 | 3 | 4 | 3 | 25 |

Nhóm chọn: **Tìm phòng trọ & tiện ích**.

Vì sao chọn:

- Có workflow rõ nhất.
- Có baseline thời gian rõ ràng.
- Có thể validate nhanh với các học viên khác cùng khóa ở xa.
- Có thể research các tool/pattern có sẵn như Google Maps API, RAG/NotebookLM.
- Có thể vẽ before/after rất rõ.

Vì sao không chọn các bài khác:

- Báo cáo tiến độ tuần: dù workflow rõ nhưng các thành viên trong nhóm không phải ai cũng có dữ liệu thực tế hoặc hiểu dự án để chạy thử trong buổi lab.
- Lọc noise trajectory: domain quá hẹp (Reinforcement Learning), các thành viên khác trong nhóm khó đóng góp và rất khó demo nhanh trong buổi lab.

## Quick validation

Nhóm hỏi nhanh 5 học viên cùng khóa ở tỉnh xa.

| Nguồn | Số người | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Quick interview | 5 | 5/5 học viên xác nhận mệt mỏi nhất vụ tìm trọ và không rành đường sá | 1 bạn nói có thể ở tạm ký túc xá hoặc nhờ người quen tìm giúp | Tập trung vào đối tượng tự thuê trọ ngoài và cần tìm các tiện ích xung quanh để tự lập |

Insight sau validation:

```text
Pain thật không nằm ở việc thiếu phòng trọ, tiện ích xung quanh. Pain nằm ở chỗ dữ liệu quá nhiều nguồn tìm kiếm giá cả, hình ảnh nằm trên Facebook; vị trí, đường đi nằm trên Google Maps; quy định học tập nằm trên các tài liệu của trường. Học viên tốn nhiều thời gian chỉ để tìm hiểu thông tin xung quanh."
```

## Research giải pháp

Nhóm tìm các hướng đã có sẵn, không giả định phải tự build từ đầu.

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Google Maps API | https://developers.google.com/maps | Tìm vị trí, tính khoảng cách, tìm tiện ích xung quanh | Tìm kiếm vị trí và chỉ đường cực kỳ chính xác | Dữ liệu phòng trọ cho thuê trên bản đồ rất nghèo nàn và không cập nhật giá | Dùng làm input về khoảng cách và tiện ích cho workflow |
| NotebookLM / RAG | https://notebooklm.google/ | Hỏi đáp trên tài liệu PDF của nhà trường | Tóm tắt nhanh nội quy, lịch học, hướng dẫn nhập học | Không thể truy xuất thông tin bên ngoài | AI hỗ trợ đọc hiểu tài liệu hướng dẫn tĩnh của trường |
| Facebook Groups | https://www.facebook.com/ | Nơi đăng tin cho thuê phòng trọ | Nguồn thông tin phòng trọ phong phú, cập nhật liên tục | Tin rác nhiều, thông tin không được cấu trúc hóa, không có vị trí chính xác | Cần một bước cào dữ liệu hoặc chuẩn hóa thông tin từ FB |

Research takeaway:

```text
Không nên cố xây một Agent tự động đi tìm và chốt phòng trọ vì rủi ro pháp lý và cọc tiền rất lớn. Hướng tiếp cận hợp lý là Workflow: scrape/cấu trúc dữ liệu phòng trọ từ FB, dùng Google Maps API tính khoảng cách, dùng AI để draft bảng so sánh 3 phòng trọ tối ưu kèm tiện ích để học viên tự xem và tự liên hệ.
```

## Workflow before/after

File nhóm nộp kèm:

```text
02-group-problem-statement-workflow.png/pdf/md
```

Nội dung workflow:

```text
CURRENT STATE — 5 bước, 3 ngày (tính theo thời gian chờ và thao tác)

[1 Nhận thông báo trúng tuyển]
→ [2 Đọc PDF giới thiệu trường: 30 phút]
→ [3 Tìm phòng trọ trên các group Facebook: 2 ngày] <-- bottleneck (đọc tin rác, inbox hỏi giá)
→ [4 Tra Google Maps khoảng cách & tìm quán ăn, cây xăng: 4 tiếng] <-- bottleneck (check chéo)
→ [5 Đi khảo sát thực tế và chốt: 1 ngày]

FUTURE STATE — 5 bước, 15 phút

[1 Nhận thông báo kèm link Bot: 1 phút]
→ [2 Học viên nhập budget & nhu cầu tiện ích: 1 phút]
→ [3 Bot tự động so khớp database trọ & Map API: 2 phút] -- Rule/API
→ [4 AI draft bảng so sánh 3 phương án tốt nhất: 1 phút] -- AI Workflow step
→ [5 Học viên review & tự liên hệ chủ nhà: 10 phút] -- Human boundary

Fallback:
AI đề xuất sai thông tin hoặc nhà đã hết phòng → Học viên bỏ qua và tự tra cứu thủ công hoặc yêu cầu Bot đề xuất lại.

Bottleneck mới:
Học viên liên hệ và đi xem phòng thực tế. Đây là chốt chặn an toàn bắt buộc để tránh bị lừa đảo cọc tiền.
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Tổng thời gian | 3 ngày | Dưới 15 phút | Target chính |
| Số bước | 5 | 5 | Giảm đáng kể công sức copy-paste thủ công |
| Bước thủ công | 5/5 | 2/5 | AI và script làm hộ phần tổng hợp dữ liệu |
| Bottleneck chính | Tìm trọ trên FB & check Map | Tự liên hệ chủ nhà | Điểm kiểm soát an toàn của con người |
| Risk mới | Không có | Lỗi thông tin ảo, trọ ảo | Cần con người tự xác nhận lại |

## Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Tân học viên khóa học chuẩn bị nhập học từ tỉnh xa. |
| **Workflow** | Nhận thông báo → Đọc PDF trường → Tìm phòng trọ trên FB → Tra Google Maps khoảng cách → Đi xem thực tế. |
| **Bottleneck** | Bước đối chiếu thủ công thông tin phòng trọ (trên FB) với khoảng cách và tiện ích xung quanh (trên Google Maps) mất quá nhiều thời gian. |
| **Impact** | Học viên mất 3 ngày mệt mỏi, stress trước khi nhập học; nhà trường có rủi ro bị rơi rụng học viên do rào cản đi lại và chỗ ở. |
| **Success Metric** | Giảm thời gian tìm ra danh sách 3 phòng trọ phù hợp từ 3 ngày xuống dưới 15 phút. |
| **Boundary** | AI không tự bịa ra thông tin nhà trọ; không tự động cọc tiền hay nhắn tin chốt nhà thay cho học viên. |

## Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Bản đồ tĩnh chứa danh sách nhà trọ cố định do trường cung cấp | Đủ nếu số lượng học viên ít và danh sách nhà trọ không thay đổi | Danh sách nhanh chóng bị lỗi thời, không cá nhân hóa được theo budget | Không chọn làm toàn bộ, chỉ dùng làm cơ sở dữ liệu tĩnh |
| **Workflow** | Scraper gom data trọ → Map API tính khoảng cách → AI tổng hợp & draft bảng so sánh dựa trên nhu cầu riêng → Học viên review | Hợp lý vì quy trình rõ ràng, tuyến tính. AI đóng vai trò ngôn ngữ để tổng hợp thông tin đa nguồn | Dữ liệu đầu vào sai lệch hoặc nhà trọ đã được cho thuê | Chọn |
| **Agent** | Agent tự chat với các chủ nhà trên Facebook để hỏi phòng trống, tự thương lượng giá và đặt cọc | Cần thiết nếu quy trình thương lượng phức tạp và tự động hóa hoàn toàn | Rủi ro lừa đảo, mất tiền cọc, vi phạm điều khoản Facebook | Không chọn |

Mức chọn:

```text
Workflow.
```

Vì sao:

- Gom dữ liệu và tính khoảng cách có thể thực hiện bằng rule/script và API.
- Việc tổng hợp nhu cầu tự nhiên của học viên và viết bản so sánh (narrative) cần khả năng ngôn ngữ của AI.
- Học viên là người trực tiếp review và liên hệ chủ nhà nên kiểm soát được rủi ro.
- Chưa cần Agent tự động đàm phán vì độ phức tạp và rủi ro pháp lý quá lớn.

## Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Tân học viên khóa học chuẩn bị nhập học từ tỉnh xa. |
| **Workflow** | Nhận thông báo → Nhập nhu cầu lên Bot → AI Workflow xử lý data → Học viên review bảng đề xuất → Tự liên hệ chủ nhà. |
| **Bottleneck** | Bước đối chiếu thông tin phòng trọ và khoảng cách địa lý mất quá nhiều thời gian và gây stress. |
| **Impact** | Tốn 3 ngày chuẩn bị; gây nản lòng cho học viên ở xa; ảnh hưởng đến tỷ lệ nhập học thực tế. |
| **Success Metric** | Giảm thời gian tìm ra 3 phòng trọ tối ưu xuống dưới 15 phút; giảm 70% câu hỏi lặp đi lặp lại gửi cho Admin trường. |
| **Boundary** | AI không tự bịa thông tin phòng trọ; không tự động cọc tiền; học viên phải tự liên hệ xác nhận. |
| **AI intervention point** | Sau khi Bot nhận nhu cầu học viên và lấy dữ liệu thô (database + Map API), AI sẽ nhảy vào để draft bảng so sánh và đánh giá tiện ích. |
| **Mức chọn** | Workflow: Script kéo data + API tính khoảng cách → AI draft đề xuất → Học viên review. |
| **Rủi ro & người thật kiểm tra** | Risk: Thông tin nhà trọ ảo hoặc đã hết chỗ, AI gợi ý quán ăn đã đóng cửa. Người thật review: Học viên bắt buộc phải tự gọi điện check và đến xem phòng trực tiếp trước khi cọc. |

## Final decision

Decision:

```text
Go với scope nhỏ.
```

Pilot nhỏ nhất:

- Dùng dữ liệu mẫu tự thu thập từ 10 phòng trọ xung quanh trường trong bán kính 2km.
- Chạy workflow bán thủ công: Học viên điền nhu cầu vào form, script chạy API tính khoảng cách, AI draft bảng đề xuất bằng prompt chuẩn.
- Đo lường thời gian từ lúc điền nhu cầu đến khi có bảng đề xuất và tỷ lệ hài lòng của học viên.

Exit / rollback:

- Nếu AI bịa đặt thông tin (khoảng cách sai lệch > 500m so với Google Maps thực tế) hoặc đề xuất toàn phòng đã cho thuê, dừng sử dụng AI và quay về cung cấp danh sách Excel tĩnh.
- Nếu học viên vẫn phải tự lên Facebook tìm kiếm lại từ đầu, hạ mức xuống dùng bản đồ tĩnh tích hợp link Google Maps.

Decision rationale:

- Bài toán cụ thể, nỗi đau rất lớn và có thật đối với các học viên ở xa.
- Công nghệ RAG + Google Maps API đã rất chín muồi, dễ triển khai nhanh trong buổi lab.
- Giới hạn an toàn (Boundary) rõ ràng: Học viên tự liên hệ và chịu trách nhiệm tiền cọc.

---

