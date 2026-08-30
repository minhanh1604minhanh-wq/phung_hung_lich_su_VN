# Bảo tàng Lịch sử Tương tác — Phùng Hưng

Website song ngữ VI/EN kế thừa template bảo tàng giấy cổ v5.8.5.

## Local
```bash
npm install
npm run validate
npm start
```
Mở `http://localhost:3000`; kiểm tra sức khỏe tại `GET /health`.

## Environment Variables
- `OPENAI_API_KEY`: khóa OpenAI phía server.
- `OPENAI_TEXT_MODEL`: mặc định `gpt-5-mini`.
- `OPENAI_TTS_MODEL`: để trống để ứng dụng dùng cấu hình tương thích; có thể đặt model TTS được tài khoản hỗ trợ.
- `ANALYTICS_API_URL`: mặc định `https://quan-ly-sigma.vercel.app`.
- `ANALYTICS_INGEST_KEY`: khóa ingest dùng chung với Analytics Manager, chỉ đặt ở backend.
- `PORT`: mặc định 3000.

## Vercel
Đẩy project lên GitHub → Import Project trên Vercel → nhập các Environment Variables ở trên → Deploy. Không cần sửa source code.

## Analytics
Browser → backend website nhân vật (`POST /analytics-event`) → Analytics Manager (`/api/events`) → Supabase. Analytics lỗi không làm gián đoạn chức năng học tập.

## Health
`GET /health` trả JSON gồm `ok`, `character`, `aiReady`, `analyticsReady`.

## Assets
- `public/assets/phung-hung.glb`
- `public/assets/phung-hung-vi.mp3`
- `public/assets/phung-hung-en.mp3`
- `public/data/phung-hung.json`
