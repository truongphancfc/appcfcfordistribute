# Công cụ thiết kế ảnh – Nhà phân phối / Đại lý CÒ BAY

Trang web tĩnh (1 file `index.html`) giúp đại lý của **CÒ BAY** (CFC – Công ty CP
Phân bón & Hoá chất Cần Thơ) tự tạo ảnh đăng Facebook / Zalo:

- Logo Cò Bay, QR Zalo OA và dòng xác nhận chính hãng **cố định** (đã nhúng sẵn, chạy offline).
- Đại lý chỉ tải ảnh + logo của mình, điền tên / mô tả / số liên hệ → bấm **Tải ảnh PNG**.
- 5 khổ: 1080×1080, 1080×1350, 1080×1920 (9:16), 1200×675 (16:9), 851×315 (bìa FB).
- Bảng màu nhấn thương hiệu, nền Tối / Sáng, xem trước trực tiếp.

## Cấu trúc repo
```
.
├── index.html      # toàn bộ công cụ (đã nhúng logo + QR base64)
├── vercel.json     # cấu hình deploy tĩnh
├── .gitignore
└── .gitattributes
```

## Chạy thử ở máy
Mở thẳng `index.html` bằng trình duyệt là chạy. (Không cần cài đặt gì.)

## Đưa lên GitHub
```bash
git init
git add .
git commit -m "Khởi tạo công cụ thiết kế ảnh cho đại lý Cò Bay"
git branch -M main
git remote add origin https://github.com/<tai-khoan>/<ten-repo>.git
git push -u origin main
```
> Có thể để repo **Private** vẫn deploy Vercel bình thường.

## Deploy lên Vercel (gắn với GitHub)
1. Vào https://vercel.com → **Add New → Project → Import Git Repository**.
2. Chọn repo này → **Deploy** (không cần chỉnh gì, đây là site tĩnh).
3. Nhận link `https://<ten>.vercel.app` → gửi cho đại lý.
4. Sau này chỉ cần sửa `index.html` rồi `git push` — Vercel **tự build lại** bản mới.

## Cập nhật logo / QR sau này
Logo và QR nằm dưới dạng chuỗi `data:image/png;base64,...` trong `index.html`
(các hằng `LOGO_GREEN`, `LOGO_WHITE`, `LOGO_QR`). Thay chuỗi tương ứng là đổi được,
hoặc gửi file mới để cập nhật.
