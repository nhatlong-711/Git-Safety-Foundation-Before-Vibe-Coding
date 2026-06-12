# Phần 4: Sửa lỗi và Quay xe (Rollback/Revert)

Khi bạn lỡ commit một nội dung sai lên hệ thống, bạn có 2 cách xử lý:
* `git revert <commit_id>`: Tạo ra một commit mới để đảo ngược thay đổi của commit cũ (An toàn khi làm việc nhóm).
* `git reset --hard <commit_id>`: Xóa hẳn các commit sau commit chỉ định (Nguy hiểm, chỉ nên làm ở local).