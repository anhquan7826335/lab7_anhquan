# Quản lý thư viện nhạc trực tuyến

Báo cáo mô tả các chức năng quản lý **User**, **Song** và **Artist**, cùng cách kiểm thử các chức năng bằng Postman.

Base URL: `http://localhost:8080`

> Các controller hiện tại dùng Spring MVC/Thymeleaf, không phải REST API trả JSON. Trong Postman, gửi dữ liệu tạo/cập nhật bằng **Body → x-www-form-urlencoded**. Những request `GET` hiển thị trang HTML; thao tác tạo, sửa, xóa sẽ redirect về trang danh sách.

### 1. User

Các thuộc tính của User: `id` (tự sinh), `username`, `email`, `role`.

#### Kiểm thử User bằng Postman

| Chức năng | Method | URL | Tham số / body |
|---|---|---|---|
| Xem danh sách | GET | `/users` | Không cần |
| Tìm kiếm theo username hoặc email | GET | `/users/search?keyword=admin` | Query `keyword` |
| Tạo mới | POST | `/users/create` | `username`, `email`, `role` |
| Cập nhật | POST | `/users/update/{id}` | `username`, `email`, `role` |
| Xóa | GET | `/users/delete/{id}` | Thay `{id}` bằng ID của User |


| Key | Value mẫu |
|---|---|
| `username` | `nguyenvana` |
| `email` | `nguyenvana@example.com` |
| `role` | `USER` |

Khi cập nhật hoặc xóa, thay `{id}` trong URL bằng ID User cần thao tác. Với tạo/cập nhật, nhập các trường trong bảng trên ở **Body → x-www-form-urlencoded**.

#### Ảnh minh họa User
GET:
<img width="959" height="599" alt="image" src="https://github.com/user-attachments/assets/ca4f6632-f950-4db5-8565-b467ac36eb6e" />
<img width="959" height="599" alt="image" src="https://github.com/user-attachments/assets/a4c29b20-e0bc-43e1-ab8e-ef4810579fc0" />

Post:
<img width="959" height="580" alt="image" src="https://github.com/user-attachments/assets/df6a01f9-10ab-471e-a9c4-d81409b15b02" />

<img width="958" height="599" alt="image" src="https://github.com/user-attachments/assets/cd177c88-0dc7-464e-a782-24864e5bc929" />


### 2. Song

Các thuộc tính của Song: `id` (tự sinh), `title`, `artist`, `genre`, `releaseYear`, `audioFilePath`, `duration`.

#### Kiểm thử Song bằng Postman

| Chức năng | Method | URL | Tham số / body |
|---|---|---|---|
| Xem danh sách | GET | `/songs` | Không cần |
| Tìm kiếm | GET | `/songs/search?keyword=love` | Query `keyword` |
| Tạo mới | POST | `/songs/create` | `title`, `artist`, `genre`, `releaseYear`, `audioFilePath`, `duration` |
| Cập nhật | POST | `/songs/update/{id}` | Các trường Song cần cập nhật |
| Xóa | POST | `/songs/delete/{id}` | Thay `{id}` bằng ID của Song; không cần body |

Ví dụ body tạo Song:

| Key | Value mẫu |
|---|---|
| `title` | `Example Song` |
| `artist` | `Example Artist` |
| `genre` | `Pop` |
| `releaseYear` | `2024` |
| `audioFilePath` | `audio/example.mp3` |
| `duration` | `03:45` |

Khi cập nhật hoặc xóa, thay `{id}` trong URL bằng ID Song cần thao tác. Với tạo/cập nhật, nhập các trường trong bảng trên ở **Body → x-www-form-urlencoded**; `releaseYear` là số nguyên.

#### Ảnh minh họa Song
Get:
<img width="959" height="599" alt="image" src="https://github.com/user-attachments/assets/1b615ccb-e4ed-4259-b84c-be2cc9f5f140" />
<img width="959" height="599" alt="image" src="https://github.com/user-attachments/assets/e6ec9cda-1687-40e5-aa20-d9dd58bad969" />

Post:
<img width="959" height="599" alt="image" src="https://github.com/user-attachments/assets/a052a30a-1ac4-4b12-a6e0-f6ef4d056207" />
<img width="959" height="599" alt="image" src="https://github.com/user-attachments/assets/572e5127-8a95-439a-b648-c82781fd605b" />


