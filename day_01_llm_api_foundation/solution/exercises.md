# Ngày 1 — Bài Tập & Phản Ánh
## Nền Tảng LLM API | Phiếu Thực Hành

**Thời lượng:** 1:30 giờ  
**Cấu trúc:** Lập trình cốt lõi (60 phút) → Bài tập mở rộng (30 phút)

---

## Phần 1 — Lập Trình Cốt Lõi (0:00–1:00)

Chạy các ví dụ trong Google Colab tại: https://colab.research.google.com/drive/172zCiXpLr1FEXMRCAbmZoqTrKiSkUERm?usp=sharing

Triển khai tất cả TODO trong `template.py`. Chạy `pytest tests/` để kiểm tra tiến độ.

**Điểm kiểm tra:** Sau khi hoàn thành 4 nhiệm vụ, chạy:
```bash
python template.py
```
Bạn sẽ thấy output so sánh phản hồi của GPT-4o và GPT-4o-mini.

---

## Phần 2 — Bài Tập Mở Rộng (1:00–1:30)

### Bài tập 2.1 — Độ Nhạy Của Temperature
Gọi `call_openai` với các giá trị temperature 0.0, 0.5, 1.0 và 1.5 sử dụng prompt **"Hãy kể cho tôi một sự thật thú vị về Việt Nam."**

**Bạn nhận thấy quy luật gì qua bốn phản hồi?** (2–3 câu)
> *Qua 4 phản hồi, khi tăng giá trị temperature thì câu trả lời có nhiều sự so sánh, cảm thán và sáng tạo hơn. Ngược lại, với temperature thấp thì câu trả lời mang tính xác định, nhất quán và chỉ đưa ra thông tin đơn giản. Từ đó cho thấy giá trị temperature chỉ định mức độ ngẫu nhiên của phản hồi của mô hình*

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> *Em sẽ đặt temperature trong khoảng 0.2-0.5 cho chatbot hỗ trợ khách hàng, vì chatbot mục đính là hỗ trợ khách hàng thì độ tin cậy và sự nhất quán được để cao hơn sự sáng tạo/ngẫu nhiên trong phản hồi, vì vậy chọn khoảng thấp cho temperature là hợp lý*

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> *Chi phí tỉ lệ với giá mỗi 1k token, Vì GPT-4o (0.010USD) đắt hơn GPT-4o-mini (0.0006USD) với mỗi 1k token, GPT-4o đắt hơn 0.01/0.006= 16.67 lần so với GPT-4o-mini.*

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> *Khi mục đích sử dụng cần độ chính xác cao và suy luận phức tạp (như tài chính, nghiên cứu, ...) thì GPT-4o xứng đáng. Khi mục đích sử dụng cần tối ưu chi phí và xử lý tác vụ đơn giản thì sử dụng GPT-4o-mini là hợp lý.*

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> *Streaming quan trong nhất trong các trường hợp cần phản hồi nhanh và cảm giác giống đối thoại trực tiếp, ví dụ chatbot hỗ trợ khách hàng, trợ lý ảo, ... Ngược lại, non-streaming phù hợp với trường hợp cần kết quả hoàn chỉnh, ngắn gọn và chính xác, ví dụ như các task backend, tạo report, ...*


## Danh Sách Kiểm Tra Nộp Bài
- [x] Tất cả tests pass: `pytest tests/ -v`
- [x] `call_openai` đã triển khai và kiểm thử
- [x] `call_openai_mini` đã triển khai và kiểm thử
- [x] `compare_models` đã triển khai và kiểm thử
- [x] `streaming_chatbot` đã triển khai và kiểm thử
- [x] `retry_with_backoff` đã triển khai và kiểm thử
- [x] `batch_compare` đã triển khai và kiểm thử
- [x] `format_comparison_table` đã triển khai và kiểm thử
- [x] `exercises.md` đã điền đầy đủ
- [x] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 
