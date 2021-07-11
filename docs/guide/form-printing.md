# Cấu hình in ấn

Dữ liệu biểu mẫu điện tử có thể xuất ra thành các file in có thể chỉnh sửa được một cách dễ dàng.

Truy cập menu **In ấn** trong biểu mẫu để thêm và chỉnh sửa các template in ấn cho biểu mẫu của bạn.

Mỗi biểu mẫu bạn có thể tạo nhiều mẫu in khác nhau. Kích vào nút **Thêm bản in** để tải lên mẫu in mới cho biểu mẫu.

<figure>
  <img src="https://formlaez.com/wp-content/uploads/2021/07/print.png" width="100%" />
  <figcaption>Cấu hình in ấn biểu mẫu</figcaption>
</figure>

## Cách tạo một mẫu in

Để có thể in được dữ liệu biểu mẫu điện tử, bạn cần tạo ít nhất một mẫu in.

Mẫu in là một biểu mẫu thông thường, lưu trữ dưới dạng file.

Hiện tại ứng dụng chỉ chấp nhận định dạng file mẫu in là `.docx`. Bạn có thể dùng Microsoft Office phiên bản từ 2010 hoặc Google Docs để soạn thảo mẫu in và tải xuống theo định dạng `.docx`.

### Đặt mã định danh cho các trường thông tin

Để dữ liệu biểu mẫu điện tử có thể điền đúng vào các mẫu in bạn cần đặt mã định danh duy nhất cho các trường thông tin trong biểu mẫu điện tử của bạn.

<figure>
  <img src="https://formlaez.com/wp-content/uploads/2021/07/field_code.png" width="100%" />
  <figcaption>Cấu hình mã định danh của trường thông tin</figcaption>
</figure>

***Lưu ý:***

* *Mã định danh của mỗi trường thông tin phải là duy nhất*
* *Mã định danh được tạo tự động khi bạn thêm trường thông tin vào biểu mẫu, tuy nhiên mã này là các ký tự không có nghĩa, vì thế bạn nên đặt lại để dễ dàng sử dụng hơn*
* *Mã định danh nên là ký tự không dấu, viết liền, in hoa hoặc in thường*

***Ví dụ:***
*Trường thông tin Họ và tên thì bạn nên đặt mã định danh là **HoVaTen***

### Soạn thảo mẫu in

#### Trường hợp không lặp lại

Đối với các trường thông tin thường các bạn chỉ cần sao chép mã của trường thông tin và dán vào vị trí mong muốn trong mẫu in.

Ví dụ: Trường thông tin là **Họ và tên** với mã định danh là **HoVaTen** thì bạn chỉ cần thêm `${HoVaTen}` vào những vị trí cần điền giá trị Họ và tên trong mẫu in.

#### Trường hợp lặp lại

Với nhóm trường thông tin lặp lại bạn có thể tạo thành bảng hoặc các đoạn văn lặp lại trong bản in.

Chúng ta ví dụ một biểu mẫu có vùng lặp lại trong biểu mẫu có định danh là **DanhSachNhanVien** và trong vùng lặp lại chúng ta có trường thông tin với mã định danh là **HoTenNhanVien**. Giả sử danh sách nhân viên người dùng nhập vào biểu mẫu bao gồm:

* Nguyễn Văn An
* Nguyên Thị Ánh


Chúng ta có thể cấu hình mẫu in như sau:

1. Lặp lại dạng bảng

* Đầu tiên bạn thêm `#{DanhSachNhanVien}` ngay trước bảng trong mẫu in
* Trong dòng cuối cùng của bảng bạn thêm giá trị này `${HoTenNhanVien}` vào ô cần hiển thị tên nhân viên
* Nếu bạn cần lấy số thứ tự hãy thêm giá trị này `${INDEX}` vào ô cần hiển thị số thứ tự

<figure>
  <img src="https://formlaez.com/wp-content/uploads/2021/07/print-vars.png" width="100%" />
  <figcaption>Lặp lại dạng bảng</figcaption>
</figure>

Như vậy khi xuất ra bản in bảng dữ liệu sẽ như sau:

<figure>
  <img src="https://formlaez.com/wp-content/uploads/2021/07/print-example_1.png" width="100%" />
  <figcaption>Xuất bản in dữ liệu lặp lại dạng bảng</figcaption>
</figure>


2. Lặp lại dạng đoạn văn bản

Trong trường này bạn cần xác định vùng lặp lại bằng cách thêm cặp giá trị sau và đầu và cuối đoạn văn bạn muốn lặp lại:

```
@{DanhSachNhanVien}

...

@{/}
```

Ví dụ:


<figure>
  <img src="https://formlaez.com/wp-content/uploads/2021/07/print-example_2.png" width="100%" />
  <figcaption>Lặp lại dạng đoạn văn</figcaption>
</figure>

Như vậy khi xuất ra bản in sẽ như sau:

<figure>
  <img src="https://formlaez.com/wp-content/uploads/2021/07/print-example_3.png" width="100%" />
  <figcaption>Xuất bản in dữ liệu lặp lại dạng đoạn văn</figcaption>
</figure>


Một số mẫu in ví dụ bạn có thể tải về tham khảo:

[Mẫu đơn xin tạm trú tạm vắng](https://drive.google.com/file/d/1jmzF5DbypPuAInMxXMa3N9w0Y9OgNfyj/view?usp=sharing)

[Mẫu tờ trình xin mua sắm thiết bị](https://drive.google.com/file/d/1zKfYw4LPLRDlzGJTIGjKIIbJIVLwJrme/view?usp=sharing)
