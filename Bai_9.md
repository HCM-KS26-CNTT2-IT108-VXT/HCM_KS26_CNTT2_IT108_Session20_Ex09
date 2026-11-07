# Bài 9: Xây Dựng Prompt 3 Thành Phần Giải Mã Lỗi Trạm Sạc

## Phần 1: Thiết kế Prompt 3 Thành phần

**1. Vì sao câu hỏi ban đầu khiến AI trả lời sai?**

Vì câu hỏi quá chung chung, không cung cấp nội dung lỗi và thông tin hệ thống nên AI dễ đoán sai nguyên nhân (Hallucination).

**2. Prompt 3 Thành phần**

**[Context]**

Tôi đang vận hành trạm sạc VoltCharge số 04, sử dụng Windows 11.

**[Raw Error]**

```text
UnauthorizedAccessException:
Access to the path 'C:\Program Files\VoltCharge\data\session.log' is denied.
Process terminated with exit code 5.
```

**[Instruction]**

Hãy giải thích lỗi bằng tiếng Việt dễ hiểu và đưa ra 3 bước khắc phục an toàn.

## Phần 2: Giải mã lỗi và khắc phục

**3. Nguyên nhân lỗi**

Ứng dụng không có quyền ghi dữ liệu vào file `session.log` trong thư mục Program Files nên không thể khởi động bình thường.

**4. Ba bước xử lý**

- Bước 1: Nhấn chuột phải vào ứng dụng VoltCharge, chọn Run as Administrator.
- Bước 2: Vào Properties → Security của thư mục `data` để kiểm tra quyền truy cập.
- Bước 3: Nhờ quản trị viên cấp quyền Write phù hợp, sau đó khởi động lại ứng dụng để kiểm tra.

**5. Xử lý API_KEY**

Phải xóa hoặc thay mã bí mật bằng `[REDACTED]` trước khi gửi cho AI.

**Lý do:** Tránh bị lộ thông tin, giúp người khác lợi dụng mã để truy cập hệ thống trái phép.