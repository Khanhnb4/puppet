# puppet


### Câu lệnh trong Puppet:

puppet apply

Thực thi các tệp manifest Puppet và áp dụng cấu hình trên một máy cụ thể.
   ```
puppet agent
   ```
   
Chạy Puppet agent để gửi yêu cầu cập nhật cấu hình đến Puppet master.
   ```
puppet cert
   ```
   
Quản lý chứng chỉ SSL của Puppet.
   ```
puppet resource
   ```
   
Hiển thị thông tin chi tiết về các tài nguyên Puppet.
   ```
puppet module
   ```
   
Quản lý và tìm kiếm module Puppet.
   ```
puppet parser validate
   ```
   
Kiểm tra tính hợp lệ của các tệp manifest Puppet.
   ```
puppet facts
   ```
   
   ```Hiển thị thông tin về các facts (thông tin máy chủ) được thu thập bởi 
Puppet.
   ```
   
### VD:
   ```
puppet describe user |more
puppet resource user bob ensure=present groups=sysadmins
puppet apply bob.pp 
   ```
   ```
puppet apply với tùy chọn --noop (no-op mode), Puppet sẽ thực hiện quá trình đánh giá và tạo ra catalog (bảng mô tả tài nguyên) nhưng không thực hiện các thay đổi thực tế trên hệ thống. Điều này giúp bạn xem trước các thay đổi mà Puppet sẽ áp dụng mà không làm ảnh hưởng đến hệ thống.
   ```
   ```
puppet cert --list (chi ra list cert dang waiting thoi,)  | puppet cert --list --all ( list all cert include waiting and catching) | puppet cert --print puppet.localdomain |more (show data cert puppet.localdomain )
   ```

### Cấu trúc một module trong Puppet thường bao gồm các thành phần sau:

1. Thư mục manifests: 
Đây là nơi chứa các tệp mã Puppet (.pp) chứa các định nghĩa và cấu hình của module. Mỗi tệp manifest thường tương ứng với một tác vụ hoặc một phần của module.

2. Thư mục files: 
Đây là nơi chứa các tệp tin (file) mà module cần sử dụng trong quá trình triển khai. Ví dụ: tệp cấu hình, tệp script, tệp khởi tạo dữ liệu, ...

3. Thư mục templates: 
Đây là nơi chứa các mẫu (templates) được sử dụng để tạo ra các tệp tin động (dynamic) trong quá trình triển khai. Mẫu thường sử dụng ngôn ngữ template của Puppet để kết hợp các giá trị và logic.

4. Thư mục facts.d: 
Đây là nơi chứa các tệp mã script hoặc tệp nhị phân được sử dụng để thu thập thông tin về các facts (thông tin hệ thống) từ các máy chủ mục tiêu. Facts được sử dụng để điều chỉnh cấu hình và cung cấp dữ liệu động cho module.

5. Tệp metadata.json: 
Đây là tệp JSON chứa thông tin metadata về module, bao gồm tên module, phiên bản, tác giả, mô tả, phụ thuộc, ... Tệp này cung cấp thông tin quan trọng về module để Puppet có thể quản lý và sử dụng module một cách chính xác.

### Cu phap tong ngon ngu template puppet
1. <-% | | -%> khac <% | | %>: cú pháp được sử dụng trong ngôn ngữ template để kiểm soát xử lý khoảng trắng và dòng trống không mong muốn được xuất hiện sau khối mã hoặc điều kiện.

### Warning
1. WARN  puppetlabs.facter - locale environment variables were bad; continuing with LANG=C LC_ALL=C

    ```
locale
export LANG=en_US.UTF-8
export LC_ALL=en_US.UTF-8
locale
   ```

