# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

**Họ và tên:** [Điền Họ và Tên của bạn]  
**MSSV:** [Điền Mã số sinh viên của bạn]  
**Tên đề tài Website:** Cửa hàng Bán đồ Điện tử Công nghệ (TechStore)  
**Công cụ AI đã sử dụng:** ChatGPT / Claude / Cursor / Gemini  

---

## 1. Yêu cầu ban đầu (System/Initial Prompt)

> *"Bạn là một lập trình viên Front-end chuyên nghiệp. Hãy viết mã nguồn hoàn chỉnh (gồm `index.html` và `style.css`) cho trang web BÁN ĐỒ ĐIỆN TỬ (Cửa hàng công nghệ TechStore) phục vụ bài thi Thiết kế Web.*
>
> **Cấu trúc thư mục dự án và tài nguyên yêu cầu:**
> - `index.html`
> - `style.css`
> - `assets/images/` (chứa `logo.png`, `hero-bg.jpg`, `products/`, `categories/`)
>
> **Các tiêu chuẩn kỹ thuật bắt buộc:**
> 1. **Chuẩn Semantic HTML5 & Accessibility:** Sử dụng triệt để các thẻ ngữ nghĩa chuẩn SEO và Accessibility (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`), hạn chế tối đa việc lạm dụng thẻ `<div>` vô nghĩa.
> 2. **Kỹ thuật CSS & Variables:** Khai báo CSS Custom Properties (`:root`), áp dụng Layout CSS Flexbox & CSS Grid, viết hiệu ứng `:hover`, `:focus` mượt mà cho các card sản phẩm và nút bấm.
> 3. **Tối ưu hóa CSS & Clean Code:** Loại bỏ thuộc tính thừa (dead code), tối ưu Selector ngắn gọn, gộp class dùng chung (`.btn`), và tổ chức cấu trúc CSS theo thứ tự logic: Base → Layout → Components → Utilities.
> 4. **Hiệu ứng & Thư viện:** Tích hợp Animate.css và AOS (Animate On Scroll) qua CDN kèm script khởi tạo `AOS.init()`."*

---

## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iterations)

### Lần 1: Dựng khung Semantic HTML & Cấu trúc CSS Variables

- **Prompt đã dùng:**  
  *"Kiểm tra lại file `index.html` và `style.css`. Thay thế tất cả các thẻ `<div>` bọc danh sách sản phẩm bằng thẻ ngữ nghĩa `<section>` và `<article>`. Đồng thời thiết lập các biến màu sắc, font chữ và khoảng cách trong `:root` (`--color-primary`, `--spacing-md`)."*
- **Kết quả AI tạo ra:**  
  AI đã tái cấu trúc HTML sang dạng Semantic HTML5 hợp lệ và định nghĩa đầy đủ các biến CSS Variables.
- **Nhận xét & Tinh chỉnh của SV:**  
  AI sử dụng một số selector quá dài như `div.container ul li a.link`. Đã nhắc AI rút gọn thành class định danh cụ thể như `.nav-link` và tách class cơ sở `.btn` dùng chung cho `.btn-primary` và `.btn-secondary` để tránh lặp code.

---

### Lần 2: Tự động hóa thư mục Assets & Xử lý lỗi lệnh PowerShell

- **Prompt đã dùng:**  
  *"Tạo script tự động hoặc cung cấp mã nguồn tải hình ảnh sản phẩm mẫu chất lượng cao vào đúng cấu trúc thư mục `assets/images/`."*
- **Thách thức gặp phải:**  
  Trình biên dịch hiển thị cảnh báo bảo mật khi AI chạy lệnh PowerShell tải ảnh (`Allow downloading sample images?`), khiến giao diện bị khựng và không hiển thị nút xác nhận do bị khuất khung hội thoại.
- **Cách sửa prompt (Debug prompt):**  
  *"Không cần chạy lệnh PowerShell tải ảnh tự động nữa. Hãy giữ nguyên đường dẫn chuẩn `assets/images/...` trong thuộc tính `src` của HTML, đồng thời gán link ảnh placeholder trực tiếp từ Unsplash để trang web hiển thị ngay mà không bị lỗi đứt gãy hình ảnh (broken images)."*

---

### Lần 3: Loại bỏ JavaScript tự viết (Custom JS) dư thừa

- **Prompt đã dùng:**  
  *"Hãy kiểm tra lại toàn bộ mã nguồn của trang web và loại bỏ hoàn toàn mọi đoạn mã JavaScript tự viết (custom JS). Đảm bảo mọi hiệu ứng chuyển động, hover, ẩn/hiện menu hay layout responsive đều được xử lý hoàn toàn bằng CSS thuần. Chỉ giữ lại CDN thư viện AOS và câu lệnh khởi tạo AOS.init()."*
- **Kết quả AI tạo ra:**  
  AI đã xóa toàn bộ các đoạn script dư thừa, loại bỏ file `script.js` và tối ưu lại CSS thuần để đảm bảo giao diện hoạt động mượt mà.
- **Nhận xét & Tinh chỉnh của SV:**  
  Mã nguồn trở nên sạch sẽ, tập trung hoàn toàn vào HTML5 & CSS3 đúng với tiêu chí học phần Thiết kế Web.

---

### Lần 4: Tích hợp thư viện AOS/Animate.css & Tổ chức CSS chuẩn Clean Code

- **Prompt đã dùng:**  
  *"Nhúng CDN của Animate.css và AOS.css/AOS.js. Thêm thuộc tính `data-aos="fade-up"` cho các thẻ `<section>`. Sắp xếp lại file `style.css` theo đúng thứ tự: Base → Layout → Components → Utilities và dọn dẹp toàn bộ dead code không dùng đến."*
- **Thách thức gặp phải:**  
  Hiệu ứng cuộn trang AOS không hoạt động khi cuộn chuột xuống dưới.
- **Cách sửa prompt (Debug prompt):**  
  *"Kiểm tra lại vị trí đặt thẻ `<script>` của AOS. Đảm bảo CDN script của AOS được đặt ngay trước thẻ đóng `</body>` và gọi hàm `AOS.init({ duration: 800, once: true });` ngay sau khi tải xong thư viện."*

---

## 3. Đánh giá cá nhân về quá trình Vibe Coding

- **AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?**  
  AI giúp khởi tạo cực kỳ nhanh bộ khung HTML5 chuẩn Semantic, thiết lập lưới sản phẩm bằng CSS Grid linh hoạt, và định nghĩa sẵn hệ thống biến màu sắc (`:root`) chỉ trong vài giây, thay vì phải gõ thủ công từng dòng mã.

- **Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web:**  
  1. Cần chỉ định rõ ràng các tiêu chuẩn kiến trúc ngay từ ban đầu (như chuẩn Semantic HTML, Accessibility, cấu trúc CSS Clean Code Base → Layout → Components → Utilities).
  2. Khi AI sinh code dư thừa (dead code, custom JS không cần thiết) hoặc selector quá sâu, phải trực tiếp nhắc nhở và chỉ đạo AI refactor lại mã nguồn thay vì chấp nhận ngay kết quả đầu tiên.
  3. Cần làm chủ cú pháp và cấu trúc mã nguồn để kịp thời phát hiện các lỗi phát sinh từ thư viện bên ngoài (như AOS chưa gọi hàm khởi tạo hoặc lỗi đường dẫn assets).