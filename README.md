# Xe Điện A&T Rạch Giá

Trang giới thiệu (landing page) một trang cho dịch vụ xe điện A&T tại Rạch Giá, Kiên Giang: đưa đón sân bay/bến tàu, tham quan nội ô, xe cưới hỏi - sự kiện, cho thuê theo giờ/ngày. Khách đặt xe qua điện thoại/Zalo (0852 755 277) hoặc gửi form đặt xe ngay trên trang.

## Công nghệ sử dụng

- HTML/CSS/JS tĩnh, không cần framework hay bước build
- **Netlify Forms** cho form "Gửi yêu cầu đặt xe" (gửi AJAX, không cần backend)
- **Netlify Image CDN** (`/.netlify/images`) để tối ưu và chuyển đổi định dạng ảnh (WebP) theo kích thước hiển thị
- Ảnh minh họa (xe điện, đội xe, tài xế) được tạo bằng Netlify AI Gateway (mô hình ảnh Gemini) và lưu trong `img/`

## Cấu trúc file

```
index.html      Toàn bộ nội dung trang (header, hero, dịch vụ, bảng giá, tuyến đường, đánh giá, liên hệ, footer)
styles.css      Toàn bộ style
script.js       Menu mobile, đếm số liệu, gửi form AJAX
img/            Ảnh minh họa (hero, đội xe, tài xế)
netlify.toml    Cấu hình publish + cache header cho ảnh
```

## Chạy thử ở local

Không cần build. Dùng Netlify CLI để giả lập đầy đủ tính năng Netlify (Forms, Image CDN):

```bash
netlify dev --port 8889
```

Sau đó mở `http://localhost:8889`.

## Chỉnh sửa nội dung

- Số điện thoại/Zalo, giá, tuyến đường: sửa trực tiếp trong `index.html`
- Thông tin công ty ở footer ("VỀ CHÚNG TÔI"): trong khối `.footer-col--about` của `index.html`
- Đơn đặt xe gửi về mục **Forms** trong Netlify UI của site này
