# 📖 Exercise4: Quản lý Sách với Dịch vụ Web ASP.NET Core và MongoDB

## 🛠 Tổng quan

Dự án này triển khai một API RESTful bằng **ASP.NET Core**, cho phép thực hiện các thao tác quản lý thông tin sách. **MongoDB** được sử dụng làm hệ quản trị cơ sở dữ liệu, hỗ trợ đầy đủ các chức năng CRUD (Create, Read, Update, Delete) cho dữ liệu sách.

---

## 📂 Cấu trúc dự án

### **Controllers**
- Chứa lớp `BooksController` để định nghĩa các API endpoints.
- Các phương thức chính:
  - `GET /api/books`: Lấy danh sách tất cả các sách.
  - `GET /api/books/{id}`: Lấy thông tin chi tiết của một sách theo ID.
  - `POST /api/books`: Thêm mới một sách vào cơ sở dữ liệu.
  - `PUT /api/books/{id}`: Cập nhật thông tin sách theo ID.
  - `DELETE /api/books/{id}`: Xóa một sách khỏi cơ sở dữ liệu.

### **Models**
- Gồm hai lớp chính:
  - **`Book`**:
    - Đại diện cho thông tin sách trong cơ sở dữ liệu.
    - Các thuộc tính:
      - `Id`: Định danh duy nhất của sách (do MongoDB tự động tạo).
      - `Name`: Tên sách.
      - `Price`: Giá sách.
      - `Category`: Thể loại sách.
      - `Author`: Tác giả.
  - **`BookStoreDatabaseSettings`**:
    - Chứa thông tin cấu hình kết nối MongoDB:
      - `ConnectionString`: Chuỗi kết nối MongoDB.
      - `DatabaseName`: Tên cơ sở dữ liệu.
      - `BooksCollectionName`: Tên bộ sưu tập trong cơ sở dữ liệu.

### **Services**
- Gồm lớp `BooksService` thực hiện các tác vụ tương tác với MongoDB.
- Các chức năng chính:
  - Truy xuất toàn bộ danh sách sách hoặc một sách cụ thể.
  - Thêm mới, cập nhật và xóa sách.
  - Sử dụng thư viện `MongoDB.Driver` để thao tác với cơ sở dữ liệu.

---

## 🌟 Chức năng chính

| **Chức năng**                     | **HTTP Method** | **Endpoint**         | **Mô tả**                                                                 |
|-----------------------------------|-----------------|----------------------|---------------------------------------------------------------------------|
| **Lấy danh sách sách**            | GET             | `/api/books`         | Lấy toàn bộ danh sách sách hiện có trong cơ sở dữ liệu.                   |
| **Truy xuất thông tin chi tiết**  | GET             | `/api/books/{id}`    | Lấy thông tin chi tiết của một sách dựa trên ID.                         |
| **Thêm sách mới**                 | POST            | `/api/books`         | Thêm một sách mới vào hệ thống với thông tin như tên, giá, thể loại, tác giả. |
| **Cập nhật sách**                 | PUT             | `/api/books/{id}`    | Cập nhật thông tin của một sách dựa trên ID và dữ liệu mới được cung cấp. |
| **Xóa sách**                      | DELETE          | `/api/books/{id}`    | Xóa một sách khỏi cơ sở dữ liệu dựa trên ID.                             |

---

## 🌟 Kết quả đạt được

1. **Triển khai thành công API RESTful**:
   - API hỗ trợ đầy đủ các thao tác CRUD, với cấu trúc rõ ràng và dễ sử dụng.

2. **Kết nối MongoDB**:
   - Hệ thống sử dụng MongoDB làm cơ sở dữ liệu chính, với cấu hình kết nối thông qua `appsettings.json`.

3. **Tích hợp Swagger**:
   - Cung cấp giao diện để thử nghiệm các API thông qua Swagger UI.

4. **Cấu trúc dự án rõ ràng**:
   - Các thành phần được tách biệt theo từng vai trò: Controller, Service, Model.
   - Dễ dàng bảo trì và mở rộng trong tương lai.

5. **Hỗ trợ dữ liệu mẫu**:
   - Có thể khởi tạo và thao tác với dữ liệu mẫu, giúp quá trình kiểm tra nhanh chóng và hiệu quả.

---
