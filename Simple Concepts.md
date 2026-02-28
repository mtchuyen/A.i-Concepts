
# 20 Khái Niệm AI Được Giải Thích Đơn Giản

---

## I. Nền tảng (Foundations)

### 1. Neural Network (Mạng nơ-ron)
Là mô hình gồm nhiều lớp “nơ-ron” kết nối với nhau.  
- Dữ liệu đi vào lớp đầu vào  
- Được xử lý qua nhiều lớp ẩn  
- Trả kết quả ở lớp đầu ra  

Mỗi kết nối có một **trọng số (weight)**. Việc huấn luyện thực chất là điều chỉnh các trọng số này để dự đoán chính xác hơn.

---

### 2. Transfer Learning (Học chuyển giao)
Thay vì huấn luyện từ đầu, ta lấy một mô hình đã học rất nhiều dữ liệu trước đó rồi tinh chỉnh cho bài toán mới.

Giống như:
> Bạn đã biết toán cơ bản → học vật lý sẽ nhanh hơn.

Giúp tiết kiệm:
- Thời gian
- Dữ liệu
- Chi phí tính toán

---

## II. Cấu trúc Transformer

### 3. Tokenization
Máy không đọc được chữ trực tiếp.  
Nó chia văn bản thành các **token** (mảnh nhỏ của từ).

Ví dụ:
- “happiness” → “hap” + “pi” + “ness”
- “cat” → 1 token

---

### 4. Embeddings
Mỗi token được chuyển thành một vector số (embedding).

Hiểu đơn giản:
> Từ có nghĩa gần nhau sẽ nằm gần nhau trong không gian số.

---

### 5. Attention
Cơ chế giúp mô hình biết **từ nào quan trọng trong ngữ cảnh**.

Ví dụ:
- “river bank” → bank = bờ sông  
- “bank account” → bank = ngân hàng  

---

### 6. Transformer
Kiến trúc kết hợp:
- Attention
- Mạng nơ-ron nhiều lớp

Ưu điểm lớn:
- Xử lý song song
- Mở rộng quy mô rất lớn

---

## III. Large Language Models (LLM)

### 7. LLM (Large Language Model)
Là Transformer được huấn luyện trên khối lượng văn bản cực lớn.

Nhiệm vụ cốt lõi:
> Dự đoán token tiếp theo.

---

### 8. Context Window
Là số token tối đa mô hình có thể “nhìn thấy” trong một lần.

---

### 9. Temperature
Điều chỉnh độ “ngẫu nhiên” khi sinh văn bản.

- 0 → rất chính xác  
- 0.7 → cân bằng  
- 1+ → sáng tạo nhưng dễ loạn  

---

### 10. Hallucination (Ảo giác)
Khi AI trả lời rất tự tin… nhưng sai.

---

## IV. Huấn luyện & Tối ưu

### 11. Fine-tuning
Tiếp tục huấn luyện mô hình trên dữ liệu chuyên biệt.

---

### 12. RLHF (Reinforcement Learning from Human Feedback)
Giúp AI trở nên:
- Lịch sự  
- An toàn  
- Hữu ích hơn  

---

### 13. LoRA (Low-Rank Adaptation)
Cách fine-tune tiết kiệm tài nguyên bằng cách thêm adapter nhỏ.

---

### 14. Quantization
Giảm số bit lưu trọng số để mô hình nhỏ hơn và chạy nhanh hơn.

---

## V. Prompting & Reasoning

### 15. Prompt Engineering
Nghệ thuật đặt câu hỏi cho AI để có câu trả lời tốt hơn.

---

### 16. Chain of Thought (CoT)
Yêu cầu AI suy nghĩ từng bước trước khi đưa ra đáp án.

---

## VI. Xây dựng hệ thống AI

### 17. RAG (Retrieval-Augmented Generation)
Kết hợp LLM với tài liệu bên ngoài để giảm sai sót.

---

### 18. Vector Database
Lưu trữ embedding và tìm kiếm theo ngữ nghĩa thay vì từ khóa.

---

### 19. AI Agents
LLM có thể thực hiện hành động như gọi API, chạy code, tìm kiếm web.

---

### 20. Diffusion Models
Mô hình tạo ảnh bằng cách học cách loại bỏ nhiễu dần dần.

---

# Tổng Kết

| Nhóm | Bao gồm |
|------|----------|
| Nền tảng | Neural Network, Transformer, Embeddings |
| Mô hình lớn | LLM, Context, Temperature, Hallucination |
| Hệ thống | RAG, Vector DB, Agents |
