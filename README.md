# AI QuizMaster - Nền tảng Tạo đề AI & Thi Trực Tuyến (Phiên bản Nâng Cấp Quản Trị & Phân Tách Học Sinh)

Ứng dụng trắc nghiệm trực tuyến phong cách **Quizizz / Kahoot** tích hợp tạo đề thông minh bám sát **từng Bài học** và **từng Chương** cho môn **Công nghệ (10, 11, 12)** cùng đầy đủ các môn học phổ thông.

---

## 🔐 1. Phân tách Trang Giáo Viên (Đăng nhập/Đăng ký) & Đường Link Học Sinh

### A. Cổng Giáo Viên & Quản Trị Viên (`index.html`)
- Trang tạo đề và tổ chức thi được bảo vệ bằng **Tên đăng nhập (Username)** và **Mật khẩu (Password)**.
- **Tài khoản mặc định tích hợp sẵn**:
  - 👑 **Tài khoản Admin**: Tên đăng nhập: `admin` | Mật khẩu: `admin123`
  - 🎓 **Tài khoản Giáo viên mẫu**: Tên đăng nhập: `giaovien` | Mật khẩu: `123456`
- **Đăng ký tài khoản mới**: Giáo viên có thể tự đăng ký tài khoản tại tab **Đăng ký tài khoản mới**.
- **Quản lý Tài khoản (Dành riêng cho Admin)**:
  - Khi đăng nhập bằng tài khoản `admin`, trên thanh công cụ sẽ xuất hiện mục **👥 Quản lý Tài khoản (ADMIN)**.
  - Admin có thể: Thêm tài khoản giáo viên mới, Phê duyệt / Khóa / Mở khóa tài khoản, Cấp quyền Admin, Đặt lại mật khẩu, Bật/tắt chế độ tự động duyệt đăng ký và Xuất/Nhập danh sách tài khoản (JSON) hoặc đồng bộ qua Firebase.

### B. Đường Link Độc Lập Gửi Cho Học Sinh Vào Phòng Thi
- Khi Giáo viên mở phòng thi với **Mã PIN 6 số** (ví dụ `839214`), hệ thống tự động tạo đường link riêng cho học sinh:
  - Cách 1 (Qua tham số link): `https://<tên-github>.github.io/<tên-repo>/?mode=student&pin=839214`
  - Cách 2 (Qua trang học sinh riêng): `https://<tên-github>.github.io/<tên-repo>/student.html?pin=839214`
- Khi học sinh nhấn vào đường link này:
  - **Ẩn hoàn toàn** giao diện tạo đề, cài đặt và quản lý tài khoản của giáo viên.
  - **Tự động điền sẵn Mã PIN phòng thi**, học sinh chỉ cần nhập Tên (Nickname), chọn Linh vật và nhấn **Vào phòng thi ngay**.

---

## 🎯 2. Tạo Câu Hỏi Chính Xác Theo Từng Bài Học / Theo Từng Chương (Môn Công Nghệ & Các Môn Khác)

Hệ thống đã được nâng cấp bộ khóa phạm vi kiến thức 3 cấp độ cho **tất cả các môn học** (Công nghệ, Hóa học, Vật lý, Sinh học, Toán học, Lịch sử, Địa lý, Tiếng Anh, Tin học, Ngữ văn, Kiến thức chung):
1. **📘 Theo Bài học cụ thể**: Chọn Chương -> Chọn Bài học. Toàn bộ câu hỏi sinh ra (cả khi dùng Gemini AI lẫn bộ sinh đề thông minh tích hợp sẵn) **chỉ lấy duy nhất kiến thức của Bài học đó**, tuyệt đối không lấy lẫn câu hỏi từ các bài khác trong SGK.
2. **📂 Theo Chương**: Chọn Chương cần kiểm tra ôn tập. Câu hỏi được lấy rải đều từ tất cả các bài học **nằm trong Chương đó**, không lấy sang chương khác.
3. **📚 Cả Khối lớp**: Tổng hợp kiến thức toàn bộ các chương trong năm học để ôn thi học kì / cuối năm.
4. **Nạp file `.md` / `.txt` tùy chỉnh**: Giáo viên dạy bất kỳ môn nào có thể tải lên file đề cương `.md` hoặc `.txt`, hệ thống sẽ tự động nhận diện Chương và Bài học.

---

## 🚀 3. Hướng Dẫn Đưa Lên GitHub Pages
1. Tải toàn bộ các file trong gói dự án (`index.html`, `student.html`, 3 file `.md` SGK, `sample_quizzes.json`, `README.md`) lên kho lưu trữ (Repository) trên GitHub.
2. Vào **Settings** -> **Pages** -> Chọn nhánh `main` / thư mục `/(root)` -> Nhấn **Save**.
