# AGENTS.md

## Kiến trúc

Site tĩnh một trang (single-page), không có build step:

- `index.html` — toàn bộ nội dung, chia theo section có id (`#gioi-thieu`, `#dich-vu`, `#bang-gia`, `#tuyen-duong`, `#danh-gia`, `#lien-he`) dùng cho anchor nav.
- `styles.css` — design tokens ở `:root` (màu xanh lá thương hiệu, bo góc, shadow). BEM-ish class naming (`.hero__lead`, `.card__icon`...).
- `script.js` — 3 việc độc lập: toggle menu mobile, animate số liệu (`IntersectionObserver`), submit form đặt xe qua AJAX tới Netlify Forms.
- `img/` — ảnh PNG được tạo qua Netlify AI Gateway (Gemini image model), phục vụ qua Netlify Image CDN (`/.netlify/images?url=/img/...`) để resize/convert WebP, không nhúng ảnh gốc trực tiếp.
- `netlify.toml` — `publish = "."` (không có build command), cache header dài hạn cho `/img/*`.

## Quy ước

- Toàn bộ nội dung bằng tiếng Việt trừ địa chỉ công ty có kèm bản tiếng Anh ở footer theo yêu cầu ban đầu.
- Số điện thoại/Zalo cố định: `0852 755 277`, xuất hiện ở header, hero, banner CTA, contact section, mobile call-bar, và floating action button — sửa cả các vị trí này nếu đổi số.
- Form đặt xe dùng Netlify Forms (`data-netlify="true"`, `name="dat-xe"`), có honeypot field chống spam. Vì đây là site tĩnh (không SSR), form được Netlify build bot detect trực tiếp từ `index.html` — không cần file skeleton riêng.

## Việc còn lại

Không có PLAN.md — đây là một trang landing page hoàn chỉnh, không có milestone kế tiếp. Nếu cần mở rộng (đa ngôn ngữ, CMS quản lý giá/tuyến đường, tích hợp CRM cho lead từ form), hãy đánh giá lại nhu cầu trước khi thêm backend/database.
