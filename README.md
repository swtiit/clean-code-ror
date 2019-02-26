## Các công cụ kiểm tra chất lượng code tốt nhất dành cho lập trình viên Ruby on Rails áp dụng trong các dự án ở công ty NAL
### 1. traceroute (https://github.com/amatsuda/traceroute )
##### Mô tả
>  Traceroute là một công cụ giúp làm gọn gàng các routes trong ứng dụng của bạn. Nó cung cấp các rake task đơn giản để kiểm tra các routes đang được ánh xạ tới những controller actions không tồn tại, và tìm ra những controller actions không thể truy cập tới.
##### Cài đặt và sử dụng
- Cài đặt: 
  - Thêm vào Gemfile: ```gem 'traceroute'```
  - Chạy ```bunde install```
- Sử dụng:
  - Chạy lệnh: ```rake traceroute```
- Kết quả:
  ```
  Unused routes:

  Unreachable action methods:

  ```
  - Unused routes: Hiển thị những routes mà chúng ta đã khai báo nhưng không sử dụng đến.
  - Unreachable action methods: Hiển thị những methods mà chúng ta đã khai báo nhưng lại không có routes.
##### Cấu hình khác
Chúng ta cũng có thể config lại những để có thể bỏ qua việc kiểm tra đến một số action nào đó mà chúng ta không cần kiểm tra bằng cách. Tạo file .traceroute.yaml (hoặc .traceroute.yml hoặc .traceroute) bên trong dự án của mình.
File sẽ có dạng như sau:
  ```
  # .traceroute.yaml
  ignore_unreachable_actions:
  - ^jasmine_rails\/
  ignore_unused_routes:
  - ^users#index

  ```

##### Yêu cầu sản phẩm ok nếu sau khi chạy có kết quả sau
  ```
  Unused routes (0):

  ```
  ---------------------
  
### 2. rails best practices (https://github.com/flyerhzm/rails_best_practices)
##### Mô tả
>  Rails best practices là một công cụ đo số liệu của codes để kiểm tra chất lượng của codes Rails của bạn. Nó cung cấp một loạt các gợi ý, như sử dụng scope access, restrict auto-generated routes, và database indexes.
##### Cài đặt và Sử dụng
- Cài đặt: 
  - Thêm vào Gemfile: ```gem 'rails_best_practices'```
  - Chạy ```bunde install```
- Sử dụng:
  - Hiển thị kết quả ngay trên terminal:
  ```rails_best_practices .```
    - Kết quả:
    ![Image of result run in terminal](https://2.pik.vn/20194c705ab3-e3f3-49dd-94a9-b24c68304bca.png)
  - Hiển thị kết quả trên file html:
  ```rails_best_practices -f html .```
    - Kết quả:
    ![Image of result run in browser](https://2.pik.vn/20196ac41a1a-83f5-44d6-a060-d7503eb0fa64.png)
    - Ở đây chúng ta sẽ kiểm tra các mục được check ở trong ảnh.
##### Cấu hình khác
- Chúng ta có thể loại bỏ những file mà chúng ta không thực hiện kiểm tra bằng câu lệnh:
  ```
  rails_best_practices -e "db/migrate" .
  ```
- Thêm nhiều file ngăn cách nhau bằng dấu ','
  ```
  rails_best_practices -e "db/migrate,vendor" .
  ```

##### Yêu cầu sản phẩm ok nếu sau khi chạy có kết quả sau
- Kết quả những phần check ở ảnh
![Image of result run in browser](https://2.pik.vn/20196ac41a1a-83f5-44d6-a060-d7503eb0fa64.png)
thì sẽ không còn 1 lỗi nào cả
##### Tham khảo: http://rails-bestpractices.com
  ---------------------
