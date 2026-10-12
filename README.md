# Thực hành chuyển CSS truyền thống sang SASS/SCSS

## 1. Nội dung thực hiện

- `styles-original.css`: CSS ban đầu trong đề, dùng để đối chiếu.
- `abstracts/_variables.scss`: các biến màu và đổ bóng.
- `abstracts/_mixins.scss`: 2 mixin `button-style` và `box-shadow`.
- `base/_global.scss`: CSS chung cho `body`.
- `layout/_container.scss`: định dạng `.container`.
- `components/_buttons.scss` và `_cards.scss`: thành phần nút, thẻ và ví dụ **nesting**.
- `main.scss`: file đầu vào tập hợp các module.
- `main.css`: CSS để trình duyệt sử dụng.
- `index.html`: trang minh họa kết quả.

Dùng **`@use`** thay cho `@import` cũ vì Dart Sass đã deprecate `@import`. Từng partial chủ động khai báo module cần dùng.

## 2. Cách chạy trên Windows (PowerShell)

Nếu SASS đã được cài ở bài trước:

```powershell
sass.cmd -v
sass.cmd main.scss main.css
```

Mở `index.html` bằng Chrome hoặc Live Server.

## 3. Thực hành tự động biên dịch

```powershell
sass.cmd main.scss main.css --watch
```

Sửa biến `$primary-color` trong `abstracts/_variables.scss`, lưu file, kiểm tra `main.css` thay đổi. Nhấn `Ctrl + C` để dừng watch.

**Chú ý:** Không biên dịch trực tiếp các file bắt đầu bằng dấu `_` (partials). Chỉ biên dịch `main.scss`.

## 4. Các kỹ thuật đáp ứng đề

- **Variables:** `$primary-color`, `$text-color`, `$border-color`, `$box-shadow`.
- **Mixins:** `@include mixins.button-style(...)`, `@include mixins.box-shadow`.
- **Nesting:** `&:hover` trong `.button`, `h2` và `p` bên trong `.card`.
- **Partials:** `abstracts/`, `base/`, `layout/`, `components/`.
- **Module system:** `@use` để nhập đúng phạm vi thay vì `@import` cũ.

## 5. Nộp bài

Đẩy toàn bộ thư mục lên GitHub, rồi nộp đường dẫn repository tại CodeGym.
