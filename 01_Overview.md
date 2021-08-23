# Tổng quan về GitLab
## **1) Giới thiệu** <img src=https://i.imgur.com/58hHlvU.png align=right width=20%>
- Trang chủ : https://gitlab.com/
- **GitLab** là một phần mềm mã nguồn mở được viết bằng ngôn ngữ **Ruby**, có nhiệm vụ quản lý kho code Git, quản lý issue, giám sát và cả tích hợp **CI/CD**. **GitLab** sở hữu các tính năng đơn giản, góp phần to lớn trong việc giúp các doanh nghiệp, cá nhân, tổ chức lưu trữ code một cách nhanh chóng vô cùng, người dùng hoàn toàn có thể truy cập mọi lúc mọi nơi miễn là có kết nối Internet.
- **Gitlab** cũng có khá nhiều điểm tương đồng với **GitHub** nhưng **GitHub** đi theo hướng kinh doanh nhiều hơn, bởi vì nếu bạn sở hữu kho code riêng và muốn ẩn chúng khỏi cộng đồng hoặc mở rộng hơn nữa thì bạn sẽ phải trả phí cho dịch vụ này. **Gitlab** hoàn toàn ngược lại, bạn có thể ẩn kho code của mình, không công khai chúng cho bất kỳ ai, trong trường hợp vượt quá ngưỡng miễn phí thì bạn mới phải mất phí để mua thêm dịch vụ.
- Công ty **GitLab** có 4 sản phẩm :
    - **GitLab CE (*community edition*)** : mã nguồn open source, bạn tự host dịch vụ **GitLab** Git Server riêng; nhận được sự hỗ trợ từ cộng đồng và forum.
    - **GitLab EE (*enterprise edition*)** : bản trả phí, thương mại, các tính năng nâng cao.
    - **GitLab.com** : tương tự Github.com , Software as Service và miễn phí.
    - **GitLab.io** : dịch vụ máy chủ **GitLab** nội bộ quản lý bởi **GitLab**.
## **2) Một số đặc điểm của GitLab**
- ***Protected branches*** :
    - Cho phép đọc hoặc ghi vào repository và các branches. Protected branches cấp quyền cho những người được phép commit và pushing code. Một protected branch gồm 3 điều cơ bản sau:
        - Ngăn chặn việc push từ tất cả mọi người trừ user và master.
        - Ngăn chặn việc push code lên branch từ những người không có quyền truy cập.
        - Ngăn chặn bất kỳ ai thực hiện xóa branch.
    - Master branch được mặc định là protected branch. User cần được cấp ít nhất một quyền từ master branch để bảo mật branch.
- ***Tầng vật lý của GitLab*** :
- ***System layout***
- ***Component***