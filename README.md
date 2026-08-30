# Website lịch sử tương tác – Phùng Hưng

Project song ngữ VI/EN, được chuyển đổi từ mẫu lịch sử tương tác v5.8.5 và giữ nguyên kiến trúc/giao diện nền.

## Cấu trúc chính
- `public/index.html`, `public/styles.css`, `public/app.js`: frontend.
- `public/data/phung-hung.json`: hồ sơ, timeline, facts có `sourceId`, nguồn, gợi ý và nhập vai.
- `public/assets/`: GLB và audio VI/EN.
- `server.js`: Express API cho AI, TTS và analytics server-to-server.
- `validate-project.js`: kiểm tra JSON, asset, hard-code, analytics, Google Sheets và cú pháp JS.

## Chạy local
```bash
npm install
cp .env.example .env
npm start
```
Mở `http://localhost:3000`; kiểm tra `http://localhost:3000/health`.

## Biến môi trường
```text
OPENAI_API_KEY=
OPENAI_TEXT_MODEL=
OPENAI_TTS_MODEL=
ANALYTICS_API_URL=https://quan-ly-s7j8.vercel.app
ANALYTICS_INGEST_KEY=
```
Không đưa secret vào frontend, GitHub hoặc ZIP.

## GitHub và Vercel
1. Tạo repository, push toàn bộ project trừ `.env` và `node_modules`.
2. Import repository vào Vercel.
3. Khai báo các Environment Variables ở trên.
4. Deploy; frontend và backend dùng chung domain, vì vậy `API_BASE_URL` mặc định để trống trong `public/config.js`.

## Kiểm tra
```bash
npm run validate
node --check public/app.js
node --check server.js
```
- `/health` phải trả `character: phung-hung`.
- Mở trang, kiểm tra GLB, audio VI/EN, Hồ sơ, Timeline, Tra cứu, Giả định, Nhập vai và PDF.
- Để test analytics, đặt đúng `ANALYTICS_API_URL` và `ANALYTICS_INGEST_KEY`, sau đó tạo phiên và thao tác các chức năng; lỗi analytics không được làm hỏng website.

## Chính sách nguồn
Nội dung nhân vật chỉ dùng các nhóm nguồn được phép. Khi dữ liệu không đủ hoặc nguồn khác nhau, hệ thống trả lời rõ “Chưa đủ nguồn để khẳng định” hoặc gắn nhãn tranh luận/mô phỏng.
