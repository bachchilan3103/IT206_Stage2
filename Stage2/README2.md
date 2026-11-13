# BÀI TẬP: PHÂN BIỆT ZERO-SHOT, ONE-SHOT VÀ FEW-SHOT PROMPTING

## PHẦN 1. PHÂN TÍCH VẤN ĐỀ

### 1. Nguyên tắc phân loại

- **Zero-shot:** Prompt không cung cấp ví dụ mẫu, AI tự thực hiện theo yêu cầu.
- **One-shot:** Prompt cung cấp đúng 1 ví dụ mẫu để AI làm theo.
- **Few-shot:** Prompt cung cấp từ 3 đến 5 ví dụ mẫu để AI nhận biết cách thực hiện.

### 2. Xác định các dòng phân loại sai

- **Dòng 1:** Đang xếp Few-shot nhưng thực tế là Zero-shot vì câu lệnh không có ví dụ mẫu.
- **Dòng 2:** Đang xếp One-shot nhưng thực tế là Zero-shot vì chỉ đưa ra yêu cầu, không có ví dụ minh họa.
- **Dòng 3:** Phân loại One-shot là đúng vì có 1 ví dụ mẫu: RAM 8GB → Đa nhiệm mượt mà mở 20 tab.
- **Dòng 4:** Đang xếp Zero-shot nhưng thực tế là Few-shot vì có 3 ví dụ mẫu.
- **Dòng 5:** Đang xếp Few-shot nhưng thực tế là Zero-shot vì không cung cấp ví dụ mẫu.
- **Dòng 6:** Phân loại One-shot là đúng vì có 1 ví dụ mẫu: Err_404 → Không tìm thấy trang.

## PHẦN 2. HOÀN THIỆN BẢNG PHÂN LOẠI

| STT | Nội dung câu lệnh (Prompt) | Phân loại hiện tại | Phân loại đúng | Số lượng ví dụ mẫu |
|---|---|---|---|---|
| 1 | Phân loại đánh giá: 'Pin dùng được nửa ngày là hết'. | Few-shot | Zero-shot | 0 |
| 2 | Viết hoa tiêu đề theo phong cách công nghệ. | One-shot | Zero-shot | 0 |
| 3 | Đổi thông số RAM 16GB theo mẫu RAM 8GB → Đa nhiệm mượt mà mở 20 tab. | One-shot | One-shot | 1 |
| 4 | Phân loại cảm xúc với 3 mẫu: Hàng tốt → Pos; Giao trễ → Neg; Bình thường → Neu. | Zero-shot | Few-shot | 3 |
| 5 | Viết lại email thông báo bảo hành xong cho khách theo giọng điệu lịch sự. | Few-shot | Zero-shot | 0 |
| 6 | Dịch mã lỗi theo mẫu Err_404 → Không tìm thấy trang. | One-shot | One-shot | 1 |

## PHẦN 3. KẾT LUẬN

Sau khi rà soát 6 câu lệnh, có 4 dòng bị phân loại sai (dòng 1, 2, 4, 5) và 2 dòng phân loại đúng (dòng 3, 6).

Việc phân loại cần dựa vào số lượng ví dụ mẫu thực tế trong Prompt, không dựa vào độ dài hay độ phức tạp của câu lệnh.

- 0 ví dụ: Zero-shot.
- 1 ví dụ: One-shot.
- 3–5 ví dụ: Few-shot.