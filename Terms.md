## 1. Token
Điều quan trọng nhất cần hiểu là các mô hình AI không đọc văn bản theo cách con người đọc. Chúng không đọc câu hay thậm chí là từ. Chúng đọc token.

Token là một đoạn văn bản nhỏ. Đôi khi nó là một từ hoàn chỉnh, đôi khi là một phần của từ, đôi khi là dấu chấm câu.

Ví dụ, câu: “Tôi yêu pizza” có thể được chia thành các token như: “Tôi” | “yêu” | “pizza”

Tại sao điều này lại quan trọng? Bởi vì các hệ thống AI đo lường mọi thứ bằng token. Giá cả, giới hạn, bộ nhớ và hiệu suất đều dựa trên token. Khi bạn gửi một lời nhắc dài, bạn đang gửi nhiều token hơn. Khi AI viết một câu trả lời dài, nó tạo ra nhiều token hơn.

**Token về cơ bản là đơn vị ngôn ngữ nhỏ nhất mà AI hiểu được.**

## 2. Context Window
*Context Window:* Cửa sổ ngữ cảnh

Context Window là **lượng** thông tin mà một mô hình AI **có thể ghi nhớ** tại một thời điểm.

Bạn có thể hình dung nó giống như một bảng trắng. Mọi thứ bạn viết trên bảng trắng đều hiển thị cho AI. Nhưng khi bảng trắng đầy, một số thứ phải được xóa đi để tạo không gian cho thông tin mới.

Cửa sổ ngữ cảnh bao gồm:
- Lời nhắc của bạn
- Các tin nhắn trước đó
- Các tài liệu bạn tải lên
- Các phản hồi của AI

Các mô hình AI cũ có cửa sổ ngữ cảnh rất nhỏ. Các mô hình mới hơn có thể xử lý lượng văn bản cực lớn, thậm chí cả toàn bộ cuốn sách.

Đây cũng là lý do tại sao AI đôi khi quên những phần đầu của các cuộc hội thoại dài. Nó không bị lỗi. Chỉ là bảng trắng đã hết chỗ mà thôi.

## 3. Temperature

*Temperature: Nhiệt độ*

Temperature kiểm soát **mức độ sáng tạo** hoặc khả năng dự đoán của phản hồi từ AI.
- **Nhiệt độ thấp (Low temperature)** --> Dễ dự đoán hơn, chính xác hơn, nhất quán hơn
- **Nhiệt độ cao (High temperature)** --> Sáng tạo hơn, bất ngờ hơn, khó dự đoán hơn

Nếu bạn sử dụng AI cho:
- Lập trình
- Tóm tắt
- Trích xuất dữ liệu
- Viết tài liệu kỹ thuật

--> Bạn cần **Low temperature**.

Nếu bạn sử dụng AI cho:
- Viết truyện
- Động não
- Ý tưởng tiếp thị
- Nội dung sáng tạo

--> Bạn cần **High temperature**.

Chỉ một thiết lập này thôi cũng có thể thay đổi hoàn toàn cách hoạt động của AI.

## 4. Hallucination

_Hallucination: Ảo giác_
Ảo giác AI (Hallucination) là hiện tượng AI đưa ra thông tin sai lệch một cách tự tin.

Điều quan trọng cần hiểu là tại sao điều này xảy ra. Mô hình AI không phải là cơ sở dữ liệu. Chúng không tra cứu sự thật. Chúng dự đoán từ tiếp theo có khả năng xảy ra nhất dựa trên các mẫu mà chúng đã học được trong quá trình huấn luyện.

Vì vậy, khi mô hình thực sự **không biết điều gì đó**, nó vẫn có thể đưa ra câu trả lời **nghe có vẻ đúng** nhưng hoàn toàn sai.

Đây là lý do tại sao không nên tin tưởng AI một cách mù quáng trong:
- Tư vấn y tế
- Tư ​​vấn pháp lý
- Thống kê
- Nghiên cứu sự thật

Cách tốt nhất để sử dụng AI là như một điểm khởi đầu, chứ không phải là thẩm quyền cuối cùng.
