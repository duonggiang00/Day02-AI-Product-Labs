# 01 — Individual Problem Scan

## Scan rộng

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | Viết báo cáo hàng tuần và họp với team | Lead dev | Mất khoảng 90 phút/tuần |
| 2 | Tốn thời gian | Lên kế hoạch tuần và phân công công việc cho member trong team | Lead dev | 45 phút/bản |
| 3 | Tốn thời gian | Review chất lượng code từ team member | Reviewer, Lead dev | 90/tuần |
| 4 | Pain từ người khác | team member không hiểu task cần giải thích chi tiết từ lead | lead, team member | 30 phút/buổi |
| 5 | AI có thể tốt hơn | tóm tắt công việc mà team member đã làm | PM, team member | 60 phút mỗi lần viết lại báo cáo công việc cá nhân |

## Chọn top 3

Tiêu chí chọn:

- Actor rõ.
- Workflow hiện tại có thể vẽ được.
- Bottleneck cụ thể.
- Impact có thể đo hoặc ước lượng.
- Có thể so sánh No AI / Rule / Workflow / Agent.
- Không quá rộng cho một buổi lab.

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Viết báo cáo hàng tuần và họp với team | Actor rõ, workflow rõ ràng: thu thập data -> tổng hợp -> Format | Văn phong báo cáo của AI có thể bị lan man hoặc quá súc tích khó hiểu |
| 2 | Lên kế hoạch tuần và phân công công việc | thể hiện khả năng suy luận của agent từ mô tả task công việc | Agent có thể không nắm rõ skill của member trong team |
| 3 | Review chất lượng code | Actor rõ, workflow chuẩn: Pull request->Review code->Approve code->Merge | Agent có thể chỉ bắt lỗi syntax, yêu cầu clean code, có thể chưa nắm rõ nghiệp vụ của doanh nghiệp |

## Problem Card Weekly Report

```text
Problem 1 câu: 
Việc tổng hợp dữ liệu từ nhiều nguồn để viết báo cáo tiến độ hàng tuần tốn quá nhiều thời gian thủ công và dễ bị dàn trải, thiếu điểm nhấn.

Actor: 
Lead dev

Thời điểm / bối cảnh: 
Chiều thứ 6 hàng tuần (hoặc trước buổi họp giao ban), khi cần gom thông tin cập nhật công việc, tiến độ, và các blocker của toàn bộ thành viên trong team.

Current workflow 3-7 bước:
1. Truy cập vào các công cụ quản lý (như Jira/Trello, GitHub/GitLab).
2. Lọc và đọc lướt trạng thái các task, commit, hoặc ghi chú của từng team member trong tuần.
3. Gom nhặt các đầu việc đã hoàn thành, các task đang bị trễ hoặc block.
4. Đánh giá thủ công xem đâu là task quan trọng (ví dụ: hotfix) để đưa lên đầu.
5. Soạn thảo, viết lại thành văn bản chỉn chu theo template của công ty và gửi báo cáo.

Bottleneck: 
Bước 2 và Bước 4. Việc đọc hiểu dữ liệu thô lộn xộn từ member và tự đánh giá độ ưu tiên tốn rất nhiều công sức nội suy của não bộ.

Impact: 
Mất khoảng 90 phút/tuần của Lead dev - khoảng thời gian quý giá có thể dùng để review kiến trúc code hoặc giải quyết technical issue.

Success metric: 
- Thời gian làm báo cáo giảm từ 90 phút xuống dưới 15 phút.
- Báo cáo highlight chính xác các blocker hoặc task quan trọng mà không bị sót.

Non-AI alternative: 
Ép quy trình (Process fix): Tạo Google Sheet và bắt buộc từng team member phải tự điền tiến độ tóm tắt của mình trước 4h chiều thứ 6. 
Rule: Viết script tự động export danh sách các task "Done" từ hệ thống ra một file text thô.

AI hypothesis: 
Một AI Agent (hoặc LLM trong một Workflow) có thể nhận dữ liệu thô (raw data) của tuần, tự động suy luận để phân loại task nào là quan trọng (hotfix, critical feature), loại bỏ các thông tin rác, và viết ra một bản báo cáo súc tích đúng template chuẩn.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết
```
## Problem Card Planning and Task Assigning
Problem 2 câu:
Lên kế hoạch tuần và phân chia task tốn nhiều công sức suy luận, đồng thời AI Agent có thể phân sai việc do không nắm rõ skill thực tế của từng member.

Actor:
Lead dev

Thời điểm / bối cảnh:
Đầu tuần (Thứ 2) hoặc cuối tuần trước khi bắt đầu một Sprint mới (Weekly/Sprint Planning).

Current workflow 3-7 bước:
1 Đọc danh sách backlog, các task thô hoặc ý tưởng tính năng cần làm trong tuần.
2 Đánh giá độ phức tạp, ước lượng thời gian (Est) cho từng task.
3 Kiểm tra capacity (khối lượng việc hiện tại) và skill matrix của từng member.
4 Suy luận và khớp việc (Assign) đúng người, đúng thế mạnh.
5 Viết mô tả chi tiết (Task Description/Acceptance Criteria) cho từng việc để member hiểu.

Bottleneck:
Bước suy luận khớp việc và viết mô tả chi tiết rõ ràng cho từng task (mất 45 phút/bản).

Impact:
Mất 45 phút/bản kế hoạch.

Success metric:
Thời gian lên plan và giao việc giảm xuống dưới 10 phút; Task giao đúng người, mô tả rõ ràng không cần giải thích lại.

Non-AI alternative:
Dùng một bảng Skill Matrix cố định trên Excel, chia việc theo rule cứng (Member A chỉ làm Frontend, Member B chỉ làm Backend) và lead tự viết mô tả thủ công.

AI hypothesis:
Xây dựng một AI Agent có khả năng suy luận (Reasoning). Ta sẽ nạp cho Agent một file Context chứa "Profile & Skill Matrix thực tế" của team (bao gồm cả ghi chú về performance). Agent sẽ đọc danh sách task thô, tự động phân tích và đưa ra đề xuất assign kèm lý do, sau đó tự động gen luôn mô tả chi tiết cho task đó.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết

## Problem Card Code Reviewing

Problem 3 câu:
Review code thủ công cực kỳ tốn thời gian và dễ sót lỗi, tuy nhiên AI Agent có rủi ro chỉ bắt được lỗi cú pháp (syntax) mà không hiểu được logic nghiệp vụ của dự án.

Actor:
Lead dev, Reviewer

Thời điểm / bối cảnh:
Bất kỳ lúc nào trong tuần khi một team member hoàn thành task và tạo Pull Request (PR) trên GitHub/GitLab.

Current workflow 3-7 bước:
1 Team member hoàn thành code và tạo Pull Request.
2 Lead dev/Reviewer nhận thông báo, mở PR và đọc các dòng code thay đổi (Code Diff).
3 Đối chiếu code với yêu cầu tính năng ban đầu (nghiệp vụ) xem dev viết có đúng logic không.
4 Kiểm tra xem code có vi phạm các lỗi cú pháp, clean code, bảo mật hay convention không.
5 Gõ comment nhận xét và bấm Approve hoặc Require Changes.

Bottleneck:
Bước đọc hiểu đống code diff và suy luận xem logic code có đang chạy đúng với nghiệp vụ (business logic) của bài toán hay không.

Impact:
Mất khoảng 90 phút/tuần của cả lead và reviewer.

Success metric:
Thời gian review giảm từ 90 phút xuống dưới 30 phút; Phát hiện sớm các lỗi convention và ít nhất 50% lỗi logic nghiệp vụ trước khi lead sờ vào.

Non-AI alternative:
Sử dụng các công cụ CI/CD chạy Rule tĩnh như SonarQube, ESLint, PHPStan để tự động bắt lỗi cú pháp, format và convention.

AI hypothesis:
Cấu hình một AI Agent tích hợp thẳng vào hệ thống CI/CD qua Webhook. Để giải quyết việc "thiếu hiểu biết nghiệp vụ", khi PR được tạo, Agent sẽ tự động fetch file "Mô tả task/User Story" liên quan từ Jira làm Context. Agent sẽ đối chiếu trực tiếp Code Diff với tài liệu nghiệp vụ đó để tìm ra các lỗ hổng về mặt logic chứ không chỉ bắt lỗi syntax.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[ ] Workflow
[x] Agent
[ ] Chưa biết