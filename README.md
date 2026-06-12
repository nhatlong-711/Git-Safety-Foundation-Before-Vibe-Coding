# Cẩm Nang Tự Học Git Cho Người Mới Bắt Đầu

Chào mừng bạn đến với repo hướng dẫn học Git thực tế. Repo này được xây dựng từng bước để giúp bạn nắm vững các khái niệm từ cơ bản đến nâng cao.

## Mục lục
1. [Git Cơ Bản](01-co-ban.md)
2. [Branch và Pull Request](02-branch-pr.md)
3. [Hướng dẫn Conflict bản đặc biệt từ nhánh Feature](03-conflict.md)

## Khóa học này được tài trợ bởi: Cộng đồng mã nguồn mở Git
## Trạng thái dự án: Cả hai nhánh cùng hợp tác

# "Dòng này được sửa bởi Nhánh A"
# "Dòng này được sửa bởi Nhánh B"

# Nhật Ký Thực Hành Git & GitHub

Dự án này ghi lại toàn bộ lộ trình tự học và thực hành Git từ các lệnh cơ bản đến các tình huống nâng cao (Revert, Branching, Pull Request và Merge Conflict).

## Quá trình thực hiện từng bước:
1. **Khởi tạo & Cơ bản:** Khởi tạo cấu trúc kho lưu trữ và thực hiện các commit đầu tiên để quản lý tài liệu hướng dẫn (`01-co-ban.md`).
2. **Quản lý Nhánh & PR:** Tạo nhánh độc lập `feature/branch-guide` để viết tài liệu, đẩy lên GitHub và thực hiện Pull Request đầu tiên vào nhánh `main`.
3. **Thực hành Quay xe (Revert):** Mô phỏng một commit lỗi gây hại lên hệ thống, sau đó sử dụng lệnh `git revert` để đảo ngược thay đổi một cách an toàn mà không làm mất lịch sử commit trước đó.
4. **Kích nổ và Xử lý Merge Conflict:** 
   * Tạo hai nhánh song song từ cùng một gốc là `nhánh-thử-conflict-a` và `nhánh-thử-conflict-b`.
   * Cho cả hai nhánh cùng chỉnh sửa tại một dòng cuối của file `README.md` với nội dung khác nhau.
   * Tiến hành hợp nhất (merge) lần lượt hai nhánh vào `main` tại local để kích hoạt tình huống `Merge Conflict`.
   * Sử dụng VS Code để dọn dẹp các ký tự phân tách (`<<<<<<<`, `=======`, `>>>>>>>`), đồng thuận giữ lại nội dung hòa giải và commit kết quả sạch sẽ lên GitHub.

Danh sách lệnh Git đã sử dụng trong suốt quá trình
Dưới đây là các lệnh Git cốt lõi đã được áp dụng thực tế để xây dựng và quản lý repo này:

git init: Khởi tạo một Git repository mới tại local.

git status: Kiểm tra trạng thái của các file (Untracked, Modified, Staged).

git add <tên_file>: Đưa file vào khu vực chuẩn bị (Staging Area).

git commit -m "thông_điệp": Ghi lại ảnh chụp lịch sử mã nguồn kèm tin nhắn có ý nghĩa.

git checkout -b <tên_nhánh>: Tạo một nhánh mới và chuyển ngay sang nhánh đó.

git checkout <tên_nhánh>: Chuyển đổi qua lại giữa các nhánh hiện có.

git merge <tên_nhánh>: Hợp nhất lịch sử và thay đổi từ nhánh chỉ định vào nhánh hiện tại.

git revert <mã_hash_commit>: Tạo ra một commit mới để đảo ngược lại các thay đổi của một commit lỗi trước đó.

git remote add origin <url_repo>: Kết nối kho lưu trữ ở local với kho lưu trữ từ xa trên GitHub.

git pull origin <tên_nhánh>: Cập nhật và kéo mã nguồn mới nhất từ GitHub về máy.

git push origin <tên_nhánh>: Đẩy toàn bộ các commit mới từ local lên GitHub.

git log --oneline --graph --all: Hiển thị toàn bộ lịch sử commit dưới dạng đồ thị trực quan để kiểm tra các vết rẽ nhánh và xử lý xung đột.

## Pull Request minh chứng
Hệ thống đã thực hiện và ghi nhận các Pull Request thực tế sau:

Pull Request #1: Đóng góp file hướng dẫn từ nhánh feature/branch-guide vào main.

Pull Request #2: Hợp nhất thành công nhánh feature/conflict-test vào main.

Pull Request #3: Hợp nhất nhánh feature/real-conflict vào main.