# Figma 5 — Figma → HTML/CSS

Cắt tay từ Figma sang HTML semantic và **CSS thuần**. Không framework, không
bước build, **không JavaScript**.

**Live:** _điền URL_ · **Source:** _điền URL_ · **Thiết kế:** _điền link Figma_

## Độ khớp với bản thiết kế

| Trang | Khung Figma | Sai lệch màu TB (/765) | Pixel lệch ≤ 30 | Ghi chú |
| --- | --- | --- | --- | --- |
| Landing page — Desktop | 1440 × 5406 | 3.5 | 98.1 % | 28/34 vùng khớp 0px, còn lại lệch 1px ở mép nét chữ |
| Landing page — Tablet | 768 × 5186 | 3.4 | 98.1 % | 29/36 vùng khớp 0px, còn lại lệch 1px |
| Landing page — Mobile | 375 × 4572 | 8.6 | 95.6 % | mọi khối lệch ≤ 1px; phần sai lệch còn lại là khác biệt khử răng cưa chữ nhỏ giữa Figma và Chrome |

Cả 3 khung là **một** trang `index.html` responsive. Overlay:
`dev/home-desktop-overlay.html`, `dev/home-tablet-overlay.html`,
`dev/home-mobile-overlay.html`, và trang gộp cả 3 khổ cạnh nhau
`dev/home-all-overlay.html` (viết tay, `regen` không ghi đè).

**Ảnh đối chiếu đã xử lý** (`docs/comparison/home/home-<khổ>-figma.png`):

- Ảnh export là bản 2x (2880 / 1536 / 750 px), đã thu về 1x bằng LANCZOS.
- Bỏ thanh Safari giả (desktop/tablet) và status bar iOS (mobile), 54px trên
  cùng: thay bằng hàng gradient ngay bên dưới.
- Xoá các đường lưới layout Figma (cột mờ dọc trang) bằng nội suy 2 cột kề.

Số đo từng khối: `docs/comparison/home/regions-<khổ>.txt` (chạy bằng
`regions.py`), thông số Figma chép trong `docs/comparison/home/spec.md`.

Ảnh đối chiếu nằm trong `docs/comparison/<trang>/`. Tự kiểm trực tiếp: mở
`dev/<trang>-overlay.html` (bốn chế độ Code only / Overlay 50% / Figma only /
Slider — không JavaScript, nút là radio input đọc bằng `:has()`).

## Không flexbox, không grid

Bố cục dựng bằng kỹ thuật trước thời flexbox: `float` + `calc()`, `flow-root`,
`inline-block` + `font-size: 0`, `line-height` + `vertical-align`,
`position: absolute`.

## Font

| Font Figma | Thay bằng (OFL) | Weight |
| --- | --- | --- |
| DynaPuff (tiêu đề) | dùng đúng font gốc — OFL-1.1 | 600, 700 |
| Manrope (chữ thường) | dùng đúng font gốc — OFL-1.1 | 500, 700 |

Tự lưu `.woff2` (bảng mã latin) trong `assets/fonts/`.

## Chỗ khác bản thiết kế

- **Ảnh theo từng khung**: mỗi khung Figma cắt ảnh khác nhau, nên ảnh thẻ lớn,
  3 ảnh Graphics, nền câu trích dẫn, ảnh Save Planet (mobile), 2 elip và Dawn
  (mobile) được cắt từ chính export 2x của khung Tablet/Mobile (`*-tablet@2x`,
  `*-mobile@2x`) và chọn bằng `<picture>` theo breakpoint. Nền câu trích dẫn đã
  xoá chữ (chữ là HTML). Ảnh Graphics tablet/mobile đã gồm hình trang trí.
- **Thẻ 1 và thẻ 4 của dải cuộn** chỉ có ảnh export đã cắt (216px). Phần còn
  thiếu (lộ ra khi cuộn hoặc màn > 1440) được lấp bằng chính ảnh đó phóng to +
  làm mờ. Tiêu đề thẻ 1 trong Figma bị khuất, tạm đặt "Banking Mobile App" `[ƯỚC]`.
- **Nhóm 2 elip** (`orbit.png`): ảnh export bị khung cắt mép phải; đã lật đối
  xứng nửa trái để có hình đầy đủ (cần cho tablet/mobile).
- **Dải thẻ dự án** cuộn ngang được (bàn phím: Tab vào rồi phím mũi tên).
  Ba chấm chỉ trang trí (`aria-hidden`), không bấm được — không JS thì
  không theo dõi được vị trí cuộn.
- **Menu mobile/tablet**: Figma không vẽ trạng thái mở; ngăn thả xuống nền
  tối là `[ƯỚC]`.
- Link: logo/nav/thẻ trỏ về các mục trong trang, CTA là `mailto:` tạm.

## Responsive

Breakpoint: `< 48rem` mobile (khung 375), `48rem` tablet (khung 768),
`64rem` laptop (bố cục desktop, container co giãn), `≥ 1440` container 1060
canh giữa, trang trí định vị theo tâm khung.

Đã kiểm 320, 360, 375, 390, 414, 568, 667, 768, 820, 1024, 1280, 1366, 1440,
1536, 1680, 1920, 2560 và điện thoại xoay ngang (568/667/844 × 320):
không khổ nào cuộn ngang, không có cảnh báo. Dưới 375 chữ tiêu đề co bằng
`clamp()` (max = số Figma).
Khổ giữa các khung Figma (`[ƯỚC]`): từ 30rem (480) Graphics xếp như tablet
(1 ảnh ngang + 2 ảnh cạnh nhau); ảnh thẻ lớn giữ tỉ lệ 311 : 278; câu trích
dẫn lớn dần theo bề ngang; nút CTA canh giữa khi màn rộng hơn khung. Ảnh 320/375 chụp qua iframe vì Chrome headless
có bề ngang cửa sổ tối thiểu ~500px.

## Còn cần từ phía khách

- Ảnh đầy đủ (384 × 448) của thẻ 1 (khối tím) và thẻ 4 (quả cầu) — hiện chỉ có phần 216px.
- Icon dạng SVG hoặc @2x: logo, nav, mạng xã hội, mũi tên, Dawn, các hình
  trang trí (hiện chỉ có 1x — mờ trên màn retina).
- Link thật cho nav, thẻ dự án, mạng xã hội, CTA.
