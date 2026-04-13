## 1. Token

**Nếu bạn hiểu về token, bạn sẽ viết lời nhắc tốt hơn**

Điều quan trọng nhất cần hiểu là các mô hình AI không đọc văn bản theo cách con người đọc. Chúng không đọc câu hay thậm chí là từ. Chúng đọc token.

Token là một đoạn văn bản nhỏ. Đôi khi nó là một từ hoàn chỉnh, đôi khi là một phần của từ, đôi khi là dấu chấm câu.

Ví dụ, câu: “Tôi yêu pizza” có thể được chia thành các token như: “Tôi” | “yêu” | “pizza”

Tại sao điều này lại quan trọng? Bởi vì các hệ thống AI đo lường mọi thứ bằng token. Giá cả, giới hạn, bộ nhớ và hiệu suất đều dựa trên token. Khi bạn gửi một lời nhắc dài, bạn đang gửi nhiều token hơn. Khi AI viết một câu trả lời dài, nó tạo ra nhiều token hơn.

**Token về cơ bản là đơn vị ngôn ngữ nhỏ nhất mà AI hiểu được.**

## 2. Context Window
*Context Window:* Cửa sổ ngữ cảnh

**Nếu bạn hiểu về cửa sổ ngữ cảnh, bạn sẽ biết tại sao AI lại quên mọi thứ**

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

**Nếu bạn hiểu về Temperature, bạn sẽ kiểm soát được sự sáng tạo so với độ chính xác**

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

**Nếu bạn hiểu về ảo giác Hallucination, bạn sẽ xác minh được thông tin quan trọng**

Ảo giác AI (Hallucination) là hiện tượng AI đưa ra thông tin sai lệch một cách tự tin.

Điều quan trọng cần hiểu là tại sao điều này xảy ra. Mô hình AI không phải là cơ sở dữ liệu. Chúng không tra cứu sự thật. Chúng dự đoán từ tiếp theo có khả năng xảy ra nhất dựa trên các mẫu mà chúng đã học được trong quá trình huấn luyện.

Vì vậy, khi mô hình thực sự **không biết điều gì đó**, nó vẫn có thể đưa ra câu trả lời **nghe có vẻ đúng** nhưng hoàn toàn sai.

Đây là lý do tại sao không nên tin tưởng AI một cách mù quáng trong:
- Tư vấn y tế
- Tư ​​vấn pháp lý
- Thống kê
- Nghiên cứu sự thật

Cách tốt nhất để sử dụng AI là như một điểm khởi đầu, chứ không phải là thẩm quyền cuối cùng.


## 5. RAG 

**(Retrieval-Augmented Generation - Tạo câu trả lời dựa trên truy xuất)**

**Nếu bạn hiểu về RAG, bạn sẽ hiểu cách các công cụ AI thực sự sử dụng dữ liệu của bạn**

RAG là công nghệ đứng sau các công cụ như:
- Trò chuyện với tệp PDF của bạn
- Bot hỗ trợ khách hàng bằng AI
- Công cụ AI trả lời câu hỏi từ tài liệu công ty

Cách hoạt động đơn giản như sau:
1. Tài liệu được chia thành các phần nhỏ
2. Các phần này được lưu trữ trong một cơ sở dữ liệu đặc biệt
3. Khi bạn đặt câu hỏi, hệ thống sẽ tìm các phần liên quan nhất
4. Các phần đó được gửi đến AI
5. AI sẽ tạo ra câu trả lời dựa trên thông tin đó

Vì vậy, AI thực chất không “học” tài liệu của bạn. Nó đang truy xuất thông tin liên quan và sau đó tạo ra câu trả lời từ đó.

Đây là cách hầu hết các công cụ kinh doanh AI hiện đại hoạt động ngày nay.
