<div align="center">

# Portfolio CV - Nguyễn Tuấn Anh

Trang portfolio cá nhân giới thiệu hồ sơ, kỹ năng, dự án và thông tin liên hệ của **Nguyễn Tuấn Anh**, định hướng Frontend Developer.

</div>

## Mục lục

- [Giới thiệu](#giới-thiệu)
- [Chức năng](#chức-năng)
- [Công nghệ sử dụng](#công-nghệ-sử-dụng)
- [Yêu cầu môi trường](#yêu-cầu-môi-trường)
- [Cài đặt và chạy thử](#cài-đặt-và-chạy-thử)
- [Chạy bằng Docker](#chạy-bằng-docker)
- [Cấu hình và tùy chỉnh](#cấu-hình-và-tùy-chỉnh)
- [Kiểm tra](#kiểm-tra)
- [Thông tin liên hệ](#thông-tin-liên-hệ)

## Giới thiệu

Đây là website portfolio dạng tĩnh, trình bày thông tin cá nhân theo bố cục một trang. Giao diện được thiết kế theo hướng mobile-first, có thể xem trên điện thoại, máy tính bảng và máy tính. Dự án không cần cơ sở dữ liệu hoặc bước biên dịch.

## Chức năng

- Điều hướng nhanh đến các phần Giới thiệu, Kỹ năng, Dự án và Liên hệ.
- Trình bày hồ sơ, vai trò nghề nghiệp và ảnh đại diện.
- Hiển thị các kỹ năng dưới dạng danh sách.
- Giới thiệu các dự án mẫu bằng bố cục lưới responsive.
- Cung cấp liên kết email và hồ sơ mạng xã hội.
- Hỗ trợ điều hướng bằng bàn phím, trạng thái focus dễ nhận biết và tùy chọn giảm chuyển động của hệ điều hành.

> Các thẻ dự án và liên kết GitHub/LinkedIn hiện là nội dung mẫu; hãy cập nhật URL trước khi xuất bản.

## Công nghệ sử dụng

- **HTML5:** cấu trúc ngữ nghĩa và nội dung trang.
- **CSS3:** giao diện, Flexbox, CSS Grid, responsive và các biến CSS.
- **Nginx (tùy chọn):** phục vụ website tĩnh trong Docker.

Trang hiện không sử dụng JavaScript, framework, thư viện bên ngoài hay trình quản lý gói.

## Yêu cầu môi trường

- Trình duyệt hiện đại như Chrome, Firefox, Edge hoặc Safari.
- Git nếu muốn sao chép dự án từ kho mã nguồn.
- **Tùy chọn để chạy máy chủ cục bộ:** Python 3.
- **Tùy chọn để chạy bằng Docker:** Docker Engine hoặc Docker Desktop đang hoạt động.

## Cài đặt và chạy thử

### Lấy mã nguồn

Nếu dự án đã có trên máy, chuyển đến thư mục dự án. Nếu lấy từ Git, thay `<URL-kho-ma-nguon>` bằng địa chỉ kho thực tế:

```bash
git clone <URL-kho-ma-nguon> CV-main
cd CV-main
```

Không cần cài dependency. Có thể mở `index.html` trực tiếp bằng trình duyệt. Để xem qua máy chủ HTTP cục bộ, chọn hướng dẫn phù hợp với hệ điều hành.

### Windows

Mở PowerShell tại thư mục dự án và chạy:

```powershell
py -3 -m http.server 8000
```

Nếu lệnh `py` không có nhưng đã cài Python, thử:

```powershell
python -m http.server 8000
```

Mở <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

### macOS

Mở Terminal, chuyển đến thư mục dự án rồi chạy:

```bash
python3 -m http.server 8000
```

Mở <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

### Linux

Mở terminal, chuyển đến thư mục dự án rồi chạy:

```bash
python3 -m http.server 8000
```

Mở <http://localhost:8000>. Dừng máy chủ bằng `Ctrl+C`.

## Chạy bằng Docker

Yêu cầu Docker đã được cài đặt và khởi động. Các lệnh bên dưới dùng image Nginx chính thức, mount thư mục dự án ở chế độ chỉ đọc và không cần tạo Dockerfile.

### Windows PowerShell

Chạy tại thư mục dự án:

```powershell
docker run --rm -d --name cv-portfolio -p 8080:80 -v "${PWD}:/usr/share/nginx/html:ro" nginx:alpine
```

### Windows Command Prompt

Chạy tại thư mục dự án:

```cmd
docker run --rm -d --name cv-portfolio -p 8080:80 -v "%cd%:/usr/share/nginx/html:ro" nginx:alpine
```

### macOS và Linux

Chạy tại thư mục dự án:

```bash
docker run --rm -d --name cv-portfolio -p 8080:80 -v "$PWD:/usr/share/nginx/html:ro" nginx:alpine
```

Sau khi container khởi động, mở <http://localhost:8080>. Dừng và xóa container bằng:

```bash
docker stop cv-portfolio
```

Nếu cổng `8080` đang được sử dụng, đổi phần `8080:80` thành một cổng trống khác, ví dụ `8081:80`, rồi mở cổng tương ứng trên trình duyệt.

## Cấu hình và tùy chỉnh

Nội dung chính nằm trong `index.html`:

- Thay tên, chức danh, phần giới thiệu, kỹ năng và nội dung dự án bằng thông tin của bạn.
- Cập nhật email cùng địa chỉ GitHub và LinkedIn trong phần Liên hệ. Thay cả URL `href`, không chỉ phần chữ đang hiển thị.
- Cập nhật tiêu đề trang, mô tả và tác giả trong phần `<head>`.
- Thay ảnh `assets/img/avatar.jpg` bằng ảnh cá nhân. Có thể giữ nguyên tên tệp hoặc sửa đường dẫn trong thuộc tính `src` tương ứng.
- Thay các liên kết `href="#"` trong thẻ dự án bằng URL dự án thật hoặc xóa liên kết nếu chưa có trang đích.

Để thay đổi màu sắc, kiểu chữ, khoảng cách và breakpoint responsive, chỉnh các biến CSS ở đầu `assets/css/styles.css` và các media query tương ứng. Vì đây là website tĩnh, không có tệp `.env` hay cấu hình máy chủ bắt buộc.

## Kiểm tra

Sau khi chạy trang, kiểm tra các điểm sau:

- Trang tải được và ảnh đại diện hiển thị.
- Các mục điều hướng cuộn đến đúng phần.
- Bố cục hiển thị phù hợp ở chiều rộng điện thoại, máy tính bảng và máy tính.
- Email mở đúng ứng dụng email; các liên kết GitHub, LinkedIn và dự án dẫn đến địa chỉ mong muốn.
- Khi chạy bằng Docker, trang truy cập được tại cổng đã ánh xạ, mặc định là `8080`.

## Thông tin liên hệ

Thông tin hiện được khai báo trong phần Liên hệ của `index.html`:

- **Tên hiển thị:** Nguyễn Tuấn Anh
- **Email mẫu:** `an.nguyen@example.com`
- **GitHub mẫu:** `github.com/nguyenvanan`
- **LinkedIn mẫu:** `linkedin.com/in/nguyenvanan`

Hãy thay thông tin mẫu bằng địa chỉ liên hệ chính thức trước khi đưa website lên môi trường công khai.
