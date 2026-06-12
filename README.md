# Nhật Ký Thực Hành Git & GitHub

Dự án này ghi lại toàn bộ lộ trình tự học và thực hành Git từ các lệnh cơ bản đến các tình huống nâng cao (Revert, Branching, Pull Request và Merge Conflict). Đây là minh chứng cho quá trình xây dựng nền tảng quản lý mã nguồn vững chắc, chuẩn bị sẵn sàng cho kỷ nguyên phát triển phần mềm hiện đại.

---

## 1. Nhật Ký Quá Trình Thực Hiện
*   **Giai đoạn 1: Khởi tạo & Cơ bản:** Khởi tạo cấu trúc kho lưu trữ local và thực hiện các commit đầu tiên để quản lý tài liệu hướng dẫn lệnh cốt lõi (`01-co-ban.md`).
*   **Giai đoạn 2: Quản lý Nhánh & PR:** Tạo nhánh độc lập `feature/branch-guide` để viết tài liệu nâng cao, đẩy lên GitHub và thực hiện Pull Request đầu tiên thành công vào nhánh `main`.
*   **Giai đoạn 3: Thực hành Quay xe (Revert):** Mô phỏng một commit lỗi gây hại lên hệ thống, sau đó ứng dụng lệnh `git revert` để đảo ngược thay đổi một cách an toàn mà không làm mất lịch sử định hình trước đó.
*   **Giai đoạn 4: Kích nổ và Xử lý Merge Conflict:** 
    *   Tạo hai nhánh độc lập từ cùng một gốc lịch sử sạch là `nhánh-thử-conflict-a` và `nhánh-thử-conflict-b`.
    *   Cho cả hai nhánh cùng chỉnh sửa tại một dòng cuối của file `README.md` với hai nội dung cạnh tranh khác nhau nhằm tạo ra xung đột cục bộ.
    *   Tiến hành hợp nhất (merge) lần lượt hai nhánh vào `main` tại local để kích hoạt tình huống `Merge Conflict`.
    *   Sử dụng trình soạn thảo code để dọn dẹp các ký tự phân tách (`<<<<<<<`, `=======`, `>>>>>>>`), đồng thuận giữ lại nội dung hòa giải của cả hai nhánh và đẩy kết quả sạch sẽ lên GitHub.

---

## 2. Lịch Sử Commit và Nhánh Đã Thực Hiện

Đã thực hiện hơn 10 commit có ý nghĩa trong suốt quá trình hoàn thiện cấu trúc dự án:

| # | Commit Message | Branch |
|---|---|---|
| 1 | `Chore: Khởi tạo repo và thêm README.md` | main |
| 2 | `Docs: Tạo file hướng dẫn 01-co-ban.md` | main |
| 3 | `Docs: Hoàn thiện 4 lệnh cơ bản trong 01-co-ban.md` | main |
| 4 | `Docs: Khởi tạo file hướng dẫn 02-branch-pr.md trên nhánh feature` | feature/branch-guide |
| 5 | `Docs: Bổ sung định nghĩa Pull Request` | feature/branch-guide |
| 6 | `Fix: Thêm tính năng thử nghiệm (commit lỗi)` | main |
| 7 | `Revert "Fix: Thêm tính năng thử nghiệm (commit lỗi)"` | main |
| 8 | `Docs: Tạo file 04-advanced.md hướng dẫn revert/reset` | main |
| 9 | `Content: Cập nhật mục lục tại nhánh main` | main |
| 10 | `Content: Sửa mục lục theo phong cách nhánh feature` | feature/conflict-test |
| 11 | `Docs: Viết tài liệu hướng dẫn fix conflict` | feature/conflict-test |
| 12 | `Content: Nhánh feature tự nhận làm nhà tài trợ` | feature/real-conflict |
| 13 | `Content: Nhánh A sửa dòng cuối` | nhánh-thử-conflict-a |
| 14 | `Content: Nhánh B sửa dòng cuối` | nhánh-thử-conflict-b |
| 15 | `Fix: Giải quyết conflict thành công giữa hai nhánh` | main |

---

## 3. Minh Chứng Thực Hành Tình Huống Đặc Biệt

### Thực hành Conflict
Đã tạo tình huống xung đột bằng cách chỉnh sửa cùng một dòng cuối trong file `README.md` trên cả branch `main` (sau khi gộp nhánh A) và branch `nhánh-thử-conflict-b`. 
Khi thực hiện `git merge nhánh-thử-conflict-b` trên `main`, Git báo conflict. Đã giải quyết conflict thành công tại local bằng cách giữ lại nội dung hòa giải từ cả hai branch, dọn sạch chữ thừa và lưu lại vết cắt lịch sử (Merge Commit) lưỡng tính rõ ràng trên GitHub.
*   *Chi tiết hướng dẫn xử lý được ghi lại tại:* `03-conflict.md`

### Thực hành Revert / Rollback
Đã mô phỏng tình huống vô tình chèn một đoạn thử nghiệm lỗi chứa thông tin sai lệch vào cuối file `README.md` ở commit số 6. Ngay sau đó, lệnh `git revert HEAD --no-edit` đã được áp dụng để tự động tạo ra commit số 7 nhằm phủ quyết và đảo ngược nội dung lỗi, đưa hệ thống về trạng thái ổn định an toàn tuyệt đối.
*   *Chi tiết hướng dẫn xử lý được ghi lại tại:* `04-advanced.md`

---

## 4. Danh Sách Lệnh Git Đã Sử Dụng
*   `git init`: Khởi tạo kho lưu trữ Git mới.
*   `git status`: Kiểm tra trạng thái thay đổi của các file.
*   `git add <file>`: Đưa file vào khu vực chuẩn bị (Staging Area).
*   `git commit -m "msg"`: Ghi lại ảnh chụp lịch sử kèm thông điệp tường minh.
*   `git checkout -b <nhánh>`: Tạo nhánh mới và chuyển sang nhánh đó.
*   `git checkout <nhánh>`: Di chuyển qua lại giữa các nhánh.
*   `git merge <nhánh>`: Hợp nhất nhánh chỉ định vào nhánh hiện tại.
*   `git revert <commit_id>`: Tạo commit mới để đảo ngược một commit cũ bị lỗi.
*   `git remote add origin <url>`: Liên kết repo local với GitHub remote.
*   `git pull origin <nhánh>`: Kéo mã nguồn mới nhất từ GitHub về máy.
*   `git push origin <nhánh>`: Đẩy các commit từ máy lên GitHub.
*   `git log --oneline --graph --all`: Xem sơ đồ đồ thị lịch sử của toàn bộ các nhánh.

---

## 5. Tầm Nhìn: “Tôi sẽ dùng Git như thế nào khi Vibe Code với AI?”
Khi bước vào kỷ nguyên **Vibe Coding** – nơi AI hỗ trợ tạo ra mã nguồn với tốc độ chóng mặt, Git không chỉ đơn thuần là công cụ quản lý phiên bản, mà chính là **"Hệ thống lưới bảo hiểm an toàn" (Safety Net)** tối thượng của tôi. 

Tôi sẽ luôn chia nhỏ các tính năng do AI gợi ý ra các nhánh (`branch`) độc lập thay vì thao tác trực tiếp trên nhánh chính `main`. Trước khi cho AI can thiệp hay cấu trúc lại (refactor) bất kỳ module quan trọng nào, tôi sẽ tạo một commit làm cột mốc đánh dấu rõ ràng. Nếu AI sinh code lỗi hoặc làm xáo trộn hệ thống logic, các kỹ năng phục hồi như `git revert` hay `git reset` sẽ là chiếc phanh giúp tôi "quay xe" an toàn ngay lập tức. Git chính là chìa khóa giúp tôi giữ thế chủ động, kiểm soát toàn diện tốc độ và chất lượng sản phẩm khi cộng tác cùng trí tuệ nhân tạo.