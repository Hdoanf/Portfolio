# CV LaTeX — Hà Văn Đoàn

File duy nhất: `cv.tex`. Không dùng class ngoài (`moderncv`, `altacv`…) nên không phải tải template gì thêm, mọi thứ định nghĩa ngay trong file.

## Dùng trên Overleaf

1. Vào [overleaf.com](https://www.overleaf.com) → **New Project** → **Blank Project**, đặt tên gì cũng được.
2. Xoá file `main.tex` mà Overleaf tạo sẵn.
3. Bấm **Upload** (icon mũi tên lên, góc trên trái) → chọn `cv.tex`.
4. **Quan trọng:** bấm **Menu** (góc trên trái) → mục **Compiler** → đổi từ `pdfLaTeX` sang **`XeLaTeX`** → đóng menu.
5. Bấm **Recompile**.

Không cần upload gì thêm — mọi gói và font đều có sẵn trên Overleaf.

### Bắt buộc: XeLaTeX, không phải pdfLaTeX

Đây là bước dễ quên nhất. pdfLaTeX sẽ làm hỏng dấu tiếng Việt.

File đã có sẵn guard: nếu quên đổi compiler, Overleaf sẽ dừng và báo lỗi nhắc đổi engine, chứ không xuất ra PDF sai dấu. Thấy lỗi đó thì quay lại bước 4.

## Nếu muốn build tại máy thay vì Overleaf

Máy bạn hiện chưa cài TeX. Cách nhẹ nhất:

```bash
winget install TectonicProject.tectonic
```

Mở terminal mới rồi chạy — Tectonic mặc định đã dùng XeTeX nên không phải khai báo gì:

```bash
tectonic D:/Downloads/portfolio/cv/cv.tex
```

## Font

Dùng **TeX Gyre Heros** (bản clone của Helvetica), có sẵn trên Overleaf và trong mọi bản TeX Live / MiKTeX / Tectonic, hỗ trợ đầy đủ dấu tiếng Việt — không cần upload hay cài font.

Muốn CV kiểu chữ có chân, sửa một dòng trong phần `\setmainfont`:

```
texgyreheros  →  texgyretermes
```

Icon dùng `fontawesome5` — Overleaf có sẵn. Nếu bản TeX nào thiếu gói này, file vẫn biên dịch bình thường, chỉ là không có icon (đã xử lý bằng `\IfFileExists`).

## Chỗ cần bạn điền

Tìm chữ `BO SUNG` trong `cv.tex`, có 3 chỗ:

1. **Số điện thoại và địa chỉ** — ở phần header, đang bị comment. Bỏ dấu `%` đầu dòng và điền vào.
2. **Kinh nghiệm** — `[Tên công ty]` và `[MM/2026 -- MM/2026]` của kỳ thực tập Smart Home IoT.
3. **Học vấn** — `[Ngành học]`, `[Tên trường]`, `[2022 -- 2026]`, và GPA nếu muốn khoe.

Ngoài ra: mục Học vấn theo thông lệ CV Việt Nam thường đặt **trên** mục Kinh nghiệm với sinh viên mới ra trường. Bản hiện tại đặt xuống cuối vì thế mạnh của bạn là dự án. Muốn đổi thì cắt nguyên khối `\section{Học vấn}` lên trên `\section{Kinh nghiệm}`.

## Độ dài

Hiện khoảng 2 trang. Muốn ép về 1 trang thì bỏ bớt 2 dự án cuối (`chimmusicplayer` và `Hệ thống quản lý tài sản`), hoặc giảm `top`/`bottom` trong dòng `\usepackage[...]{geometry}`.

## Nội dung lấy từ đâu

Cùng nguồn với portfolio: README, cây file và `pubspec.yaml` / `requirements.txt` của các repo trên `github.com/Hdoanf`. Không có mục nào là bịa — trừ các placeholder trong ngoặc vuông ở trên.
