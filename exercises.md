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
> *Khi temperature tăng từ 0.0 lên 1.5, câu trả lời trở nên đa dạng, sáng tạo và ít mang tính “an toàn” hơn. Temperature thấp tạo ra phản hồi ổn định, ngắn gọn và nhất quán, trong khi temperature cao thường tạo ra các cách diễn đạt bất ngờ hoặc đôi khi hơi lan man.*

**Bạn sẽ đặt temperature bao nhiêu cho chatbot hỗ trợ khách hàng, và tại sao?**
> *Tôi sẽ đặt temperature khoảng 0.2–0.5 cho chatbot hỗ trợ khách hàng. Mức này giúp phản hồi vẫn tự nhiên nhưng giữ được tính chính xác, ổn định và tránh tạo ra thông tin không đáng tin cậy.*

---

### Bài tập 2.2 — Đánh Đổi Chi Phí
Xem xét kịch bản: 10.000 người dùng hoạt động mỗi ngày, mỗi người thực hiện 3 lần gọi API, mỗi lần trung bình ~350 token.

**Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:**
> *Ước tính xem GPT-4o đắt hơn GPT-4o-mini bao nhiêu lần cho workload này:*
*Theo bảng pricing trong bài lab:
GPT-4o input/output: $5 / $20
GPT-4o-mini input/output: $0.15 / $0.60
Tỷ lệ chi phí gần đúng là:
Input: 5 / 0.15 ≈ 33 lần
Output: 20 / 0.60 ≈ 33 lần*

**Mô tả một trường hợp mà chi phí cao hơn của GPT-4o là xứng đáng, và một trường hợp GPT-4o-mini là lựa chọn tốt hơn:**
> *GPT-4o phù hợp cho các tác vụ cần suy luận mạnh và độ chính xác cao như trợ lý lập trình, phân tích tài liệu pháp lý hoặc hỗ trợ y tế.*
*GPT-4o-mini phù hợp hơn cho chatbot FAQ, hỗ trợ khách hàng cơ bản hoặc các ứng dụng quy mô lớn cần tối ưu chi phí và tốc độ.*

---

### Bài tập 2.3 — Trải Nghiệm Người Dùng với Streaming
**Streaming quan trọng nhất trong trường hợp nào, và khi nào thì non-streaming lại phù hợp hơn?** (1 đoạn văn)
> *Streaming quan trọng nhất trong các ứng dụng chat thời gian thực như AI assistant hoặc chatbot hỗ trợ khách hàng, vì người dùng có thể thấy phản hồi xuất hiện dần thay vì phải chờ toàn bộ kết quả hoàn thành. Điều này tạo cảm giác hệ thống phản hồi nhanh hơn và tự nhiên hơn. Ngược lại, non-streaming phù hợp hơn khi kết quả cần hoàn chỉnh trước khi hiển thị, ví dụ như tạo báo cáo, phân tích dữ liệu hoặc xuất nội dung dài cần xử lý toàn bộ trước khi trả về.*


## Danh Sách Kiểm Tra Nộp Bài
- [ ] Tất cả tests pass: `pytest tests/ -v`
- [ ] `call_openai` đã triển khai và kiểm thử
- [ ] `call_openai_mini` đã triển khai và kiểm thử
- [ ] `compare_models` đã triển khai và kiểm thử
- [ ] `streaming_chatbot` đã triển khai và kiểm thử
- [ ] `retry_with_backoff` đã triển khai và kiểm thử
- [ ] `batch_compare` đã triển khai và kiểm thử
- [ ] `format_comparison_table` đã triển khai và kiểm thử
- [ ] `exercises.md` đã điền đầy đủ
- [ ] Sao chép bài làm vào folder `solution` và đặt tên theo quy định 
