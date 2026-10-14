# KẾ HOẠCH SPRINT CHO HỆ THỐNG ĐẶT LỊCH SẠC XE MÁY ĐIỆN

## (1) Nhiệm vụ 1: Phân tích Velocity và Capacity

### Velocity tham khảo
*   **Cách tính:** (15 SP + 16 SP + 17 SP) / 3 Sprint = 16 SP
*   **Ghi chú:** Velocity là giá trị trung bình từ các Sprint trước, dùng để dự báo lượng công việc nhóm có thể hoàn thành trong Sprint này, không phải là cam kết tuyệt đối.

### Bảng Capacity Sprint này

| Developers | Ngày Sprint | Ngày không tham gia | Ngày khả dụng | Giờ tập trung/ngày | Capacity (giờ) |
| :--------- | :---------- | :------------------ | :------------ | :----------------- | :------------- |
| Dev A      | 10          | 0                   | 10            | 5                  | 50             |
| Dev B      | 10          | 0                   | 10            | 5                  | 50             |
| Dev C      | 10          | 2                   | 8             | 5                  | 40             |
| Dev D      | 10          | 0                   | 10            | 5                  | 50             |
| **Tổng**   |             |                     |               |                    | **190 giờ**    |

### Nhận xét
Capacity Sprint này là 190 giờ, thấp hơn mức 200 giờ tiêu chuẩn (giảm 10 giờ) do Dev C nghỉ 2 ngày. Dùng Velocity tham khảo (16 SP) và Capacity (190 giờ) để dự báo: nhóm có thể đặt mục tiêu hoàn thành khoảng 11-16 SP trong Sprint này, với tổng thời gian làm việc là 190 giờ. Điều này giúp nhóm chọn PBI phù hợp với khả năng thực tế, tránh quá tải hoặc đặt ra mục tiêu không khả thi.

## (2) Nhiệm vụ 2: Viết lại Sprint Goal

**Sprint Goal đã chỉnh sửa:**
Người dùng có thể dễ dàng tìm kiếm trạm sạc xe máy điện phù hợp, xem được các khung giờ trống và đặt chỗ trước thành công, giúp họ chủ động hơn trong việc sạc xe và tránh phải chờ đợi.

## (3) Nhiệm vụ 3: Lập Sprint Backlog

### Lựa chọn PBI

| Mã Story | Ưu tiên | SP | Chọn/Chưa chọn | Lý do                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| :------- | :------ | :- | :------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| CS01     | 1       | 3  | ☑ Chọn         | Ưu tiên 1; bước đầu để người dùng tìm trạm, hiển thị thông tin cần thiết.                                                                                                                                                                                                                                                                                                                                |
| CS02     | 2       | 3  | ☑ Chọn         | Ưu tiên 2; cần biết giờ còn trống trước khi đặt, là bước tiếp theo của CS01.                                                                                                                                                                                                                                                                                                                            |
| CS03     | 3       | 5  | ☑ Chọn         | Đây là chức năng cốt lõi mà Product Owner mong muốn đạt được trong Sprint này, mang lại giá trị trực tiếp cho người dùng (không phải chờ). Phù hợp với Sprint Goal tập trung vào việc đặt chỗ trước.                                                                                                                                                                                                                   |
| CS04     | 4       | 5  | ☐ Chưa chọn    | - **Sprint Goal:** Sprint Goal tập trung vào "tìm kiếm, xem giờ trống và đặt chỗ trước thành công", chức năng hủy chưa phải trọng tâm chính. <br>- **Độ rõ của Acceptance Criteria:** Có một quy tắc "chưa chốt: hủy sát giờ sạc có bị hạn chế hay không", khiến PBI chưa sẵn sàng (Definition of Ready chưa đạt) và tiềm ẩn rủi ro về phạm vi, thời gian. <br>- **Velocity & Capacity:** Với Velocity khoảng 16 SP và Capacity 190 giờ, nhóm có thể hoàn thành nhiều hơn 11 SP, nhưng rủi ro của CS04 về độ rõ là quá cao, có thể ảnh hưởng đến chất lượng chung của Sprint. |

**Tổng SP đã chọn:** 11 SP (Mức dự báo, không phải cam kết)

### Task Breakdown cho CS03 (Đặt trước một vị trí sạc)

| STT | Task                                             | Đầu ra                                                                                                                                                           | Ước lượng (giờ) |
| :-- | :----------------------------------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------- | :-------------- |
| 1   | Phát triển giao diện người dùng cho chức năng đặt lịch | Giao diện đặt lịch cho phép người dùng chọn trạm, ngày, giờ và xe cần sạc; hiển thị thông báo lỗi khi không đủ thông tin hoặc giờ đã kín.                | 20              |
| 2   | Triển khai logic xử lý đặt lịch và quản lý vị trí sạc | API/logic xử lý yêu cầu đặt lịch, kiểm tra trùng lịch, cập nhật trạng thái vị trí sạc, và tạo mã xác nhận cho lịch đặt thành công.                   | 25              |

## (4) Nhiệm vụ 4: Phân tích Burndown Chart

1.  **So sánh đường thực tế với đường lý tưởng, chỉ ra dấu hiệu bất thường và rủi ro cho Sprint Goal.**
    *   **Đầu Sprint (Ngày 0-2):** Đường thực tế (11 SP) trùng với đường lý tưởng. Điều này cho thấy chưa có PBI nào được hoàn thành (Done) trong những ngày đầu, không có Story Point nào được trừ. 
    *   **Giữa Sprint (Ngày 3-7):** Ngày 3, đường thực tế giảm từ 11 SP xuống 8 SP, trong khi đường lý tưởng giảm dần đều. Tuy nhiên, từ Ngày 4 đến hết Ngày 7, đường thực tế giữ nguyên ở mức 8 SP. Đây là một dấu hiệu bất thường rõ rệt, cho thấy không có PBI nào được đánh dấu "Done" trong suốt 4 ngày liên tiếp. 
    *   **Cuối Sprint (Ngày 8-10):** Ngày 8, đường thực tế giảm từ 8 SP xuống 5 SP, rồi lại giữ nguyên ở 5 SP vào Ngày 9. Đến Ngày 10 (ngày cuối Sprint), tất cả 5 SP còn lại đều được trừ, đưa đường thực tế về 0. Điều này cho thấy các PBI chỉ được hoàn thành (Done) và trừ SP vào những ngày cuối Sprint, đặc biệt là vào ngày cuối cùng.
    *   **Rủi ro cho Sprint Goal:** Việc không có PBI nào được "Done" trong phần lớn Sprint và dồn lại vào cuối Sprint cho thấy nhóm có thể đang gặp khó khăn trong việc hoàn thành công việc một cách liên tục, các PBI có thể bị chặn hoặc không đạt Definition of Done sớm. Điều này tiềm ẩn rủi ro lớn về chất lượng sản phẩm (do ít thời gian kiểm thử, tích hợp) và có thể ảnh hưởng nghiêm trọng đến khả năng đạt được Sprint Goal đã đề ra, vì các giá trị cốt lõi của Sprint Goal (tìm trạm, xem giờ trống, đặt chỗ) có thể không hoàn thành đúng hạn hoặc không đạt chất lượng mong muốn.

2.  **Đề xuất 1 hành động giúp đạt Sprint Goal tại Daily Scrum ngày 7.**
    Tại Daily Scrum ngày 7, nhóm vẫn còn 8 SP chưa hoàn thành (đường thực tế ở mức 8 SP), trong khi đường lý tưởng đã ở mức 3.3 SP, cho thấy nhóm đang chậm tiến độ đáng kể. 
    Hành động đề xuất: "Nhóm cần tập trung nguồn lực vào PBI 3SP còn lại (giả định là CS02) để đưa nó về trạng thái 'Done' ngay lập tức. Các thành viên có thể cùng nhau rà soát lại các task còn dang dở của PBI này, xác định và tháo gỡ mọi rào cản, hoặc hỗ trợ lẫn nhau để hoàn thành nhanh chóng, mục tiêu là giảm lượng SP tồn đọng từ 8 SP xuống 5 SP trong ngày hôm nay hoặc ngày mai để bắt kịp tiến độ và giảm rủi ro trượt Sprint Goal." 