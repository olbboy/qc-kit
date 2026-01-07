# 📘 QC-Kit: Cẩm Nang Antigravity (v1.0.0)

> **"Chúng tôi không chỉ test. Chúng tôi suy nghĩ, xác minh, và phòng ngừa."**

Chào mừng đến với **Biệt Đội Kiểm Soát Chất Lượng (Antigravity Native)**.
Đây không phải chatbot. Đây là **Hệ thống Chuyên gia Đa tác tử** được thiết kế để hỗ trợ **Kiểm Soát Chất Lượng Độ Tin Cậy Cao** (lấy cảm hứng từ CMMI Level 5).

---

## 🌌 Triết Lý: Ba Trụ Cột của Trí Tuệ Kiểm Thử

Để làm chủ bộ công cụ này, bạn phải hiểu cách Biệt Đội "tư duy".

### 1. 🧠 Nhận Thức Hệ Thống 2 (Bộ Não)
AI thông thường tạo test ngay lập tức (Hệ thống 1). Điều này dễ bỏ sót edge cases.
**Các Agent của chúng tôi Dừng lại & Suy nghĩ.**
*   **Vòng Lặp Phản Tư**: Trước khi deliver, mỗi agent tự phê bình output.
*   **Tool Mandates**: Họ không giả định tests chạy đúng (họ chạy thật). Họ không đoán coverage (họ dùng Python).

### 2. 🤝 Phối Hợp Biệt Đội (Mạng Lưới)
Các agent không hoạt động riêng lẻ. Họ tạo thành **Mạng Lưới Kiểm Thử Phối Hợp (DAG)**.
*   **Cách cũ**: Bạn gọi `@qc-testcase`. Xong việc. Bạn tự hỏi tiếp theo là gì.
*   **Cách mới**: `@qc-testcase` hoàn thành và *khuyến nghị*: "Handover: Triệu hồi `@qc-automation` để viết script."

### 3. 📒 Ngữ Cảnh Test (Bộ Nhớ)
Biệt đội chia sẻ "Bộ Nhớ Kiểm Thử" qua `templates/TEST_CONTEXT.md`.
*   **Vấn đề**: "Tôi bảo `@qc-testcase` test trên Chrome, nhưng `@qc-automation` viết script cho Safari."
*   **Giải pháp**: Bạn định nghĩa Ngữ cảnh MỘT LẦN. Tất cả 15 agents đọc trước khi hành động.

---

## 🚦 Đội Hình: 15 Chuyên Gia, Một Sứ Mệnh

| Agent | Vai Trò | Khi Nào Triệu Hồi |
| :--- | :--- | :--- |
| **CHỈ HUY** | | |
| **`@qc-master`** | *Chiến Lược Gia* | "Tôi bắt đầu dự án mới. Giúp tôi lập kế hoạch test." |
| **KHỐI THIẾT KẾ** | | |
| **`@qc-strategy`** | *Kiến Trúc Sư* | "Tạo chiến lược test cho release này." |
| **`@qc-testcase`**| *Nhà Thiết Kế* | "Generate test cases từ User Story này." |
| **`@qc-data`** | *Kỹ Sư Dữ Liệu* | "Tạo test data edge case cho email." |
| **KHỐI THỰC THI**| | |
| **`@qc-manual`** | *Thám Hiểm Viên* | "Làm bug hunt trên checkout flow." |
| **`@qc-automation`**| *SDET* | "Convert test cases sang Playwright scripts." |
| **`@qc-api`** | *API Tester* | "Generate tests cho REST API endpoint này." |
| **`@qc-performance`**| *Kỹ Sư Hiệu Năng* | "Tạo k6 load test cho 1000 users." |
| **`@qc-security`** | *Security Tester* | "Audit form này theo OWASP Top 10." |
| **KHỐI PHÂN TÍCH**| | |
| **`@qc-bug`** | *Biên Tập Bug* | "Viết bug report chi tiết cho lỗi này." |
| **`@qc-root-cause`**| *Thám Tử Lỗi* | "Tại sao bug này cứ xảy ra? Dùng 5 Whys." |
| **`@qc-metrics`** | *Nhà Phân Tích* | "Tính test coverage percentage." |
| **`@qc-regression`**| *Bảo Vệ Regression* | "Sau code change này, cần chạy tests nào?" |
| **KHỐI BÁO CÁO**| | |
| **`@qc-report`** | *Biên Tập Báo Cáo* | "Generate test summary cho sprint này." |
| **`@qc-review`** | *Điều Phối Review* | "Review test cases xem đủ chưa." |

---

## ⚔️ Quy Trình Chiến Thuật

### Quy Trình 1: "Tiêm Ngữ Cảnh"
**Ngừng lặp lại thông tin.**
1.  Copy `templates/TEST_CONTEXT.md` vào thư mục gốc dự án.
2.  Điền: `Scope: Login Feature`. `Environment: Chrome, Staging`.
3.  **Kết quả**: Mọi agent đều biết ngữ cảnh testing.

### Quy Trình 2: "User Story → Test Suite"
**Từ zero đến automated tests trong 3 bước.**
1.  `@qc-testcase Generate test cases cho: "User có thể login bằng email/password."`
2.  `@qc-data Generate test data cho login tests.`
3.  `@qc-automation Convert sang Playwright TypeScript.`

### Quy Trình 3: "Khám Nghiệm Bug"
**Tìm nguyên nhân gốc, không chỉ triệu chứng.**
1.  `@qc-bug Viết bug report cho: "Checkout thất bại trên mobile."`
2.  `@qc-root-cause Phân tích bug này bằng 5 Whys.`
3.  `@qc-regression Cần thêm tests nào để phòng ngừa?`

---

## 🚀 Cách Bắt Đầu (Zero-Shot)

Bạn không cần học prompts phức tạp. Các Agent biết phải làm gì.

**Chỉ cần gõ:**
> `@qc-master Tôi cần test tính năng thanh toán mới.`

**Biệt Đội sẽ tiếp quản:**
1.  `@qc-master` phân tích yêu cầu.
2.  Route bạn đến `@qc-strategy` để lập kế hoạch.
3.  `@qc-strategy` route bạn đến `@qc-testcase` để generate cases.
4.  **Phản ứng dây chuyền** bắt đầu.

*Chào mừng đến với Kiểm Thử Hệ Thống 2.*

---

## 🛡️ Tool Mandates (Độ Tin Cậy Cao)

| Agent | Rủi ro Nếu Không Dùng Tool | Tool Bắt Buộc |
| :--- | :--- | :--- |
| `@qc-metrics` | Tính toán sai | `run_command(python)` |
| `@qc-automation` | Scripts không chạy | `run_command(npx playwright test)` |
| `@qc-performance` | Load test không hợp lệ | `run_command(k6 run)` |
| `@qc-security` | Lỗ hổng cũ | `search_web` (OWASP) |
| `@qc-regression` | Bỏ sót dependencies | `grep_search` |

---

## 📊 Tiêu Chuẩn Chất Lượng

Bộ công cụ này được xây dựng trên các tiêu chuẩn hàng đầu:

| Tiêu chuẩn | Ứng dụng |
| :--- | :--- |
| **ISTQB** | Kỹ thuật thiết kế test, quy trình |
| **OWASP Top 10** | Checklist kiểm thử bảo mật |
| **ISO 25010** | Thuộc tính chất lượng (Performance, Security, Usability) |
| **IEEE 829** | Tiêu chuẩn tài liệu test |

---

<p align="center">
  <strong>Được xây dựng cho Kỷ nguyên Antigravity.</strong><br>
  <em>Test Thông minh. Ship Nhanh hơn.</em>
</p>
