# Cài đặt GitLab CE
## **1) Cài đặt trên CentOS 7**
- **B1 :** Update các package sẵn có :
    ```
    # yum update -y
    # yum upgrade -y
    ```
- **B2 :** Cài đặt một số package cần thiết :
    ```
    # yum install -y curl policycoreutils-python openssh-server perl
    ```
- **B3 :** Cài đặt repo của **GitLab** :
    ```
    # curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.rpm.sh | sudo bash
    ```
- **B4 :** Cài đặt **GitLab CE** :
    ```
    # yum -y install gitlab-ce
    ```
    <img src=https://i.imgur.com/8idVdCw.png>

    > ***Lưu ý :*** 
    - **Gitlab Omnibus** bao gồm nhiều gói package bên trong như: NginX, Postgresql, Redis, Sidekiq, Unicorn, .. nên dung lượng khá nặng.
    - Nếu trên server đang sử dụng Nginx làm web server thì có thể bị trùng port `80` hoặc `443`. Chúng ta có thể disable gói Nginx trong **Gitlab Omnibus** đi để dùng Nginx có sẵn.
- **B5 :** Cho phép port `80` qua `firewalld` :
    ```
    # firewall-cmd --zone=public --permanent --add-port=80/tcp
    # firewall-cmd --reload
    ```
- **B6 :** Cấu hình domain cho **GitLab** :
    ```
    # vi /etc/gitlab/gitlab.rb
    ```
    - Chỉnh sửa `external_url` ở dòng `32` :
        ```
        external_url 'http://192.168.5.70'
        ```
        - Trong đó, `192.168.5.70` là IP server. Nếu có tên miền, có thể cấu hình tên miền ở đây.
- **B7 :** Load các cấu hình của **GitLab** :
    ```
    # gitlab-ctl reconfigure
    ```
- **B8 :** Kiểm tra lại trạng thái các thành phần của **GitLab** :
    ```
    # gitlab-ctl status
    ```
    <img src=https://i.imgur.com/XSHySlS.png>

- **B9 :** Lấy password user `root` của **GitLab** ở file `/etc/gitlab/initial_root_password` :
    ```
    # cat /etc/gitlab/initial_root_password
    ```
    <img src=https://i.imgur.com/ZMKAGpO.png>
    > File này sẽ tự động xóa sau `24h` cài đặt **GitLab**.
- **B10 :** Trên trình duyệt, nhập URL của **GitLab** để truy cập, nhập user `root` và password đã lấy ở trên -> ***Sign in*** :
    ```
    http://192.168.5.70
    ```
    <img src=https://i.imgur.com/S9F5xTO.png>

    - Đăng nhập thành công :

        <img src=https://i.imgur.com/eHrfPYc.png>

- **B11 :** Đổi password và user mặc định. Vì lý do bảo mật , thì chúng ta không nên để tên user `root` dễ bị dò thông tin. Thay vào đó hãy đổi sang tên khác như `admin` hoặc bất kì cái tên gì bạn muốn. Truy cập **Profile -> Settings** :

    <img src=https://i.imgur.com/Iu5S0xY.png>

    - Tại màn hình **User Settings** -> Chọn **Account** -> Nhập tên user muốn đổi thành -> ***Update username*** :

        <img src=https://i.imgur.com/9gmMTlo.png>

    - Refresh lại trang ta sẽ thấy user đã được đổi tên thành công :

        <img src=https://i.imgur.com/ajhaU4p.png>

    - Chọn **Password** để đổi mật khẩu. Nhập các thông tin về mật khẩu mặc định và mật khẩu mới -> ***Save password*** :

        <img src=https://i.imgur.com/rnJGgTI.png>

    - Sau khi đổi thành công, hệ thống sẽ tự động logout. Đăng nhập lại với user và password vừa đổi.