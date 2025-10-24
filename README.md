# Hướng Dẫn Cài Đặt Nút "Copy" Bài Wiki Trên Backlog

## Mục đích
Script này giúp **sao chép toàn bộ nội dung** của một **trang Wiki trên Backlog thành một trang mới ở cùng cấp thư mục**.
Khi trang gốc đã tồn tại, Backlog sẽ tự động đặt tên trang mới theo quy tắc:
 
 * Nếu tên gốc là **Home**, trang sao chép đầu tiên sẽ là **Home (2)**,
 * Lần sao chép tiếp theo: **Home (3)**, rồi **Home (4)**, v.v.

**Ví dụ**:
 * Trang gốc: **tech/AWS/AWS用語**
 * Trang sao chép đầu tiên: **tech/AWS/AWS用語 (2)**
 * Trang sao chép lần thứ hai: **tech/AWS/AWS用語 (3)**

---

## Yêu cầu trước khi bắt đầu
- Đang dùng **Google Chrome** (hoặc trình duyệt dựa trên Chromium như **Edge**, **Brave**…). Có thể tham khảo hướng dẫn chính thức cài đặt với các trình duyệt khác nhau qua liên kết sau:
    [https://www.tampermonkey.net/index.php](https://www.tampermonkey.net/index.php)
- Có **tài khoản Backlog** và quyền truy cập **API**.

---

## Bước 1: Cài đặt tiện ích Tampermonkey

1. Mở **Google Chrome**.
2. Truy cập liên kết sau:  
   [https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
3. Nhấn **"Add to Chrome"**, sau đó chọn **"Add extension"**.
4. Sau khi cài xong, sẽ thấy biểu tượng **Tampermonkey** (hình con khỉ) ở góc trên bên phải thanh địa chỉ.

---

## Bước 2: Bật quyền chạy script người dùng

> **Lưu ý**: Từ Chrome phiên bản 138 trở lên, **bắt buộc** phải bật quyền này. Hãy làm theo 2 bước bên dưới.

### 1. Qua trang quản lý tiện ích Chrome
  1. Mở trang quản lý tiện ích của Chrome
     * Nhấp vào biểu tượng **ba chấm dọc (⋯)** ở góc trên bên phải trình duyệt.
     * Chọn **Extensions** → sau đó chọn **Manage Extensions**.
  2. Tìm tiện ích **Tampermonkey**
     * Trong danh sách tiện ích hiện ra, tìm mục có tên “**Tampermonkey**”.
     * Đảm bảo tiện ích **đang được bật** (nút chuyển sang **màu xanh da trời**). Nếu chưa bật, hãy nhấp vào nút đó để bật.
  3. Vào chi tiết tiện ích
     * Nhấp vào nút “**Details**” (Chi tiết) bên dưới tên **Tampermonkey**.
  4. Bật tính năng “**Allow User Scripts**”
     * Trong phần “**Extension options**” hoặc gần đầu trang chi tiết, tìm tùy chọn “**Allow User Scripts**”.
     * **Bật công tắc** này (chuyển sang màu xanh).

### 2. Qua trang quản lý tiện ích
  1. Gõ vào thanh địa chỉ:  
  ```
  chrome://extensions/
  ```
  2. Ở góc trên bên phải, bật **"Developer mode"** (Chế độ dành cho nhà phát triển).

---

## Bước 3: Thêm script vào Tampermonkey

1. Nhấp **trái** vào biểu tượng **Tampermonkey** → chọn **"Create a new script"**.
2. Một cửa sổ soạn thảo hiện ra. **Xóa toàn bộ nội dung có sẵn**.
3. Dán toàn bộ nội dung từ file `scripts.js` vào cửa sổ này.
4. Tìm dòng có nội dung:
```
const API_KEY = ''; // Replace with your actual API key
```
5. Thay thế đoạn `''` bằng **API Key** của bạn (xem cách lấy ở phần tiếp theo). Ví dụ:
```
const API_KEY = 'iaCfXKsKns7QPh2TvsU7Ltzjy6WGRy0vlz1NSLV**************';
```
6. Nhấn **Ctrl + S** (Windows) hoặc **Cmd + S** (Mac) để lưu.

> Hoàn tất! Khi truy cập bất kỳ trang Wiki nào trên Backlog, nút "**Copy**" sẽ tự động xuất hiện.

---

# Cách lấy API Key từ Backlog
1. Đăng nhập vào **Backlog**.
2. Nhấp vào **ảnh đại diện** ở góc trên bên phải.
3. Chọn "**Personal Settings**".
4. Trong menu bên trái, chọn "**API**".
5. Nhập bất kỳ ghi chú nào vào ô "**Memo**" (ví dụ: `Script Copy Wiki`).
6. Nhấn "**Submit**".
7. Hệ thống sẽ hiển thị **API Key** — hãy sao chép toàn bộ chuỗi này và dán vào script như hướng dẫn ở Bước 3.

> **Lưu ý quan trọng**: Không chia sẻ **API Key** với bất kỳ ai. 

---

# Nếu gặp sự cố trong quá trình cài đặt:
Nếu nút "**Copy**" không xuất hiện hoặc thực hiện không thành công:
 * Đảm bảo **Tampermonkey đang bật** (nút chuyển sang **màu xanh da trời**). Nếu chưa bật, hãy nhấp vào nút đó để bật thông qua thanh địa chỉ:
   ```
   chrome://extensions/
   ```
   hoặc thực hiện theo từng bước sau:
   * Mở trang quản lý tiện ích của **Chrome**
     * Nhấp vào biểu tượng **ba chấm dọc (⋯)** ở góc trên bên phải trình duyệt.
     * Chọn **Extensions** → sau đó chọn **Manage Extensions**.
   * Tìm tiện ích **Tampermonkey**
     * Trong danh sách tiện ích hiện ra, tìm mục có tên “**Tampermonkey**”.
     * Đảm bảo tiện ích **đang được bật** (nút chuyển sang **màu xanh da trời**). Nếu chưa bật, hãy nhấp vào nút đó để bật.
 * Kiểm tra lại **API Key** đã được điền chính xác chưa.
 * Truy cập trang hỗ trợ chính thức của **Tampermonkey**:
  [https://www.tampermonkey.net/faq.php](https://www.tampermonkey.net/faq.php)

---
