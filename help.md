# plantuml

built to vector file

```xml
java -jar $env:PLANTUML_JAR %file%

```

and include them inside latex

```tex
lualatex  -shell-escape -synctex=1 -interaction=nonstopmode -file-line-error -recorder  "d:/Projects/note/academy_docs/tex/c2.project.1.tex
```

Build with VSCode

Ctrl + Shift + P -> Build with recipe -> latexmk (lualatex) (for building report.tex)


- BÌA MÀU XANH NƯỚC BIỂN (KHÔNG SỬ DỤNG BÌA KIẾNG)
- BÌA ĐỆM
- PHIẾU GIAO ĐỀ CƯƠNG THỰC TẬP TỐT NGHIỆP ĐƯỢC PHÊ DUYỆT.
- PHIẾU NHẬN XÉT CỦA ĐƠN VỊ THỰC TẬP
- PHIẾU NHẬN XÉT CỦA GIÁO VIÊN HƯỚNG DẪN

Đánh số trang dạng: i,ii,iii…. Từ Lời cảm ơn đến Danh mục hình vẽ.
- LỜI CẢM ƠN.
- MỤC LỤC.
- DANH MỤC CÁC BẢNG VẼ
- DANH MỤC CÁC HÌNH VẼ
- DANH MỤC CÁC KÝ HIỆU VÀ CHỨ VIẾT TẮT

- MỞ ĐẦU
- CHƯƠNG 1...
- CHƯƠNG 2...
- CHƯƠNG N.
- KẾT LUẬN, KIẾN NGHỊ
- TÀI LIỆU THAM KHẢO
- PHỤ LỤC (NẾU CÓ).

## Problem

messing with custom chapter = no toc produced for some reason.
comment out the placeins package for now


header ChươngA 2. Chương 2. Phân tích và thiết kế hệ thống (\renewcomman{\chaptername}{ChươngA}) fancyhdr set header

chapter: ChươngB 2. Phân tích và thiết kế hệ thống (titlesec \titleformat)
