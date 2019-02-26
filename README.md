## Các công cụ kiểm tra chất lượng code tốt nhất dành cho lập trình viên Ruby on Rails áp dụng trong các dự án ở công ty NAL
### traceroute (https://github.com/amatsuda/traceroute )
##### Mô tả
>  Traceroute là một công cụ giúp làm gọn gàng các routes trong ứng dụng của bạn. Nó cung cấp các rake task đơn giản để kiểm tra các routes đang được ánh xạ tới những controller actions không tồn tại, và tìm ra những controller actions không thể truy cập tới.
##### Cài đặt và thực hiện
- Cài đặt: 
  - Thêm vào Gemfile: gem 'traceroute'
  - Chạy bunde install
- Thực hiện:
  - Chạy lệnh: rake traceroute
- Kết quả:
  ```
  Unused routes:

  Unreachable action methods:

  ```
  - Unused routes: Hiển thị những routes mà chúng ta đã khai báo nhưng không sử dụng đến.
  - Unreachable action methods: Hiển thị những methods mà chúng ta đã khai báo nhưng lại không có routes.
##### Cài đặt khác
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
