# Portfolio — Hà Văn Đoàn

Portfolio một trang, viết bằng HTML/CSS/JS thuần. Toàn bộ nằm trong `index.html`, không cần build, không cần cài gì.

## Xem thử

Nháy đúp vào `index.html` là mở được ngay trong trình duyệt.

## Nội dung đã có gì

Nội dung được lấy từ chính các repo trên GitHub `Hdoanf`:

| Phần | Nguồn |
|---|---|
| HealthPulse VN | `doantotnghiep` — Flutter + Firebase + Gemini + ESP32-C3, kèm nút Demo trỏ tới https://hdoanf.github.io/doantotnghiep/ |
| Smart Home IoT | `fontend_HC` — Flutter + Riverpod + MJPEG |
| Chatbot AI Amy | `demo` — FastAPI + LangChain + FAISS |
| App Học Tiếng Trung | `apphoctiengtrung` — Flutter + Firestore + TTS |
| chimmusicplayer | `chimmusicplayer` — TUI viết bằng C |
| Quản lý tài sản & kho | `hdoanf.github` — PHP + MySQL + PHPWord |

Phần thống kê GitHub ở đầu trang tự gọi GitHub API mỗi lần load, nên số repo và số ngôn ngữ luôn mới. Nếu offline hoặc bị rate-limit thì hiện số cố định sẵn trong HTML.

## Định hướng

Portfolio định vị là **Flutter / Mobile Developer** (AI & IoT), không phải full-stack web. Các đồ án PHP/MySQL vẫn được giữ lại nhưng ghi rõ là "mức đồ án" — chúng cho thấy nền tảng dữ liệu/CRUD chứ không phải kỹ năng chính.

Mục Kỹ năng có một card riêng cho **AI Agent & Agentic coding** (Claude Code, Gemini CLI, MCP). Bằng chứng trong repo: `apphoctiengtrung` có `.claude/settings.local.json` và `GEMINI.md`.

Mục Liên hệ chỉ còn tiêu đề + hai nút, không có câu xin việc.

## Theme

Mặc định là **sáng**. Nút mặt trăng góc phải đổi sang tối và ghi nhớ lựa chọn trong `localStorage`.

Trong CSS, `:root` giữ bộ màu sáng, `:root[data-theme="dark"]` ghi đè sang tối. Muốn đổi mặc định về tối thì đảo tên hai selector đó, và đảo hai điều kiện `=== 'dark'` trong đoạn JS theme.

Bộ màu sáng dùng teal đậm `#0a7a63` thay vì teal nhạt của bản tối — teal nhạt trên nền trắng không đủ tương phản để đọc chữ nhỏ. Biến `--on-accent` giữ màu chữ nằm trên nền accent (trắng ở theme sáng, gần đen ở theme tối).

## Cần chỉnh gì

Tất cả trong `index.html`:

- **Email** — đang là `bestbubuom@gmail.com`, tìm chuỗi này để đổi.
- **Pill ở hero** — vẫn còn dòng "Đang tìm cơ hội Mobile Developer". Nếu không muốn lộ đang tìm việc thì xoá thẻ `<span class="pill">` đó đi cho khớp với mục Liên hệ.
- **Thời gian các mốc còn lại trong mục Hành trình** — suy ra từ ngày commit của repo. Riêng mốc thực tập đã được xác nhận là 12/2025 – 04/2026 (Công ty Cổ phần HC-Hiteck), các mốc khác vẫn nên kiểm tra lại.
- **LinkedIn / Facebook** — chưa có link, thêm vào mục Liên hệ.
- **Nút tải CV** — bản LaTeX nằm ở [`cv/cv.tex`](cv/README.md). Sau khi biên dịch ra `cv/cv.pdf` thì thêm một nút `.btn-ghost` trỏ tới file đó vào mục Liên hệ.
- **Ảnh chụp app** — mục Dự án hiện chỉ có chữ. Thẻ HealthPulse đã có nút Demo mở trang giao diện chạy thật (`docs/index.html` trong repo `doantotnghiep`, phục vụ qua GitHub Pages); các dự án còn lại vẫn nên bổ sung screenshot.

## Deploy lên GitHub Pages

Tạo repo mới tên `Hdoanf.github.io` trên GitHub, rồi:

```bash
cd D:/Downloads/portfolio && git init && git add . && git commit -m "portfolio" && git branch -M main && git remote add origin https://github.com/Hdoanf/Hdoanf.github.io.git && git push -u origin main
```

Vài phút sau trang sẽ chạy ở `https://Hdoanf.github.io`.

> Lưu ý: repo hiện có sẵn tên `hdoanf.github` là dự án PHP quản lý tài sản, **không phải** repo GitHub Pages — đừng push portfolio vào đó.

## Cách khác: Netlify / Vercel

Kéo thẳng thư mục `portfolio` vào https://app.netlify.com/drop là xong, không cần git.
