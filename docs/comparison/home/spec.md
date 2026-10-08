# Spec — Landing page (index.html)

Chép từ panel Figma (Dev Mode). Toạ độ tương đối với frame, bỏ thanh Safari/status bar
(thanh Safari giả cao 53px ở desktop/tablet; status bar iOS ở mobile — chỉ là khung trình bày).
Ô trống = không có ảnh chụp thông số.

## Chung

| Thứ | Giá trị |
| --- | --- |
| Font tiêu đề | DynaPuff 700 (Bold), 600 (SemiBold) cho tiêu đề thẻ dự án |
| Font chữ thường | Manrope 500 / 700 |
| Line-height | 100% mọi chữ |
| Letter-spacing | 0% |
| Nền hero | Linear gradient #FFEE32 → #D6D6D6 (Rectangle 1) |
| Nền tối | #202020 (Section 2, footer) |
| Viền vòng trang trí (Group 3) | 1px #737373 |
| Vàng tiêu đề | #FAEB49 |
| Nền thẻ dự án | #FFFEF2, radius 24, padding 24/20 (tablet), gap 10 |
| Ảnh trong thẻ | radius 13, nền #D9D9D9 + gradient đen → đen 0% |
| Tiêu đề thẻ | DynaPuff, màu #565656 |
| Mô tả thẻ | Manrope 700 16 #000 |
| Chấm carousel | Rectangle 14: 33×11 r5.5 #FFEE32; Ellipse 11×11 #FFFEF2; gap 7 |
| Soft Star | #F8841D |
| Butterfly | #F2C94C |
| Asterisk | #2F80ED |
| Ảnh Graphics | radius 40 |
| CTA pill (Frame 29) | viền 1px #F2F2F2 (Gray 6), radius 139, padding 42/137 |
| Dawn (icon CTA) | 108×108, viền 4px #FFF |
| Mũi tên CTA (Group 2) | 55×26, viền 2px #FFF |
| Social icon | 24×24 |
| Copyright | Manrope 500 16 lh100% #FFF, căn giữa, 226×22 |

## Tablet (768)

| Layer | x | y | w | h | Chữ | Màu | Khác |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Rectangle 1 (hero) | 0 | 0 | 768 | 796 | | gradient #FFEE32/#D6D6D6 | |
| Hope (logo) | 33 | 80 | 56 | 56 | | #FFF | |
| header menu item | 680 | 80 | 56 | 56 | | | |
| Hero title | 33 | 315 | 521 | 393 | DynaPuff 700 80/100% | #FFF | |
| Section 2 / Rectangle 2 | 0 | 796 | 768 | 470 | | #202020 | |
| Group 3 (vòng) | 513 | 754 | 551.58 | 552.04 | | | viền 1px #737373 |
| Meet Alex Johnsson | | | 492 | 58 | DynaPuff 700 48/100% | #FAEB49 | |
| Đoạn giới thiệu | | | 524 | 44 | Manrope 500 16/100% | #FFF | |
| Số 39/50/24 | | | 55/59/55 | 58 | DynaPuff 700 48/100% | #FFF | |
| Nhãn số | | | 116 | 22 | Manrope 700 16/100% | #FFF | |
| Section 3 | | 1266 | | | | | |
| Thẻ Banking (Frame 18) | 33 | 1318 | 703 | 680 | | #FFFEF2 | r24, pad 24/20/24/20, gap 10 |
| Ảnh Banking (Frame 17) | | | 663 | 498 | | | r13, pad 20, gap 10 |
| Tiêu đề Banking | | | 663 | 48 | DynaPuff 600 40/100% | #565656 | |
| Mô tả Banking | | | 580 | 44 | Manrope 700 16/100% | #000 | |
| Thẻ nhỏ (Frame 23/24) | | | 424 | 634 | | #FFFEF2 | r24, pad 20, gap 10 (carousel) |
| Ảnh thẻ nhỏ | | | 384 | 448 | | | r13 |
| Tiêu đề thẻ nhỏ | | | 384 | 38 | DynaPuff 700 32/100% | #565656 | |
| Mô tả thẻ nhỏ | | | 364 | 66 | Manrope 500 16/100% | #000 | |
| Chấm carousel (Frame 31) | 350 | 2764 | 69 | 11 | | | gap 7 |
| Graphics Design | 32 | 2938 | 704 | 108 | DynaPuff 700 80/100% | #FFF | |
| Ảnh unsplash | 32 | 3084 | 704 | 414 | | | r40 |
| Soft Star | 271 | 3177 | 227 | 227 | | #F8841D | |
| Rectangle 6 | 32 | 3524 | 336 | 325 | | | r40 |
| Butterfly | 126 | 3611 | 147 | 151 | | #F2C94C | |
| Rectangle 7 | 402 | 3524 | 334 | 325 | | | r40 |
| Asterisk | 477 | 3598 | 183 | 177 | | #2F80ED | |
| Quote | 32 | 4252 | 704 | 232 | DynaPuff 700 48/100% center | #FFF | |
| Section 6 (footer) | 0 | 4778 | 768 | 408 | | | |
| CTA pill (Frame 29) | 32 | 4874 | 714 | 150 | | | r139 viền 1px #F2F2F2 |
| Have a new project? | | | 487 | 58 | DynaPuff 700 48/100% center | #FFF | |
| Frame 28 (link) | | | 249 | 33 | | | gap 24 |
| Book a call now | | | 170 | 33 | Manrope 500 24/100% | #FFF | |
| Copyright | 271 | 5129 | 226 | 22 | Manrope 500 16 | #FFF | |

Ghi chú: toạ độ tablet ở trên tính cả thanh Safari 53px? — Hope top 80 trong khi ảnh export
có thanh Safari phía trên; kiểm lại bằng đo pixel (locate.py).

## Mobile (375)

| Layer | x | y | w | h | Chữ | Màu | Khác |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Section 1 (hero) | 0 | 0 | 375 | 800 | | gradient | gồm status bar iOS |
| Status bar giờ 9:41 | 33.45 | 17.17 | 28.43 | 11.09 | | #000 | khung trình bày |
| Hope (logo) | 17 | 80 | 56 | 56 | | #FFF | |
| header menu item | 303 | 80 | 56 | 56 | | | |
| Hero title | 21 | 465 | 326 | 239 | DynaPuff 700 48/100% | #FFF | |
| Section 2 | 0 | 800 | 604.58 | 466 | | #202020 | |
| Meet Alex Johnsson | | | 342 | 86 | DynaPuff 700 36/100% | #FAEB49 | |
| Đoạn giới thiệu | | | 342 | 60 | Manrope 500 15/100% | #FFF | |
| Group 3 (vòng) | 259.87 | 863 | 344.71 | 345 | | | viền 1px #737373 |
| Số 39/50/24 | | | 42/44/42 | 43 | DynaPuff 700 36/100% | #FFF | |
| Nhãn số (Happy Clients…) | | | 76/74/75 | 44 | Manrope 700 16/100% | #FFF | 2 dòng |
| Section 3 (dải thẻ) | -330 | 1266 | 1390 | 1206 | | | |
| Thẻ Banking | 16 | 1318 | 343 | 488 | | #FFFEF2 | r24, pad 16, gap 10 |
| Ảnh Banking | | | 311 | 278 | | #D9D9D9 + gradient đen | r13, pad 20 |
| Tiêu đề Banking | | | 311 | 76 | DynaPuff 600 32/100% | #565656 | 2 dòng |
| Mô tả Banking | | | 311 | 60 | Manrope 700 15/100% | #000 | |
| Frame 32 (carousel) | -330 | 1861 | 1390 | 518 | | | gap 6, cuộn ngang |
| Thẻ nhỏ (Frame 20) | | | 343 | 518 | | #FFFEF2 | r24, pad 12, gap 10 |
| Ảnh thẻ nhỏ | | | 319 | 363 | | | r13 |
| Tiêu đề thẻ nhỏ | | | 319 | 29 | DynaPuff 700 24/100% | #565656 | |
| Mô tả thẻ nhỏ | | | 319 | 60 | Manrope 500 15/100% | #000 | |
| Frame 31 (chấm) | 154 | 2402 | 69 | 11 | | | gap 7 |
| Graphics Design | 16 | 2530 | 327 | 54 | DynaPuff 700 36/100% | #FFF | |
| Ảnh unsplash | 16 | 2612 | 343 | 325 | | | r40 |
| Soft Star | 102 | 2689 | 172 | 172 | | #F8841D | |
| Rectangle 6 | 16 | 2957 | 343 | 325 | | | r40 |
| Butterfly | 121 | 3051 | 134 | 137 | | #F2C94C | |
| Rectangle 7 | 16 | 3314 | 343 | 325 | | | r40 |
| Asterisk | 114 | 3405 | 148 | 143 | | #2F80ED | |
| Section 5 (quote) | 0 | 3732 | 375 | 498 | | | |
| Quote | 16 | 3912 | 343 | 145 | DynaPuff 700 24/100% center | #FFF | |
| CTA pill (Frame 29) | 17 | 4283 | 342 | 72 | | | r139, viền 1px #F2F2F2 |
| Dawn | | | 52 | 51 | | | viền 4px #FFF |
| Have a new project? | | | 203 | 24 | DynaPuff 700 20/100% | #FFF | |
| Book a call now | | | 107 | 20 | Manrope 500 15/100% | #FFF | |
| Social icon | | | 24 | 24 | | | |
| Copyright | 89 | 4513 | 198 | 19 | Manrope 500 14/100% center | #FFF | |

## Desktop (1440)

Ảnh thông số desktop đã đọc nhưng không còn trong ngữ cảnh khi chép spec — số đo desktop
lấy bằng đo pixel trên ảnh export (`[ĐO]`), màu/font lấy theo bảng "Chung" ở trên.
