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

Bản sạch của trang danh mục, HTML giữ nguyên như site. Chỉ sửa banner `.category-hero` bằng CSS. Phần mới duy nhất là `<style id="vmx-change">`, dán cuối `woocommerce-archive.css`.

1. Mobile và tablet (≤991px): ảnh banner thành dải riêng ở đầu thẻ, cao 120–168px, căn phải để thấy xích đu, thú nhún và cầu trượt. Tiêu đề và mô tả nằm trên nền vàng trơn. Trước đây ảnh phủ kín khung, chỉ còn khúc giữa ảnh nằm ngay sau chữ.
2. Desktop (≥992px): ảnh chiếm 62% bên phải, căn phải, mép trái mờ dần vào nền vàng. Cột chữ còn 46% (trước là 58%) nên mô tả không còn đè lên xích đu.
3. Từ 992 đến 1199px: thanh 4 tiêu chí xuống 2 hàng (cao 100px) nhưng vẫn neo đáy như khi chỉ có 1 hàng, nên che mất 40px đoạn mô tả (lỗi có sẵn trên site). Bản sửa đưa thanh vào dòng chảy và chia 2×2.

CSS dùng chung selector `.shop-archive .category-hero`, nên dán lên site sẽ áp cho mọi danh mục. Các ảnh banner khác cũng theo bố cục trang trí bên trái, sản phẩm bên phải. Riêng ảnh Đồ chơi vận động (800×500, có viền kem) cần up lại dạng dải 1024×224.

`do-choi-ngoai-troi-mam-non/index.html` là bản build từ `Design UX-UI/brands/viet-my/nguyen-lieu/2026-11-09_banner-ngoai-troi-trang-build/`. Sửa `change.css` rồi chạy `build.py`. Đừng sửa tay.
