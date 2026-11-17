# Vận dụng cơ bản 1: Sửa prompt thiếu ràng buộc định dạng

## Bước 1: Phân tích lỗi

**Prompt cũ:** `Hãy giải thích ngắn gọn các nội dung của Chain-of-Thought, Prompt Chaining, xử lý đứt gãy.`

**3 phần thừa trong câu trả lời cũ:**

| # | Đoạn thừa | Loại |
|---|---|---|
| 1 | "Chào bạn!" | Lời chào |
| 2 | "Rất vui được giải thích về các kỹ thuật này." | Lời dẫn |
| 3 | "Hy vọng hữu ích! Cần thêm ví dụ cứ hỏi nhé." | Lời kết |

**Nguyên nhân:** "ngắn gọn" quá mơ hồ, không quy định định dạng, không cấm văn xã giao.

## Bước 2: Prompt tối ưu

```text
Giải thích Chain-of-Thought, Prompt Chaining, xử lý đứt gãy.
BẮT BUỘC: đúng 3 gạch đầu dòng, mỗi gạch 1 kỹ thuật, tối đa 20 từ, dạng "**Tên**: định nghĩa".
Bắt đầu thẳng vào gạch đầu tiên.
CẤM: lời chào, lời dẫn, lời kết, giải thích ngoài 3 gạch.
```

**Kết quả mong đợi:**

```markdown
- **Chain-of-Thought**: yêu cầu AI suy luận từng bước trước khi đưa ra đáp án.
- **Prompt Chaining**: chia bài toán lớn thành nhiều prompt nối tiếp nhau.
- **Xử lý đứt gãy**: bắt lỗi, thử lại hoặc dừng an toàn khi một bước thất bại.
```
