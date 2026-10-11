# Bảng chẩn đoán lỗi Git trên máy Lab

| STT | Triệu chứng quan sát | Nguyên nhân gốc | Thao tác khắc phục | Kết quả kiểm chứng |
|:---:|---|---|---|---|
| 1 | Commit hiện tên DESKTOP-LAB07 thay vì tên người | user.name ở phạm vi toàn máy (global) đang bị đặt thành tên máy. | Đặt lại user.name ở phạm vi toàn máy (git config --global). | Chạy lệnh git config user.name trả về đúng họ tên của bạn. |
| 2 | Các commit trên GitHub không gắn với tài khoản nào | user.email bị sai (là email local ảo lab07@...). GitHub cần email trùng với email đăng ký tài khoản để link profile. | Đặt lại user.email ở phạm vi toàn máy (git config --global) bằng email đăng ký GitHub. | Chạy lệnh git config user.email trả về đúng email GitHub. |
| 3 | Có 2 dòng user.email trong git config --list của thư mục library-docs | Ai đó đã cài đặt user.email riêng lẻ ở phạm vi kho hiện tại (--local) đè lên cấu hình hệ thống. | Xóa cấu hình email ở phạm vi local của repo này. | Chạy git config --show-origin user.email hiển thị nguồn là từ file .gitconfig global. |
| 4 | Nhập đúng mật khẩu tài khoản GitHub khi push vẫn bị từ chối (Authentication failed) | Từ 08/2021, GitHub đã gỡ bỏ xác thực bằng mật khẩu tài khoản để tăng bảo mật. | Tạo Personal Access Token (PAT) trên GitHub và dùng nó thay cho mật khẩu khi push. | Lệnh git push origin main thực thi thành công. |
