# Figma 5 — Figma → HTML/CSS

Chuyển thiết kế Figma sang HTML semantic + CSS thuần. Không framework, không
bước build, **không một dòng JavaScript nào được gửi xuống trình duyệt**.

Chú thích trong code viết tiếng Việt cho dễ đọc lúc phát triển — chuyển sang
tiếng Anh trước khi bàn giao.

## Quy ước bắt buộc — đọc trước khi sửa bất cứ gì

- **Không flexbox, không grid, không `gap`.** Bố cục dựng bằng `float` +
  `calc()`, `clear`, `flow-root`, `inline-block` + `font-size: 0` ở cha,
  `line-height` + `vertical-align`, `position: absolute`.
- **Không JavaScript** trên trang giao cho khách. Trạng thái mở/đóng dùng
  `:target`, `<details>`, radio/checkbox + `:has()`. `dev/*-overlay.html` là
  công cụ nội bộ (cũng không JS).
- **CSS chia theo cascade layer**, khai báo một lần trong `<head>`:
  `reset, tokens, base, layout, components, utilities`. Không `!important`
  (trừ khối `prefers-reduced-motion`).
- **`css/tokens.css` chỉ chứa giá trị dùng chung** (màu, font, thang độ đậm,
  leading, chuyển động, bo góc). Số đo riêng của component ghi thẳng trong
  file component. Số dùng ở nhiều rule trong cùng component thì làm biến cục
  bộ trên selector gốc (vd. `.card { --card-title-gap: 87px; }`), không đưa lên
  `:root`. Mọi con số đều ghi nhãn nguồn gốc ngay bên cạnh:
  - `[FIGMA]` — đọc thẳng từ panel inspector
  - `[ĐO]` — đo bằng script quét pixel trên ảnh export 1:1
  - `[MẪU]` — lấy từ file asset được cung cấp
  - `[ƯỚC]` — ước lượng, chờ xác nhận lại
- Đặt tên BEM, specificity phẳng, không selector lồng quá một cấp, không dùng
  ID để style.
- **Pixel-perfect**: mỗi trang render đúng khổ khung Figma; đối chiếu bằng
  overlay + script so pixel. Đã chốt số đo thì không đổi.
- Font thương mại → thay bằng font OFL, tự lưu `.woff2` trong `assets/fonts/`
  (không gọi Google Fonts).

## Cấu trúc

```
*.html                   mỗi trang Figma một file
css/
├── reset.css / fonts.css / tokens.css / base.css / layout.css
├── components/          mỗi khối một file BEM
└── utilities.css        .visually-hidden, .skip-link
assets/fonts|icon|img/
dev/pages.json           danh sách trang (nguồn sinh overlay)
dev/*-overlay.html       đè ảnh Figma lên bản code (Code / 50% / Figma / Slider)
                         index.html có 3 overlay: desktop / tablet / mobile
docs/comparison/<slug>/  <slug>-figma.png, -build, -side-by-side, -overlay, -difference
```

## Trạng thái các trang

- **Landing page** (`index.html`): xong 3 khung Desktop 1440 × 5406, Tablet
  768 × 5186, Mobile 375 × 4572. Sai lệch TB 5.6 / 25.3 / 32.4 (/765); khối chữ
  lệch ≤ 1px ở cả 3 khung. Component: `site-header`, `hero`, `about`,
  `projects` (thẻ + dải cuộn), `graphics`, `quote`, `site-footer`.
  Overlay: `dev/home-{desktop,tablet,mobile}-overlay.html`.

## Chạy thử

```bash
npm install     # chỉ để có browser-sync
npm run dev     # http://localhost:3000
```

Không có npm: `python3 -m http.server 3000`.

Đo pixel khổ < 500px: Chrome headless không thu cửa sổ nhỏ hơn ~500px →
chụp qua một trang tạm chứa `<iframe width="375">` rồi cắt.
