# Báo cáo kiểm thử

- **Phiên bản:** v1.0
- **Ngày kiểm thử:** 2026-10-27
- **Phạm vi:** Website portfolio tĩnh (`index.html` và `assets/css/styles.css`).
- **Môi trường:** Microsoft Edge, kiểm tra trang cục bộ tại kích thước desktop 1440 × 1100 và mobile 390 × 844.

## Tóm tắt kết quả

| Tiêu chí | Kết quả | Tóm tắt |
|---|---|---|
| Tính đúng đắn | Đạt có điều kiện | Trang hiển thị đủ các phần; một số liên kết dự án chưa có đích thật. |
| UI/UX | Cần cải thiện | Khi chụp ở viewport mobile 390 × 844, phần giới thiệu bị tràn ngang và bị cắt; cần sửa bố cục mobile. |
| Khả năng vận hành - xử lý lỗi | Đạt có điều kiện | Trang tĩnh tải được cục bộ, nhưng không có cơ chế ghi nhận hay xử lý lỗi phía ứng dụng. |
| Bảo mật | Đạt trong phạm vi kiểm tra | Không thấy mã JavaScript, biểu mẫu, xử lý dữ liệu người dùng hoặc bí mật trong trang; chưa thực hiện kiểm thử bảo mật chuyên sâu. |
| Chất lượng mã nguồn | Đạt có điều kiện | HTML có cấu trúc ngữ nghĩa và CSS tách riêng; chưa có bộ kiểm thử tự động hoặc kiểm tra HTML/CSS. |
| Khả năng triển khai | Đạt có điều kiện | Có thể phục vụ dưới dạng website tĩnh hoặc bằng Docker theo README; chưa xác minh triển khai trên hosting thực tế. |

## 1. Tính đúng đắn

- **Kết quả:** Đạt có điều kiện.
- **Kiểm tra:** Mở trang bằng Microsoft Edge; xác nhận tiêu đề trang, phần Giới thiệu, Kỹ năng, Dự án, Liên hệ và chân trang được trình duyệt nhận diện. Các liên kết điều hướng nội bộ trỏ đến các phần tương ứng.
- **Hạn chế:** Các liên kết “Xem chi tiết” trong thẻ dự án và liên kết GitHub/LinkedIn hiện trỏ đến `#`; nội dung dự án là mẫu, không xác minh được chức năng đích.
- **Minh chứng:** [Ảnh giao diện desktop](screenshots/desktop-home.png), [ảnh mục dự án](screenshots/desktop-projects.png).

## 2. UI/UX

- **Kết quả:** Cần cải thiện.
- **Kiểm tra:** CSS sử dụng cách tiếp cận mobile-first, lưới dự án thích ứng theo breakpoint, trạng thái focus dễ nhận biết và hỗ trợ `prefers-reduced-motion`. Chụp giao diện ở kích thước desktop 1440 × 1100 và mobile 390 × 844.
- **Vấn đề phát hiện:** Ở ảnh mobile, một số dòng phần giới thiệu vượt khỏi mép phải và bị cắt. Cần điều chỉnh chiều rộng/căn chỉnh của nội dung hero để hiển thị trọn vẹn trên màn hình hẹp.
- **Hạn chế:** Ảnh chụp theo kích thước viewport mô phỏng; chưa thay thế cho kiểm tra trên thiết bị thật, trình đọc màn hình hoặc đánh giá tương phản có công cụ.
- **Minh chứng:** [Ảnh desktop](screenshots/desktop-home.png), [ảnh mobile](screenshots/mobile-home.png).

## 3. Khả năng vận hành - xử lý lỗi

- **Kết quả:** Đạt có điều kiện.
- **Kiểm tra:** Trang portfolio là nội dung tĩnh, không cần backend, cơ sở dữ liệu hoặc bước biên dịch. README cung cấp hướng dẫn chạy bằng HTTP server cục bộ và Docker/Nginx.
- **Hạn chế:** Không có mã xử lý lỗi phía ứng dụng, logging, giám sát, kiểm tra sức khỏe hoặc thông báo lỗi. Chưa thực hiện thử nghiệm lỗi mạng, tải tài nguyên thất bại hay container Docker.
- **Minh chứng:** [Ảnh trang hiển thị trong trình duyệt](screenshots/desktop-home.png).

## 4. Bảo mật

- **Kết quả:** Đạt trong phạm vi kiểm tra tĩnh cơ bản; không phải chứng nhận bảo mật.
- **Kiểm tra:** Trang không chứa JavaScript, biểu mẫu, đầu vào người dùng, thông tin xác thực hoặc kết nối backend trong phạm vi mã được kiểm tra. Các ảnh minh họa dự án được nhúng dưới dạng SVG trong trang.
- **Hạn chế:** Chưa chạy quét lỗ hổng, kiểm tra cấu hình bảo mật HTTP/HTTPS, CSP, cấu hình máy chủ hoặc thành phần triển khai. Cần thay thông tin liên hệ mẫu và cấu hình hosting an toàn trước khi công khai.
- **Minh chứng:** [Ảnh trang portfolio](screenshots/desktop-home.png); đối chiếu mã trong `index.html`.

## 5. Chất lượng mã nguồn

- **Kết quả:** Đạt có điều kiện.
- **Kiểm tra:** Nội dung HTML và stylesheet được tách riêng; trang dùng các vùng ngữ nghĩa như `header`, `nav`, `main`, `section`, `article` và `footer`, đồng thời có nhãn thay thế cho ảnh.
- **Hạn chế:** Chưa có bộ kiểm thử tự động, trình định dạng, linter hoặc kiểm tra tuân thủ HTML/CSS được cấu hình; chưa đo độ bao phủ kiểm thử.
- **Minh chứng:** [Ảnh phần dự án](screenshots/desktop-projects.png); đối chiếu cấu trúc trong `index.html` và `assets/css/styles.css`.

## 6. Khả năng triển khai

- **Kết quả:** Đạt có điều kiện.
- **Kiểm tra:** Dự án là website tĩnh, có thể mở trực tiếp hoặc phục vụ bằng máy chủ HTTP. README cũng có lệnh Docker chạy Nginx và phục vụ thư mục dự án ở chế độ chỉ đọc.
- **Hạn chế:** Chưa xác minh image Docker, triển khai hosting, tên miền, HTTPS, cache, quy trình CI/CD hoặc môi trường production.
- **Minh chứng:** [Ảnh trang chạy trong trình duyệt](screenshots/desktop-home.png); hướng dẫn triển khai trong `README.md`.

## Danh sách ảnh minh chứng

- [desktop-home.png](screenshots/desktop-home.png) — giao diện trang portfolio ở desktop.
- [desktop-projects.png](screenshots/desktop-projects.png) — giao diện desktop, gồm phần đầu trang và các thẻ dự án đầu tiên.
- [mobile-home.png](screenshots/mobile-home.png) — giao diện trang portfolio ở kích thước mobile.

> Ảnh minh chứng là ảnh chụp trang portfolio thực tế trong trình duyệt ở các kích thước viewport nêu trên. Kết quả chỉ phản ánh phạm vi kiểm tra trong báo cáo, không khẳng định đã thực hiện những kiểm thử chưa được liệt kê.
