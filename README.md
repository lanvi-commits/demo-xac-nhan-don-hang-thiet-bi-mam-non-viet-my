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

Bản sạch của trang danh mục, HTML giữ nguyên như site. Sửa banner `.category-hero` bằng CSS (`<style id="vmx-change">`, dán cuối `woocommerce-archive.css`) và khai ảnh banner làm ảnh đại diện danh mục (mục 5).

1. Mobile và tablet (≤991px): H1 và mô tả nằm trên cùng, trên nền vàng trơn. Ngay bên dưới là dải ảnh riêng, cao theo đúng tỉ lệ ảnh 32:7 (khoảng 83px ở khổ 390px) nên thấy trọn ảnh, không bị cắt; tiếp theo là thanh tiêu chí. Trước đây ảnh phủ kín khung, chỉ còn khúc giữa ảnh nằm ngay sau chữ.
2. Desktop (≥992px): ảnh chiếm 62% bên phải, căn phải, mép trái mờ dần vào nền vàng. Cột chữ còn 52% (trước là 58%): mô tả không còn đè lên xích đu, H1 36px vẫn nằm 1 dòng nên banner giữ 222px và hàng sản phẩm đầu bắt đầu ở 573px (≤600px theo tiêu chí E1 của visual-semantic-seo).
3. Thanh 4 tiêu chí hiện đủ chữ ở mọi khổ (trước bị cắt "…"). Nhãn dài thì xuống 2 dòng. Thanh nằm ngay dưới mô tả, không ghim ở đáy nữa: trước đây ở khổ 992–1199px thanh xuống 2 hàng nhưng vẫn ghim đáy nên che mất 40px mô tả (lỗi có sẵn trên site). 992–1199px chia 2×2; dưới 390px chuyển 1 cột để không nhãn nào vỡ 3 dòng; nút (i) luôn sát mép phải. Ô cuối trên mobile trước lệch 8px do rule `.item:last-child { padding-right: 0 }` của thanh ngang desktop.

4. Mobile và tablet (≤991px): khoảng trắng giữa header và breadcrumb giảm từ 48px xuống 12px. 48px cũ gồm `padding-top: 24px` của `main.shop-archive` cộng `gap: 24px` của `.layout`. Cột `.sidebar` cao 0px vì bộ lọc là ngăn kéo `position: fixed`, nhưng vẫn tạo thêm một khoảng gap. Desktop giữ nguyên 24px vì cột bộ lọc vẫn hiện.

5. Ảnh đại diện danh mục: khai ảnh banner cho `og:image` (kèm width/height/alt/type), `twitter:image`, và thêm `ImageObject` `#primaryimage` vào schema, gắn vào `CollectionPage.image` + `primaryImageOfPage`. Trang live chưa có cả 3. Phần này DEV làm ở Rank Math, không sửa template.

CSS dùng chung selector `.shop-archive .category-hero`, nên dán lên site sẽ áp cho mọi danh mục. Các ảnh banner khác cũng theo bố cục trang trí bên trái, sản phẩm bên phải. Riêng ảnh Đồ chơi vận động (800×500, có viền kem) cần up lại dạng dải 1024×224.

`do-choi-ngoai-troi-mam-non/index.html` là bản build từ `Design UX-UI/brands/viet-my/nguyen-lieu/2026-11-09_banner-ngoai-troi-trang-build/`. Sửa `change.css` rồi chạy `build.py`. Đừng sửa tay.
