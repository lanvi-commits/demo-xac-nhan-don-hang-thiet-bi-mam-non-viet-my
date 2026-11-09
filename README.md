# Demo trang Xác nhận đặt hàng — Thiết bị mầm non Việt Mỹ

Trang Xác nhận đặt hàng (`/checkout/order-received/`) của site đang dựng (website-demo-02.thcmedia.vn) sau khi áp feedback dòng 232–237 tab "Review tổng thể website". Bản sạch, chỉ giao diện: header, thanh tiến trình, footer, thanh liên hệ nổi giữ nguyên như site.

1. H1 "Đặt hàng thành công · Đơn #…", dưới H1 có giờ đặt, phương thức thanh toán, nút "Chép mã đơn"; breadcrumb + tiêu đề tab đổi theo (dòng 236)
2. Thẻ "Đơn hàng của bạn": sản phẩm × số lượng × mẫu mã × ghi chú, Tiền hàng · Vận chuyển & lắp đặt · Tạm tính, người nhận, địa chỉ giao (dòng 237)
3. Lưu ý VAT: ý "nhân viên gọi tư vấn VAT, phí vận chuyển & lắp đặt" lên mô tả dưới H1 + bước 1; dưới Tạm tính 1 dòng "Chưa gồm VAT 10%, phí vận chuyển & lắp đặt", bỏ hộp vàng (dòng 233)
4. Đơn chuyển khoản: khối "chưa cần chuyển lúc này", không in số tài khoản (theo Chính sách thanh toán)
5. Các bước tiếp theo có mốc thời gian, lấy từ Chính sách giao hàng (dòng 237)
6. "Có thể bạn cũng cần" đặt sau khối đơn, link thẻ SP mở bằng JS (Brief dòng 35)
7. Bỏ dòng "Bạn có mã ưu đãi?…" (dòng 232) và câu "Trả tiền mặt khi giao hàng." cuối trang (dòng 234)
8. Không tìm thấy đơn: thanh tiến trình xám, H1 "Không tìm thấy đơn hàng", nút Về giỏ hàng + gọi hotline (dòng 236)

Hotline giữ 0902 333 196 (24/7), chờ SEO xác nhận số (dòng 235). Đơn #10521 và người đặt là dữ liệu mẫu; sản phẩm và giá là sản phẩm thật trên site (23/10/2026).

- Xem trực tiếp: https://lanvi-commits.github.io/demo-xac-nhan-don-hang-thiet-bi-mam-non-viet-my/
- Đơn chuyển khoản: https://lanvi-commits.github.io/demo-xac-nhan-don-hang-thiet-bi-mam-non-viet-my/?thanh-toan=chuyen-khoan
- Không tìm thấy đơn: https://lanvi-commits.github.io/demo-xac-nhan-don-hang-thiet-bi-mam-non-viet-my/?don=khong-tim-thay

Phần mới chỉ gồm `<div class="order-received-content">`, `<style id="vmx-change">` (dán cuối `woocommerce-checkout.css`) và `<script id="vmx-page-js">`. `<script id="vmx-demo-state">` (đổi trạng thái theo URL) và `<script id="vmx-demo-guard">` (form popup tư vấn không gửi đi đâu) chỉ dành cho demo, không đưa lên site. Trang mẫu, có `noindex`.

`index.html` là bản build từ `Design UX-UI/brands/viet-my/nguyen-lieu/2026-10-23_xac-nhan-don-hang-trang-build/` (sửa `section.html` / `change.css` / `page.js` → chạy `build.py` → commit + push). Đừng sửa tay `index.html`.

---

## Trang phụ: banner danh mục Đồ chơi ngoài trời mầm non (09/11/2026)

- Xem trực tiếp: https://lanvi-commits.github.io/demo-xac-nhan-don-hang-thiet-bi-mam-non-viet-my/do-choi-ngoai-troi-mam-non/
- Trang thật: https://website-demo-02.thcmedia.vn/do-choi-ngoai-troi-mam-non/

Bản sạch của trang danh mục, HTML giữ nguyên như site. Sửa banner `.category-hero` bằng CSS (`<style id="vmx-change">`, dán cuối `woocommerce-archive.css`) khai ảnh banner làm ảnh đại diện danh mục (mục 5), bọc ảnh banner bằng `<picture>` và cho 4 ảnh thẻ đầu tải ngay (mục 6).

1. Mobile và tablet (≤991px): **bỏ ảnh banner**, chỉ còn H1, mô tả và thanh tiêu chí trên nền vàng. Theo tiêu chí E1 của visual-semantic-seo: trang danh mục không dùng banner hero, ảnh đại diện đi qua `og:image` + `CollectionPage.image` (mục 5). Lưới sản phẩm lên cao: thẻ đầu ở 648px (390×844), toolbar Bộ lọc nằm trong màn hình đầu kể cả ở 375×667. Ảnh **không bị tải** trên mobile (xem mục 6).
2. Desktop (≥992px): ảnh chiếm 62% bên phải, căn phải, mép trái mờ dần vào nền vàng. Cột chữ còn 52% (trước là 58%): mô tả không còn đè lên xích đu, H1 36px vẫn nằm 1 dòng nên banner giữ 222px và hàng sản phẩm đầu bắt đầu ở 573px (≤600px theo tiêu chí E1 của visual-semantic-seo).
3. Thanh 4 tiêu chí hiện đủ chữ ở mọi khổ (trước bị cắt "…"):
   - Desktop: nhãn đầy đủ, nhãn dài xuống 2 dòng. Thanh nằm ngay dưới mô tả, không ghim ở đáy nữa (trước ở khổ 992–1199px thanh 2 hàng che mất 40px mô tả, lỗi có sẵn trên site). Khổ 992–1199px chia 2×2.
   - Điện thoại (≤767px): 2×2, **nhãn ngắn 1 dòng**: "Chính hãng 100%" · "An toàn cho trẻ" · "Báo giá dự án" · "Đủ hóa đơn VAT". Khối cao 92px (trước 120px), thẻ SP đầu lên 620px ở 390×844. Nhãn đầy đủ vẫn nằm trong `aria-label` của nút và trong tooltip. HTML mới: `<span class="label-full">` + `<span class="label-short">` trong `.label`. DEV thêm trường "Nhãn ngắn (mobile)" cho mỗi tiêu chí.
   - Mobile và tablet (≤991px): **chạm vào cả ô để mở tooltip**. Vùng bấm của nút (i) phủ kín ô (`::before`), ô cao ≥44px; trước đây nút chỉ 12×12px. JS tooltip của theme giữ nguyên. Dưới 390px ẩn hình (i) để 2×2 vẫn vừa 1 dòng.
   - Ô cuối trên mobile trước hụt 8px lề phải do rule `.item:last-child { padding-right: 0 }` của thanh ngang desktop.
   - Cần bên SEO hoặc khách xác nhận: nhãn đầy đủ "Giá tốt nhất thị trường" và "An toàn tuyệt đối" là từ ngữ tuyệt đối (Luật Quảng cáo 2012 Điều 8 cấm "nhất", "tốt nhất" khi không có tài liệu chứng minh). Nhãn ngắn trên điện thoại đã tránh.

4. Mobile và tablet (≤991px): khoảng trắng giữa header và breadcrumb giảm từ 48px xuống 12px. 48px cũ gồm `padding-top: 24px` của `main.shop-archive` cộng `gap: 24px` của `.layout`. Cột `.sidebar` cao 0px vì bộ lọc là ngăn kéo `position: fixed`, nhưng vẫn tạo thêm một khoảng gap. Desktop giữ nguyên 24px vì cột bộ lọc vẫn hiện.

5. Ảnh đại diện danh mục: khai ảnh banner cho `og:image` (kèm width/height/alt/type), `twitter:image`, và thêm `ImageObject` `#primaryimage` vào schema, gắn vào `CollectionPage.image` + `primaryImageOfPage`. Trang live chưa có cả 3. Phần này DEV làm ở Rank Math, không sửa template.

6. Ảnh và LCP:
   - Ảnh banner bọc `<picture>`, có `<source media="(max-width: 991.98px)" srcset="(ảnh GIF rỗng 1×1)">`. Chỉ ẩn bằng `display:none` thì mobile vẫn tải ảnh, lại với `fetchpriority="high"`, giành băng thông với phần tử LCP thật. Desktop vẫn dùng `srcset` cũ của `<img>`.
   - 4 ảnh thẻ sản phẩm đầu (hàng đầu desktop, 2 hàng đầu mobile) đổi `loading="lazy"` thành `loading="eager"` và bỏ `auto, ` trong `sizes` (chỉ hợp lệ với lazy). Ở 390px và 768px ảnh thẻ đầu chính là phần tử LCP. DEV: lọc `wp_get_attachment_image_attributes` theo vị trí trong vòng lặp sản phẩm.
   - Phần tử LCP đo được: desktop = ảnh banner; 390×844 và 768×1024 = ảnh thẻ sản phẩm đầu; 375×667 = H1. Tất cả đều nằm trong màn hình đầu.

CSS dùng chung selector `.shop-archive .category-hero`, nên dán lên site sẽ áp cho mọi danh mục. Các ảnh banner khác cũng theo bố cục trang trí bên trái, sản phẩm bên phải. Riêng ảnh Đồ chơi vận động (800×500, có viền kem) cần up lại dạng dải 1024×224.

`do-choi-ngoai-troi-mam-non/index.html` là bản build từ `Design UX-UI/brands/viet-my/nguyen-lieu/2026-11-09_banner-ngoai-troi-trang-build/`. Sửa `change.css` rồi chạy `build.py`. Đừng sửa tay.
