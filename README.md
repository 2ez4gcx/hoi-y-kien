# Hỏi Ý Kiến 💘

Webapp trêu chọc kiểu "tỏ tình không đường lui":

1. Người tạo mở trang, chọn **ngôn ngữ** (🇻🇳 Tiếng Việt / 🇬🇧 English), nhập câu muốn hỏi → nhận **link chia sẻ** (ngôn ngữ nhúng sẵn trong link).
2. Người nhận mở link, thấy câu hỏi với 2 nút:
   - **Đồng ý 💖** → mưa tim chúc mừng 🎉
   - **Không đồng ý** → nút **chạy trốn mượt mà khỏi con chuột**: chuột lại gần là lùi ra xa, dí sát thì tăng tốc, kẹt góc thì phóng dọc tường thoát thân — nhưng **không bao giờ chạy đè lên nút Đồng ý**. Đồng hồ 3 giây **chỉ đếm lúc đang bị rượt** (buông chuột là tạm dừng). Đủ 3 giây bị rượt thì nút chịu thua đứng yên, nhưng bấm vào thì bị **sợi xích ⛓️ + ổ khoá 🔒** quấn lại, không bấm được nữa.

## Cách hoạt động (vì sao miễn phí 100%)

- Chỉ có **1 file `index.html`** — HTML/CSS/JS thuần, không framework, không backend, không database.
- Câu hỏi được mã hoá **base64url ngay trong link** (`?q=...`), hỗ trợ tiếng Việt + emoji. Không lưu dữ liệu ở đâu cả → không tốn chi phí server.

## Chạy thử trên máy

```bash
python -m http.server 8734
```

Rồi mở http://localhost:8734

## Deploy public miễn phí (chọn 1 trong các cách)

### Cách 1 — GitHub Pages (khuyên dùng, link vĩnh viễn)
1. Tạo repo mới trên GitHub (ví dụ `hoi-y-kien`), upload `index.html`.
2. Vào **Settings → Pages → Source: Deploy from a branch → main / root** → Save.
3. Sau ~1 phút có link dạng `https://<username>.github.io/hoi-y-kien/`.

### Cách 2 — Netlify Drop (nhanh nhất, không cần tài khoản git)
1. Mở https://app.netlify.com/drop
2. Kéo thả thư mục chứa `index.html` vào → có link `https://<tên>.netlify.app` ngay lập tức.

### Cách 3 — Vercel / Cloudflare Pages
- Vercel: `npx vercel` trong thư mục này, hoặc import repo trên vercel.com.
- Cloudflare Pages: dash.cloudflare.com → Pages → Upload assets.

Cả 4 dịch vụ đều free cho trang tĩnh, có HTTPS sẵn.

## Tuỳ biến nhanh

Mở `index.html`:
- `FLEE_DURATION` — tổng thời gian bị rượt thì nút mới chịu dừng (mặc định 3000 ms).
- `REACT_RADIUS` — con trỏ cách mép nút bao nhiêu px thì nút bắt đầu lùi (mặc định 150).
- `I18N` — bảng ngôn ngữ (vi/en); muốn thêm tiếng khác chỉ cần thêm một mục mới cùng cấu trúc.
