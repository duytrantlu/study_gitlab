# tạo project và sử dụng trên gitlab
**các bước tạo và đưa project lên gitlab**
    - bước 1:
        ```
           vào trang chủ gitlab, chọn \*New\* sau đó nhập tên project và ấn create.
        ```
    - bước 2:
        ```
            trong project trên máy tính cá nhân, thực hiện các lệnh sau bằng CLI (chú ý: đường dẫn phải đang ở trong project đó).
            * thực hiện 2 lệnh sau nếu lần đầu up project lên gitlab
                git config --global user.name "duytranmanh"
                git config --global user.email "duytrantlu@gmail.com"
            * Create a new repository (thường thì bước này đã tạo bằng tay ở bước 1)
                git clone https://gitlab.com/duytm2/study.git
                cd study
                touch README.md
                git add README.md
                git commit -m "add README"
                git push -u origin master
            * nếu thư mục đã tồn tại (thường thì làm từ bước này đi)
                cd existing_folder
                git init
                git remote add origin https://gitlab.com/duytm2/study.git
                git add .
                git commit -m "Initial commit"
                git push -u origin master
            * nếu repository đó đã tồn tại (đây là trường hợp khi muốn thay đổi repository, khuyến cáo ko nên đọc lại Docs rồi làm)
                cd existing_repo
                git remote rename origin old-origin
                git remote add origin https://gitlab.com/duytm2/study.git
                git push -u origin --all
                git push -u origin --tags
        ```
    - bước 3:
        * bước 2 thực ra là đã xong hết việc đẩy code lên gitlab, bước này để giành cho ai muốn tạo riêng branch, (thường thì bình thường chúng ta đẩy code vào branch master, điều này là ko đc khuyến cáo).
        * trước tiên tạo mới 1 branch bằng cú pháp:
            git checkout -b tên_branch_mới
        * đẩy code lên branch mới
            git commit -am "My feature is ready"
            git push origin tên_branch vừa tạo
    - ngoài ra còn 1 số lệnh hỗ trợ:
        * để pull project về:
            git pull tên_branch_muốn_pull