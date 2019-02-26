## Các công cụ kiểm tra chất lượng code tốt nhất dành cho lập trình viên Ruby on Rails áp dụng trong các dự án ở công ty NAL

### 1. traceroute (https://github.com/amatsuda/traceroute)
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
### 3. rubocop (https://github.com/rubocop-hq/rubocop)
##### Mô tả
>  Rubocop là một công cụ để phân tích và so sánh code Ruby với một số quy tắc đã được định nghĩa sẵn (Các quy tắc của RuboCop thường được gọi là "cops").
##### Link tham khảo style: https://github.com/rubocop-hq/ruby-style-guide (Có bản dịch khoảng 10 ngôn ngữ khác nhau)
##### Cài đặt và sử dụng
- Cài đặt: 
  - Thêm vào Gemfile: ```gem 'rubocop', require: false```
  - Chạy ```bunde install```
- Sử dụng:
  - Chạy lệnh: ```rubocop```
  - Hoặc có thể chạy cho một file nào cụ thể bằng cách:
    - ```rubocop + 'đường dẫn file'```
    - example: ```rubocop app/models/answer```
- Kết quả:
  ![Image of rubocop](https://2.pik.vn/2019fa232ca6-d8a6-4d95-b362-a45ff69065ed.png)
##### Cấu hình khác
Chúng ta cũng có thể config lại những để có thể bỏ qua việc kiểm tra đến những file mà chúng ta cho rằng không cần thiết hoặc có thể chỉnh sửa lại cài đặt sẵn của Rubocop mà chúng ta cảm thấy chưa hợp lý. Tạo file .rubocop.yml bên trong dự án của mình.
File sẽ có dạng như sau:
 ![Image of config rubocop]( https://2.pik.vn/201949ac2c63-b4ae-48d4-980d-4e7dee326cb5.png)

##### Yêu cầu sản phẩm ok nếu sau khi chạy có kết quả sau
 - Những file vừa thay đổi thì kết quả sau ```0 files inspected, no offenses detected```
  ---------------------
### 4. scss-lint (https://github.com/brigade/scss-lint)
##### Mô tả
>  scss-lint là một công cụ giúp giữ cho các file SCSS của bạn sạch sẽ và có thể đọc được bằng cách chạy nó dựa trên các quy tắc linter rules.
- linter rules (https://github.com/brigade/scss-lint/blob/master/lib/scss_lint/linter/README.md)
##### Cài đặt và sử dụng
- Cài đặt: 
  - Thêm vào Gemfile: ```gem 'scss_lint', require: false```
  - Chạy ```bunde install```
- Sử dụng:
  - Chạy lệnh: ```scss-lint app/assets/stylesheets/```
  - Hoặc có thể chạy cho một file nào cụ thể bằng cách:
    - ```scss-lint app/assets/stylesheets/**/*.css.scss```
- Kết quả:
  ![Image of scss lint](https://2.pik.vn/20198bcc6cb5-62a6-422d-8291-8705dc80df09.png)
##### Cấu hình khác
Chúng ta cũng có thể chỉnh sửa lại cài đặt sẵn của scss-lint mà chúng ta cảm thấy chưa hợp lý. Tạo file .scss-lint.yml bên trong dự án của mình.
File sẽ có dạng như sau:
 ![Image of config scss lint]( https://2.pik.vn/20193f8dbbfe-e223-4f5b-b10e-db0115b7cd59.png)

##### Yêu cầu sản phẩm ok nếu sau khi chạy có kết quả sau
 - Những file vừa thay đổi thì kết quả sẽ không còn file nào có lỗi.
  --------------------
### 5. eslint-rails (https://github.com/appfolio/eslint-rails)
##### Mô tả
>  eslint-rails là một công cụ giúp giữ cho các file js, jsx, es6 của bạn sạch sẽ và có thể đọc được bằng cách chạy nó dựa trên các quy tắc ESLint.
- ESLint (https://eslint.org/)
##### Cài đặt và sử dụng
- Cài đặt: 
  - Thêm vào Gemfile: ```gem 'eslint-rails'```
  - Chạy ```bunde install```
- Sử dụng:
  - Chạy lệnh: ```rake eslint:run_all```
  - Hoặc có thể chạy cho một file application.js:
    - ```rake eslint:run```
- Kết quả:
  ![Image of eslint](https://2.pik.vn/20195fcf17b3-dd19-4c89-a11b-c37c128800fb.png)
##### Yêu cầu sản phẩm ok nếu sau khi chạy có kết quả sau
 - Những file vừa thay đổi thì kết quả sẽ không còn file nào có lỗi.
