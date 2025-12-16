# 🏢 S2O Admin Web

**S2O Admin Web** là dashboard quản trị dành cho các operator của hệ sinh thái **S2O (Scan2Order)** – một nền tảng SaaS đa tenant phục vụ quản lý nhà hàng, QR ordering, ứng dụng khách hàng, và AI services.

Thông qua dashboard này, các admin có thể quản lý tenants, cấu hình hệ thống, giám sát hoạt động và doanh thu, cũng như thiết lập các tính năng AI.

---

## 📌 Repository Overview

| Repository      | Mục đích                                                   |
|-----------------|------------------------------------------------------------|
| s2o-admin-web   | Dashboard admin: quản lý tenants, cấu hình hệ thống, giám sát, AI configuration panel |

**Các repo liên quan trong hệ sinh thái S2O:**
- **s2o-api** – Backend chính với multi-tenant, auth, menu, order, reporting  
- **s2o-restaurant-web** – Web quản lý nhà hàng, menu, bàn, order  
- **s2o-guest-web** – Web QR ordering cho khách  
- **s2o-mobile** – Mobile app khách hàng  
- **s2o-ai-chatbot** – AI chatbot & recommendation engine  
- **s2o-infra** – Hạ tầng, DevOps, CI/CD pipelines  
- **s2o-docs** – Central documentation hub  

---

## ⚙️ Features

- **Tenant Management:** Onboard nhà hàng mới, quản lý tenants hiện có  
- **System Configuration:** Cấu hình hệ thống, phân quyền, global settings  
- **Monitoring:** Dashboard giám sát doanh thu, hoạt động hệ thống  
- **AI Configuration:** Quản lý các tham số AI recommendation engine  
- **Reporting & Analytics:** Tổng hợp báo cáo hoạt động và doanh thu  

---

## 🏗️ Architecture Overview

**S2O Admin Web** tương tác trực tiếp với **s2o-api** để thực hiện các tác vụ quản trị. Tổng quan kiến trúc:

```text
Admin Web App
      |
      v
  S2O Backend API
      |
+-----+-----+
| DB | Redis |
|PgSQL|Cache|
+-----+-----+
Frontend: React / Next.js (functional components + hooks)

Backend API: kết nối với s2o-api (RESTful, JWT auth)

Cache & DB: Redis, PostgreSQL (multi-tenant)

🛠️ Development Setup
Prerequisites
Node.js >= 18

npm hoặc yarn

Access tới backend API (s2o-api)

Environment file .env (dựa trên .env.example)

Install Dependencies
Sao chép mã
npm install
# hoặc
yarn install

Run Development Server
Sao chép mã
npm run dev
# hoặc
yarn dev

Build Production
Sao chép mã
npm run build
npm run start

Lint & Format
Sao chép mã
npm run lint
npm run format


🧭 Workflow & Contribution
Tuân theo quy chuẩn từ CONTRIBUTING.md và WORKFLOW.md:

Branch Naming
Sao chép mã
type(scope): short-description-TASKCODE
Example:
Sao chép mã
feat(admin-web): add-tenant-dashboard-SSRMPWQCO-21
fix(admin-web): resolve-login-error-SSRMPWQCO-33

Commit Message
Sao chép mã
type(scope): short description TASKCODE
Một commit = một logical change

Tránh commit mơ hồ (update, fix, temp)

Pull Request Checklist
Chạy đúng local environment

Không còn debug logs

Task code trong PR title

Rebase với main hoặc develop

Cập nhật tests nếu cần

🔒 Security
Không commit .env hoặc secrets

RBAC và HTTPS enforced

Input validation & secure password hashing

📑 Documentation References
Architecture Overview

Workflow

Repositories Overview

Contributing Guide

📬 Contact
Mọi câu hỏi hoặc đề xuất, vui lòng mở Issue hoặc Pull Request trong repository này.

🎉 Thank you for contributing to S2O Admin Web!