# Postman API Testing

## 1. Student Information

- Họ và tên: Nguyễn Thế Cường
- Môn học: Đánh giá và kiểm định chất lượng phần mềm
- Công cụ: Postman
- API sử dụng: JSONPlaceholder
- GitHub Repository: postman-api-testing


---

## 2. Mục tiêu

Mục tiêu của bài tập là thực hành kiểm thử REST API bằng công cụ Postman.

Các chức năng API được kiểm thử gồm:

- GET danh sách người dùng
- GET thông tin người dùng theo ID
- Kiểm tra trường hợp người dùng không tồn tại
- POST tạo người dùng
- PUT cập nhật người dùng
- DELETE người dùng

---

## 3. API sử dụng

API được sử dụng trong bài:

https://jsonplaceholder.typicode.com

JSONPlaceholder là một REST API giả lập được sử dụng để thực hành và kiểm thử API.

---

## 4. Test Cases

| Test Case | Method | Endpoint | Expected Result |
|---|---|---|---|
| TC01 - GET Users | GET | /users | 200 OK |
| TC02 - GET User By ID | GET | /users/1 | 200 OK |
| TC03 - GET User Not Found | GET | /users/999 | 404 Not Found |
| TC04 - POST Create User | POST | /users | 201 Created |
| TC05 - PUT Update User | PUT | /users/1 | 200 OK |
| TC06 - DELETE User | DELETE | /users/1 | 200 OK |

---
# 5. Chi tiết kiểm thử

## TC01 - GET Users

**Mục đích:** Kiểm tra API lấy danh sách người dùng.

**Phương thức:** GET

**URL:**

https://jsonplaceholder.typicode.com/users

**Kết quả mong đợi:** HTTP 200 OK.

**Nội dung kiểm tra:**

- Kiểm tra mã trạng thái trả về là 200.
- Kiểm tra response có định dạng JSON.
- Kiểm tra response chứa danh sách người dùng.
- Kiểm tra người dùng đầu tiên có các trường `id`, `name`, `email`.

**Kết quả:** PASS

![TC01](images/TC01.png)

---

## TC02 - GET User By ID

**Mục đích:** Kiểm tra API lấy thông tin người dùng theo ID.

**Phương thức:** GET

**URL:**

https://jsonplaceholder.typicode.com/users/1

**Kết quả mong đợi:** HTTP 200 OK.

**Nội dung kiểm tra:**

- Kiểm tra mã trạng thái trả về là 200.
- Kiểm tra response có định dạng JSON.
- Kiểm tra ID người dùng trả về là 1.
- Kiểm tra người dùng có các trường `id`, `name`, `email`.

**Kết quả:** PASS

![TC02](images/TC02.png)

---

## TC03 - GET User Not Found

**Mục đích:** Kiểm tra trường hợp người dùng không tồn tại.

**Phương thức:** GET

**URL:**

https://jsonplaceholder.typicode.com/users/999

**Kết quả mong đợi:** HTTP 404 Not Found.

**Nội dung kiểm tra:**

- Kiểm tra mã trạng thái trả về là 404.
- Kiểm tra response có định dạng JSON.
- Kiểm tra dữ liệu trả về là object rỗng.

**Kết quả:** PASS

![TC03](images/TC03.png)

---

## TC04 - POST Create User

**Mục đích:** Kiểm tra chức năng tạo người dùng mới.

**Phương thức:** POST

**URL:**

https://jsonplaceholder.typicode.com/users

**Dữ liệu gửi lên:**

```json
{
    "name": "Nguyen The Cuong",
    "username": "thecuong",
    "email": "cuong@example.com"
}
Kết quả mong đợi: HTTP 201 Created.

Nội dung kiểm tra:

Kiểm tra mã trạng thái trả về là 201.
Kiểm tra response có định dạng JSON.
Kiểm tra response có trường id.
Kiểm tra thông tin người dùng được tạo chính xác.

Kết quả: PASS

TC05 - PUT Update User

Mục đích: Kiểm tra chức năng cập nhật thông tin người dùng.

Phương thức: PUT

URL:

https://jsonplaceholder.typicode.com/users/1

Dữ liệu gửi lên:

{
    "id": 1,
    "name": "Nguyen The Cuong Updated",
    "username": "thecuong_updated",
    "email": "cuong.updated@example.com"
}

Kết quả mong đợi: HTTP 200 OK.

Nội dung kiểm tra:

Kiểm tra mã trạng thái trả về là 200.
Kiểm tra response có định dạng JSON.
Kiểm tra ID người dùng là 1.
Kiểm tra thông tin người dùng đã được cập nhật chính xác.

Kết quả: PASS

TC06 - DELETE User

Mục đích: Kiểm tra chức năng xóa người dùng.

Phương thức: DELETE

URL:

https://jsonplaceholder.typicode.com/users/1

Kết quả mong đợi: HTTP 200 OK.

Response:

{}

Nội dung kiểm tra:

Kiểm tra mã trạng thái trả về là 200.
Kiểm tra response có định dạng JSON.
Kiểm tra response trả về object rỗng.

Kết quả: PASS

6. Tổng kết kết quả kiểm thử
Test Case	Kết quả
TC01 - GET Users	PASS
TC02 - GET User By ID	PASS
TC03 - GET User Not Found	PASS
TC04 - POST Create User	PASS
TC05 - PUT Update User	PASS
TC06 - DELETE User	PASS
Tổng kết

6/6 Test Case PASS

Tỷ lệ Test Case đạt:

100%

7. Kết luận

Qua bài thực hành, em đã sử dụng Postman để thực hiện kiểm thử REST API với các phương thức GET, POST, PUT và DELETE.

Các Test Case bao gồm cả trường hợp thành công và trường hợp lỗi 404. Kết quả cho thấy tất cả 6 Test Case đều đạt yêu cầu.

8. Tài liệu tham khảo
Postman: https://www.postman.com/
JSONPlaceholder: https://jsonplaceholder.typicode.com/
Video hướng dẫn Postman: https://www.youtube.com/watch?v=MFxk5BZulVU
