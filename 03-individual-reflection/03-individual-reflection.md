# 03 — Individual Reflection Example

## Đóng góp của Giang trong nhóm

| Hoạt động | Giang đã làm gì? | Kết quả |
|---|---|---|
| Đề xuất ý tưởng | Đưa ra trải nghiệm thực tế của bản thân về việc báo cáo công việc và họp nhóm hàng tuần | Nhóm có một bài toán thực tế, có nỗi đau rõ ràng để đưa vào shortlist |
| Phản biện | Đặt câu hỏi về rủi ro khi cho AI tự nhắn tin thương lượng giá với chủ nhà | Nhóm loại bỏ ý tưởng tự động hóa quá đà, giới hạn scope lại ở mức an toàn |
| Nghiên cứu giải pháp | Tìm hiểu cách tích hợp Google Maps API và kỹ thuật RAG đọc tài liệu trường | Nhóm xác định giải pháp khả thi bằng cách kết hợp API và RAG, không cần build agent lớn |

## Bảng dùng AI trong reflection

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì |
|---|---|---|---|---|
| Vẽ workflow | Nhờ AI cấu trúc và căn chỉnh sơ đồ ASCII Trước/Sau | Định dạng sơ đồ ASCII nhanh chóng, dễ nhìn | AI tự ý gộp bước tìm trọ trên FB và xem thực tế làm một | Bắt AI tách riêng vì xem thực tế là bước kiểm chứng bắt buộc |
| Nghiên cứu giải pháp | Hỏi cách tích hợp bản đồ và cách thu thập dữ liệu phòng trọ | Gợi ý sử dụng Google Maps API rất chính xác | Khuyên nên làm AI Agent tự động đi chat đàm phán với chủ nhà trọ trên FB | Xóa bỏ gợi ý này vì rủi ro lừa đảo cọc tiền quá cao và vi phạm chính sách của FB |


## Bài học của Giang

- Việc vẽ workflow chi tiết giúp ta nhận ra chỗ nào rule đủ dùng, chỗ nào mới thật sự cần AI hỗ trợ.
- Agent tự trị không phải đích đến mặc định. Trong bài toán này, Workflow hợp lý hơn rất nhiều vì nó có đường đi cố định và giữ được chốt chặn con người.
- Nghiên cứu giải pháp là để tìm ra pattern thiết kế phù hợp: để AI làm nháp (draft), con người duyệt (review).

