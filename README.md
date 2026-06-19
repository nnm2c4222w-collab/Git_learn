# Git_learn
# Kiến Thức Cốt Lõi Về Git & GitHub (Alex The Analyst Series)

Tài liệu này tóm tắt toàn bộ quy trình làm việc, các khái niệm căn bản và hệ thống câu lệnh thông dụng được hướng dẫn trong loạt bài học Git và GitHub nhằm quản lý dự án hiệu quả.

---

## 1. Phân Biệt Git và GitHub

*   **Git:** Công cụ quản lý phiên bản (Version Control System - VCS) chạy trực tiếp dưới máy tính cục bộ (Local). Giúp chụp ảnh (Snapshot), ghi nhận lịch sử và theo dõi tiến độ chỉnh sửa code.
*   **GitHub:** Nền tảng dịch vụ lưu trữ đám mây (Cloud). Đóng vai trò như một không gian lưu trữ và chia sẻ các kho lưu trữ từ máy cá nhân lên Internet, hỗ trợ làm việc nhóm và xây dựng Portfolio.

---

## 2. Các Khái Niệm Quan Trọng

*   **Repository (Repo / Kho lưu trữ):** Một thư mục dự án được quản lý hoàn toàn bằng Git. Gồm hai loại chính:
    *   *Public:* Ai cũng có thể xem và tải mã nguồn về.
    *   *Private:* Chỉ chủ sở hữu hoặc những người được phân quyền mới có thể truy cập.
*   **Snapshot (Bức ảnh chụp nhanh):** Trạng thái toàn bộ các tệp tin trong dự án được đóng gói và lưu giữ tại một thời điểm cụ thể sau mỗi lệnh Commit.
*   **Commit Hash (SHA-1 ID):** Chuỗi ký tự dài đóng vai trò là định danh duy nhất (ID) của mỗi commit, dùng để đối chiếu lịch sử hoặc khôi phục phiên bản cũ.

---

## 3. Bản Đồ Quy Trình Quản Lý Tệp Tin (File Workflow)

Một tệp tin khi làm việc với Git sẽ trải qua 3 khu vực lưu trữ chính:
1.  **Working Directory:** Thư mục làm việc thực tế, nơi bạn trực tiếp chỉnh sửa hoặc tạo tệp mới.
2.  **Staging Area:** Khu vực đệm/hàng chờ, nơi tập hợp các thay đổi đã sẵn sàng để chuẩn bị ghi nhận.
3.  **Local Repository (.git folder):** Kho lưu trữ chính thức trên máy sau khi đã đóng gói thành công.
4.  **Remote Repository:**  Kho lưu trữ chính thức trên đám mây (Internet).

---

## 4. Tổng Hợp Các Lệnh Git Cơ Bản

### Khởi tạo & Kiểm tra vị trí
*   `pwd` (Print Working Directory): Hiển thị đường dẫn thư mục hiện tại đang đứng.
*   `ls` (List): Liệt kê tệp tin thông thường. 
*   `ls -a`: Liệt kê tất cả các tệp, bao gồm cả thư mục ẩn `.git`.
*   `git init`: Khởi tạo một kho lưu trữ Git mới ngay tại thư mục hiện hành.

### Theo dõi & Lưu trữ tiến độ
*   `git status`: Kiểm tra trạng thái hiện tại của kho lưu trữ (tệp nào chưa theo dõi, tệp nào đã sửa đổi).
*   `git add <tên_file>`: Đưa một tệp cụ thể vào Staging Area.
*   `git add .`: Gom tất cả các thay đổi vào Staging Area.
*   `git commit -m "Lời nhắn"`: Ghi nhận cột mốc lịch sử kèm nội dung mô tả ngắn gọn.
*   `git log`: Xem lại cuốn album lịch sử tất cả các commit cũ trong dự án.
*   `git log --oneline`: Rút gọn danh sách hiển thị commit thành từng dòng đơn giản.

### Di chuyển & Khôi phục phiên bản
*   `git checkout <mã_hash_commit>`: Di chuyển thư mục làm việc quay lại một thời điểm trong quá khứ.
*   `git checkout <tên_nhánh>`: Đổi không gian làm việc sang nhánh được chỉ định.
*   `git checkout -b <tên_nhánh_mới>`: Tạo nhanh một nhánh mới từ vị trí hiện tại và nhảy sang nhánh đó luôn.

### Phân nhánh & Gộp mã nguồn (Branching & Merging)
*   **Tạo nhánh dựa trên mốc cụ thể:** `git checkout -b <tên_nhánh> <mã_hash>`
*   **Gộp nhánh:** 
    1. Quay về nhánh chính nhận mã nguồn: `git checkout master` (hoặc `main`).
    2. Chạy lệnh gộp: `git merge <tên_nhánh_phụ>`.
