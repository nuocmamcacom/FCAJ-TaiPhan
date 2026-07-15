# FCAJ - Phan Tài

Live demo: https://nuocmamcacom.github.io/FCAJ-TaiPhan/

Repository: https://github.com/nuocmamcacom/FCAJ-TaiPhan

---

## Thông tin sinh viên

- **Full name:** Phan Văn Tài
- **Phone number:** 0972009161
- **Email:** phanvantai.dev@gmail.com
- **University:** Ho Chi Minh City University of Technology (HUTECH)
- **Major:** Information Technology
- **Specialization:** Software Engineering

## Thông tin thực tập

- **Company / Program:** Bootcamp First Cloud AI Journey
- **Position:** Workforce Bootcamp 
- **Duration:** April 17, 2026 – July 30, 2026

---

## Mô tả dự án

Đây là trang tài liệu / hồ sơ cá nhân được xây dựng bằng Hugo để ghi lại hành trình học và thực hành các dịch vụ AWS trong khuôn khổ Bootcamp "First Cloud AI Journey". Site chứa các bài học, worklog, proposal, workshop, và feedback — được tổ chức dưới dạng các section trong thư mục `content/`.

Mục tiêu:
- Ghi chép rõ ràng các bài học, demo và hướng dẫn triển khai trên AWS.
- Triển khai site tĩnh lên GitHub Pages để làm portfolio và tham khảo.

---

## Dịch vụ / công nghệ sử dụng

- Hugo (static site generator)
- GitHub Pages (deploy)
- GitHub Actions (CI build/deploy)
- Các dịch vụ AWS (được ghi chép trong nội dung)

---

## Cấu trúc chính của repository

- `archetypes/` — mẫu nội dung cho Hugo
- `config.toml` — cấu hình site (baseURL, theme, params...)
- `content/` — nội dung site (Worklog, Proposal, Blogs, Workshop, Self-eval, Feedback)
- `layouts/` — template Hugo (partials, shortcodes)
- `static/` — tài nguyên tĩnh (ảnh, css, js)
- `themes/` — Hugo theme
- `.github/workflows/hugo.yml` — CI để build và deploy site

---

## Chạy local

Yêu cầu: Hugo đã được cài đặt trên máy.

Các bước cơ bản:

```bash
# clone repo
git clone https://github.com/nuocmamcacom/FCAJ-TaiPhan.git
cd FCAJ-TaiPhan

# chạy server Hugo (chạy ở chế độ draft nếu cần)
hugo server -D

# mở trình duyệt tới:
# http://localhost:1313/FCAJ-TaiPhan/  (hoặc http://localhost:1313/ tùy cấu hình baseURL)
```

---

## Mục tiêu học tập (Learning objectives)

- Nắm vững kiến trúc hạ tầng AWS cơ bản và các dịch vụ phổ biến (EC2, S3, RDS, IAM...)
- Triển khai và cấu hình ứng dụng trên nền tảng đám mây
- Ghi lại quá trình học tập, phát triển kỹ năng DevOps/Cloud

---

## Xem trước

Live demo (GitHub Pages): https://nuocmamcacom.github.io/FCAJ-TaiPhan/

---

## Liên hệ

- Email: phanvantai.dev@gmail.com
- Phone: 0972009161
- GitHub: https://github.com/nuocmamcacom

---

## Lời cảm ơn

Cảm ơn Bootcamp First Cloud AI Journey và đội ngũ hướng dẫn đã hỗ trợ, cùng các tài nguyên mở giúp em hoàn thành dự án này.
