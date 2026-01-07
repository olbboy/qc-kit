<p align="center">
  <img src="assets/logo.png?v=1.0.0" alt="QC-Kit Logo" width="200">
</p>

<div align="center">

[**🇬🇧 English**](README.md) | [**🇻🇳 Tiếng Việt**](README.vi.md)

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Phiên%20bản-1.0.0-blue?style=for-the-badge" alt="Version 1.0.0">
  <img src="https://img.shields.io/badge/Agents-15-green?style=for-the-badge" alt="15 Agents">
  <img src="https://img.shields.io/badge/Giao%20thức-Antigravity%20Native-orange?style=for-the-badge" alt="Antigravity Native">
  <img src="https://img.shields.io/badge/Tiêu%20chuẩn-ISTQB%20%7C%20OWASP%20%7C%20ISO%2025010-purple?style=for-the-badge" alt="Standards">
</p>

<h1 align="center">🧪 QC-Kit (Phiên Bản Antigravity)</h1>
<h3 align="center">Biệt Đội Chuyên Gia Kiểm Soát Chất Lượng</h3>

<p align="center">
  <strong>Biến AI thành Đội ngũ QA/QC Đẳng cấp Thế giới</strong><br>
  15 Chuyên gia Tự Kiểm chứng • Tư duy Hệ thống 2 • Automation Excellence
</p>

---

## 🎯 QC-Kit là gì?

QC-Kit là một **Biệt đội Chuyên gia** gồm 15 Chuyên viên Kiểm Soát Chất Lượng được thiết kế cho **Antigravity Native Protocol (ANP)**.

Nó thay thế mô hình "Một Chatbot duy nhất" bằng một **Đội ngũ 15 QC Experts**:
*   Cần Test Cases? Triệu hồi **`@qc-testcase`**.
*   Cần Automation Scripts? Triệu hồi **`@qc-automation`**.
*   Cần Security Audit? Triệu hồi **`@qc-security`**.

Mỗi chuyên gia được trang bị **Tư duy Hệ thống 2** (Vòng Lặp Phản Tư) để "Dừng & Nghĩ" trước khi trả lời, đảm bảo **Độ bao phủ Kiểm thử Cao** (High-Assurance).

---

## 🤖 Biệt Đội Chuyên Gia (15 Personas)

### 🔴 Bộ Chỉ Huy
| Agent | Vai trò | Năng lực |
| :--- | :--- | :--- |
| **`@qc-master`** | **Chiến Lược Gia** | Lập Kế hoạch Test, Đánh giá Rủi ro, Mapping Coverage. |

### 🔵 Khối Thiết Kế
| Agent | Vai trò | Năng lực |
| :--- | :--- | :--- |
| **`@qc-strategy`** | Kiến Trúc Sư Test | Test Pyramid, ISO 25010. |
| **`@qc-testcase`**| Nhà Thiết Kế Test | **Generate Test Cases**, BDD/Gherkin. |
| **`@qc-data`** | Kỹ Sư Dữ Liệu Test | Boundary Values, Edge Cases. |

### 🟡 Khối Thực Thi
| Agent | Vai trò | Năng lực |
| :--- | :--- | :--- |
| **`@qc-manual`** | Tester Thám Hiểm | Session-Based Testing, Bug Hunting. |
| **`@qc-automation`**| SDET | **Playwright/Cypress Scripts**, Page Object Model. |
| **`@qc-api`** | API Tester | REST/GraphQL Testing, Contract Testing. |
| **`@qc-performance`**| Kỹ Sư Hiệu Năng | **k6/JMeter**, Load Testing. |
| **`@qc-security`** | Security Tester | **OWASP Top 10**, SAST/DAST. |

### 🟣 Khối Phân Tích
| Agent | Vai trò | Năng lực |
| :--- | :--- | :--- |
| **`@qc-bug`** | Biên Tập Bug | Bug Reports chi tiết, Phân loại Mức độ. |
| **`@qc-root-cause`**| Thám Tử Lỗi | 5 Whys, Chiến lược Phòng ngừa. |
| **`@qc-metrics`** | Nhà Phân Tích QA | **Python-Verified** Coverage %, Defect Density. |
| **`@qc-regression`**| Bảo Vệ Regression | Impact Analysis, Tối ưu Test Suite. |

### ⚫ Khối Báo Cáo
| Agent | Vai trò | Năng lực |
| :--- | :--- | :--- |
| **`@qc-report`** | Biên Tập Báo Cáo | Test Summary, Executive Dashboard. |
| **`@qc-review`** | Điều Phối Review | Test Case Reviews, V&V. |

---

## 🚀 Bắt Đầu Nhanh (Antigravity Native)

### 1. Cài Đặt
Sao chép workflows vào "bộ não" của Agent:
```bash
cp -r qc-kit/.agent/workflows/ ~/.gemini/antigravity/workflows/
```

### 2. Triệu Hồi
Trong khung chat, chỉ cần gõ `@` theo sau là Tên Agent:
> **User**: *"@qc-testcase Generate test cases cho Login feature."*

> **@qc-testcase**: *"Test Designer nhận lệnh. Em sẽ tạo Positive, Negative, và Edge cases..."*

### 3. "Chế Độ Flash"
Chuyển đổi agent ngay lập tức:
> **User**: *"@qc-automation Convert những test cases này sang Playwright."*

---

## 🧠 Trí Tuệ Hệ Thống 2

Tất cả các agent đều tuân theo **Vòng Lặp Nhận Thức Phản Tư**:
1.  **Phân tích (Hệ thống 1)**: Khớp mẫu nhanh.
2.  **Hành động (Hệ thống 1)**: Phác thảo test cases/scripts.
3.  **Phản Tư (Hệ thống 2)**: **DỪNG & NGHĨ**.
    *   *Phê bình*: "Em có bỏ sót edge case nào không?"
    *   *Hành động*: Thêm test cases bổ sung.
4.  **Đầu ra**: Test Artifacts Đã Xác minh, Hoàn chỉnh.

---

## 📁 Cấu Trúc Repository

```
qc-kit/
│
├── .agent/workflows/           # 🤖 Bộ não (15 Agent Definitions)
├── docs/knowledge_base/        # 📚 Kho Tri thức (ISTQB, OWASP, etc.)
│   ├── core/                   # 🔵 Core QC Skills
│   ├── specialized/            # 🟡 Specialized Skills
│   └── advanced/               # 🟣 Advanced Skills
├── templates/                  # 🟢 Test Templates
└── README.md                   # 📄 File này
```

---

## 📄 Giấy Phép

MIT License. Miễn phí sử dụng cho dự án cá nhân và doanh nghiệp.

---

<p align="center">
  <strong>Được xây dựng cho Kỷ nguyên Antigravity.</strong><br>
  <em>Test Thông minh. Ship Nhanh hơn.</em>
</p>
