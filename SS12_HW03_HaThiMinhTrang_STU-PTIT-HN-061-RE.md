# Bài 3: Sinh mã nguồn API Spring Boot từ tài liệu SRS

---

## 1. Prompt 1

Hãy đóng vai là một Senior Backend Developer có nhiều kinh nghiệm xây dựng hệ thống tài chính/ngân hàng bằng Java Spring Boot. Dựa trên tài liệu SRS eKYC của ABC Bank, hãy sinh mã nguồn hoàn chỉnh cho API endpoint 'Đăng ký mở tài khoản cơ bản'.

Yêu cầu kỹ thuật:

Cấu trúc thiết kế 3 lớp bao gồm đầy đủ các class:

Account (Entity)

AccountRequestDTO và AccountResponseDTO (Data Transfer Object)

AccountRepository (Interface kế thừa JpaRepository)

AccountService (Interface) và AccountServiceImpl (Implementation)

AccountController (REST Controller với endpoint POST /api/v1/accounts/register)

Chất lượng Code:

Áp dụng Bean Validation cho DTO: @NotBlank, @Email, và sử dụng @Pattern để custom validation cho số CCCD (citizenId) phải đúng định dạng 12 chữ số.

Dữ liệu đầu vào (Request): fullName, phone, email, citizenId.

Dữ liệu đầu ra (Response): accountId, accountNumber, status (PENDING/ACTIVE).

Phải có JavaDoc giải thích các class/method và comment bằng tiếng Việt trong các đoạn logic xử lý bên trong Service.

Hãy viết toàn bộ mã nguồn của từng file một cách tường minh trong các block code Markdown.

## 2. Prompt 2

Cảm ơn bạn. Để hoàn thiện tài liệu bàn giao kỹ thuật, hãy viết mã Mermaid để vẽ một Architecture Diagram (Sequence Diagram hoặc Flowchart) mô tả luồng đi của dữ liệu từ:
Client (Mobile App) -> AccountController -> AccountService -> AccountRepository -> Database (MySQL/PostgreSQL), sau đó phản hồi ngược lại cho Client.
Đảm bảo hiển thị rõ bước kiểm tra dữ liệu đầu vào (Validation) diễn ra ở đâu.

## 3. Prompt 3

Mã nguồn rất tốt, tuy nhiên tôi muốn tối ưu thêm một chút để đảm bảo an toàn nghiệp vụ ngân hàng:

Hãy bổ sung thêm logic kiểm tra vào AccountServiceImpl: Nếu email hoặc citizenId đã tồn tại trong cơ sở dữ liệu, hãy ném ra một ngoại lệ tùy chỉnh (BadRequestException hoặc DuplicateResourceException).

Cập nhật lại AccountController để xử lý ngoại lệ này và trả về mã lỗi HTTP 400 Bad Request kèm thông điệp lỗi rõ ràng.
Hãy viết lại đoạn code của ServiceImpl và Controller sau khi đã tối ưu.
