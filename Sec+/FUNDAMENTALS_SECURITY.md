# FUNDAMENTALS OF SECURITY

---

## 1. INFORMATION SECURITY VS INFORMATION SYSTEM SECURITY

| Tiêu chí | **Information Security** | **Information System Security** |
|----------|--------------------------|----------------------------------|
| **Phạm vi** | Bảo vệ dữ liệu (data) ở mọi dạng | Bảo vệ toàn bộ hệ thống (Hardware + Software + Data + People) |
| **Trọng tâm** | Confidentiality, Integrity, Availability của thông tin | Bảo vệ hạ tầng vận hành thông tin |
| **Ví dụ** | Mã hóa file, kiểm soát truy cập dữ liệu | Firewall, IDS/IPS, Backup hệ thống |
| **Mối đe dọa** | Đánh cắp dữ liệu, rò rỉ thông tin | Tấn công DDoS, lỗi phần cứng, virus phá hủy hệ thống |
| **Biện pháp** | Encryption, Digital Signatures, DRM | Firewall, Antivirus, RAID, Redundancy, Failover |

> 💡 **Mẹo nhớ:**
> - **Information Security** = Bảo vệ **CÁI GÌ** (What) – Dữ liệu
> - **Information System Security** = Bảo vệ **LÀM THẾ NÀO** (How) – Hệ thống vận hành

---

## 2. CIA TRIAD

CIA Triad là **nền tảng** của mọi chính sách bảo mật.

### 2.1. Confidentiality – Bảo mật (C)

| Yếu tố | Mô tả |
|--------|-------|
| **Định nghĩa** | Đảm bảo chỉ những người được ủy quyền mới có thể truy cập thông tin |
| **Mục tiêu** | Ngăn chặn xâm nhập trái phép |
| **Cơ chế** | Mã hóa, kiểm soát truy cập, xác thực |
| **Vi phạm** | Rò rỉ thông tin, đánh cắp dữ liệu |

#### Biện pháp bảo vệ Confidentiality

| Biện pháp | Mô tả |
|-----------|-------|
| **Mã hóa (Encryption)** | AES, RSA |
| **Kiểm soát truy cập (Access Control)** | ACL, RBAC |
| **Xác thực (Authentication)** | Username/Password, MFA |
| **Phân loại dữ liệu (Data Classification)** | Public, Internal, Confidential, Top Secret |

---

### 2.2. Integrity – Toàn vẹn (I)

| Yếu tố | Mô tả |
|--------|-------|
| **Định nghĩa** | Đảm bảo dữ liệu không bị thay đổi trái phép hoặc không chính xác |
| **Mục tiêu** | Dữ liệu chính xác, đáng tin cậy (VD: Số dư tài khoản ngân hàng không bị sửa) |
| **Cơ chế** | Hashing, Checksum, Digital Signature (SHA-256, MD5 cũ) |
| **Vi phạm** | Dữ liệu bị sửa đổi, giả mạo (VD: Hacker thay đổi hóa đơn từ $100 → $1000) |

#### Biện pháp bảo vệ Integrity

| Biện pháp | Mô tả |
|-----------|-------|
| **Hashing (Băm dữ liệu)** | SHA-256, SHA-3 |
| **Chữ ký số (Digital Signature)** | RSA, ECDSA |
| **Logging & Auditing** | Ghi lại mọi thay đổi |
| **ACID Properties trong Database** | Atomicity, Consistency, Isolation, Durability |
| **Immutable Storage** | Dữ liệu chỉ đọc, không thể sửa |

---

### 2.3. Availability – Sẵn sàng (A)

| Yếu tố | Mô tả |
|--------|-------|
| **Định nghĩa** | Đảm bảo hệ thống và dữ liệu luôn sẵn sàng khi người dùng cần |
| **Mục tiêu** | Hệ thống hoạt động 24/7/365 (VD: Website không bao giờ down) |
| **Cơ chế** | Redundancy, Backup, Failover (RAID, Load Balancer) |
| **Vi phạm** | DDoS, lỗi phần cứng, ransomware (VD: Trang web không truy cập được) |

#### Biện pháp bảo vệ Availability

| Biện pháp | Mô tả |
|-----------|-------|
| **Redundancy (Dự phòng)** | RAID 1, 5, 10 |
| **Backup (Sao lưu)** | Full, Incremental, Differential |
| **Failover (Chuyển đổi dự phòng)** | Primary → Secondary |
| **DDoS Protection** | Cloudflare, AWS Shield |
| **Disaster Recovery Plan (DRP)** | Quy trình phục hồi thảm họa |

---

## 3. NON-REPUDIATION – KHÔNG THỂ CHỐI BỎ

| Yếu tố | Mô tả |
|--------|-------|
| **Định nghĩa** | Đảm bảo một người **không thể phủ nhận** hành động của mình (không thể nói *"Tôi không làm việc đó"*) |
| **Cơ chế chứng minh** | • Digital Signature (Chữ ký số) <br> • Audit Logs (Nhật ký hệ thống) <br> • Biometric Logs (Vân tay, khuôn mặt) |

---

## 4. CIANA PENTAGON – MỞ RỘNG CIA TRIAD

CIANA Pentagon là mô hình mở rộng, bổ sung thêm 2 yếu tố:

| Yếu tố | Viết tắt | Ý nghĩa | Giải thích ngắn gọn |
|--------|----------|---------|----------------------|
| **Confidentiality** | C | Bảo mật | Chỉ người ủy quyền mới xem được |
| **Integrity** | I | Toàn vẹn | Dữ liệu không bị sửa đổi trái phép |
| **Availability** | A | Sẵn sàng | Hệ thống luôn hoạt động |
| **Non-Repudiation** | N | Không chối bỏ | Không thể phủ nhận hành động |
| **Accountability** | A | Trách nhiệm giải trình | Ai làm gì, lúc nào, đều ghi lại |

---

## 5. TRIPLE A (AAA)

### 5.1. Authentication – Xác thực

**Định nghĩa:** Xác minh danh tính của người dùng.

**Các yếu tố xác thực:**
- **Knowledge** – Cái bạn biết (Password, PIN)
- **Possession** – Cái bạn có (Token, Smart Card)
- **Inherence** – Cái bạn là (Vân tay, khuôn mặt)

| Phương thức | Mô tả |
|-------------|-------|
| **Single-Factor Authentication (SFA)** | Chỉ cần 1 yếu tố (VD: Password) |
| **Two-Factor Authentication (2FA)** | Cần 2 yếu tố (VD: Password + OTP) |
| **Multi-Factor Authentication (MFA)** | Cần từ 2+ yếu tố, ưu tiên dùng 3 yếu tố khác nhau |
| **Biometric Authentication** | Fingerprint, Face ID, Voice Recognition, Iris Scan |
| **SSO (Single Sign-On)** | Đăng nhập 1 lần, truy cập nhiều hệ thống (VD: Google SSO, Microsoft Entra ID) |

---

### 5.2. Authorization – Ủy quyền

**Định nghĩa:** Xác định quyền hạn của người dùng **sau khi đã xác thực**.

| Mô hình | Giải thích | Ví dụ |
|---------|------------|-------|
| **DAC** (Discretionary AC) | Chủ sở hữu tự phân quyền | File Owner cho phép user khác đọc |
| **MAC** (Mandatory AC) | Hệ thống quy định cứng | Military: Top Secret, Secret, Unclassified |
| **RBAC** (Role-Based AC) | Phân quyền theo vai trò | Admin, Manager, Staff, Intern |
| **ABAC** (Attribute-Based AC) | Phân quyền theo thuộc tính | User from HR, Device Compliant, Time 8-5 |
| **PBAC** (Policy-Based AC) | Phân quyền theo chính sách | Dynamic, Context-aware |

#### Ví dụ Roles (RBAC)

| Role | Permissions | Resources |
|------|-------------|-----------|
| **Administrator** | `[READ, WRITE, DELETE, EXECUTE]` | `[All]` |
| **Developer** | `[READ, WRITE, EXECUTE]` | `[/source_code, /project]` |
| **HR_Staff** | `[READ, WRITE]` | `[/hr_data]` |
| **Intern** | `[READ]` | `[/project]` + `[READ_ONLY]` |

---

### 5.3. Accounting – Lưu vết / Ghi nhật ký

**Định nghĩa:** Ghi lại toàn bộ hoạt động của người dùng để kiểm tra và truy xuất.

---

## 6. SECURITY CONTROLS

### 6.1. 4 CATEGORIES (THEO BẢN CHẤT)

#### 6.1.1. Technical Controls (Kỹ thuật)

> Là các biện pháp dùng công nghệ (phần cứng, phần mềm). Hoạt động tự động, 24/7.

| Ví dụ |
|-------|
| Tường lửa (Firewall) |
| Mã hóa (Encryption) |
| IDS/IPS |
| Antivirus/EDR (Endpoint Detection and Response) |
| MFA |
| VPN |
| SIEM (Security Information and Event Management) |
| Access Control Lists (ACL) |

- ✅ **Điểm mạnh:** Tự động, nhanh, không nghỉ.
- ❌ **Điểm yếu:** Cần cập nhật, bảo trì. Có thể bị bypass kỹ thuật.

---

#### 6.1.2. Managerial Controls (Quản lý)

> Là các biện pháp liên quan đến chính sách, chiến lược, quản trị rủi ro. Định hướng toàn bộ hệ thống.

| Ví dụ |
|-------|
| Chính sách bảo mật (Security Policies) |
| Đánh giá rủi ro (Risk Assessment) |
| Kế hoạch duy trì kinh doanh (BCP) |
| Kế hoạch phục hồi thảm họa (DRP) |
| Đào tạo nhận thức bảo mật |
| Khung tuân thủ (ISO 27001, NIST, GDPR) |

- ✅ **Điểm mạnh:** Tạo nền tảng và định hướng.
- ❌ **Điểm yếu:** Chỉ là giấy tờ nếu không thực thi.

---

#### 6.1.3. Operational Controls (Vận hành)

> Là các quy trình và thủ tục do con người thực hiện hàng ngày.

| Ví dụ |
|-------|
| Quy trình cập nhật bản vá (Patch Management) |
| Quy trình quản lý thay đổi (Change Management) |
| Quy trình sao lưu và phục hồi (Backup/Restore) |
| Quy trình ứng phó sự cố (Incident Response) |
| Rà soát quyền truy cập định kỳ |
| Xem xét log thủ công |

- ✅ **Điểm mạnh:** Linh hoạt, xử lý được tình huống phức tạp.
- ❌ **Điểm yếu:** Phụ thuộc con người, dễ sai sót.

---

#### 6.1.4. Physical Controls (Vật lý)

> Là các biện pháp bảo vệ cơ sở vật chất, phần cứng và con người.

| Ví dụ |
|-------|
| Khóa cửa, thẻ từ |
| Camera giám sát (CCTV) |
| Bảo vệ an ninh |
| Hàng rào, cổng |
| Hệ thống chữa cháy |
| Máy phát điện dự phòng, UPS |
| Tủ khóa rack server |

- ✅ **Điểm mạnh:** Lớp bảo vệ đầu tiên, ngăn truy cập trực tiếp.
- ❌ **Điểm yếu:** Chi phí đầu tư cao, chỉ bảo vệ được vật lý.

---

### 6.2. 6 TYPES (THEO CHỨC NĂNG)

| Loại | Chức năng | Ví dụ |
|------|-----------|-------|
| **Preventative** (Ngăn chặn) | Ngăn sự cố xảy ra, can thiệp từ trước | Firewall chặn IP xấu từ cổng vào |
| **Deterrent** (Răn đe) | Tác động tâm lý, làm kẻ tấn công do dự | Camera giả, biển báo |
| **Detective** (Phát hiện) | Phát hiện sự cố trong khi hoặc sau khi xảy ra | IDS/SIEM |
| **Corrective** (Khắc phục) | Phục hồi và sửa chữa sau khi sự cố xảy ra | Backup & Restore, Patch |
| **Compensating** (Bù trừ) | Biện pháp tạm thời khi không thể áp dụng biện pháp chính | MFA thay cho password yếu |
| **Directive** (Chỉ đạo) | Hướng dẫn, ra lệnh, quy định những điều phải làm | Security Policy, SOP |

---

## 7. ZERO TRUST

> **Nguyên lý cốt lõi:** *"Never Trust, Always Verify"*

- Không tin bất kỳ ai, bất kỳ thiết bị nào, kể cả đang ở trong mạng nội bộ.
- Mạng luôn bị coi là đã bị xâm nhập.
- Mọi yêu cầu truy cập đều phải được xác thực, phân quyền và ghi log từ đầu đến cuối.

---

### 7.1. KIẾN TRÚC ZERO TRUST

#### A. CONTROL PLANE (Lớp điều khiển – "BỘ NÃO")

Đây là nơi đưa ra mọi quyết định. Gồm 4 thành phần:

##### 1. Adaptive Identity (Danh tính thích ứng)
- Xác thực không cố định, thay đổi theo ngữ cảnh.
- Ví dụ: User đăng nhập từ IP lạ vào ban đêm → Yêu cầu thêm MFA.
- Đánh giá rủi ro theo thời gian thực.

##### 2. Threat Scope Reduction (Giảm phạm vi đe dọa)
- Chia mạng thành nhiều vùng cực nhỏ (Micro-segmentation).
- Mỗi vùng có quyền truy cập riêng, không ai tự do di chuyển.
- Nếu một vùng bị xâm nhập, các vùng khác vẫn an toàn.

##### 3. Policy-driven Access Control (Truy cập theo chính sách động)
- Chính sách được đánh giá real-time, không phải quyền tĩnh.
- Khi ngữ cảnh thay đổi (vị trí, thiết bị, hành vi), quyền thay đổi theo.
- Ví dụ: Nếu user thử tải 1000 file trong 1 phút → Lập tức thu hồi quyền.

##### 4. Secured Zones (Các vùng an toàn)
- Phân chia môi trường theo mức độ nhạy cảm.
- Ví dụ: Public zone, Internal zone, HR zone, PCI zone, Database zone.
- Mỗi zone có yêu cầu bảo mật khác nhau.

---

#### B. DATA PLANE (Lớp dữ liệu – "CÁNH TAY")

Đây là nơi **thực thi** các quyết định từ Control Plane. Gồm 4 thành phần:

##### 1. Subject/System (Chủ thể/Hệ thống)
- Người dùng, thiết bị, hoặc ứng dụng đang yêu cầu truy cập.
- Gửi thông tin lên Policy Engine để đánh giá.

##### 2. Policy Engine (Cỗ máy chính sách)
- Nhận request từ Subject.
- Đánh giá dựa trên: Danh tính, thiết bị, vị trí, thời gian, độ nhạy của tài nguyên.
- Tính toán **Trust Score** (điểm tin cậy).
- Ra quyết định: **ALLOW** (cho phép) hoặc **DENY** (từ chối).

##### 3. Policy Administrator (Người quản trị chính sách)
- Tạo, cập nhật, quản lý các chính sách.
- Đồng bộ chính sách với Policy Engine.
- Thường là hệ thống hoặc con người có quyền cao nhất.

##### 4. Policy Enforcement Points (PEPs – Điểm thực thi)
- Nơi chặn và kiểm tra trước khi cho phép truy cập.
- Ví dụ: Firewall, API Gateway, Proxy, VPN Gateway.
- Nhận lệnh từ Policy Engine: **ALLOW** → cho đi qua, **DENY** → chặn lại.
- PEPs nằm ở mọi điểm giao tiếp, không chỉ ở biên mạng.

---

### 7.2. LUỒNG HOẠT ĐỘNG CỦA ZERO TRUST
Subject gửi request truy cập tài nguyên
↓

Request được chuyển đến Policy Engine (Control Plane)
↓

Policy Engine kiểm tra Adaptive Identity, thiết bị, vị trí, thời gian
↓

Policy Engine tính Trust Score → ra quyết định ALLOW hoặc DENY
↓

Quyết định được gửi xuống Data Plane
↓

Policy Enforcement Points (PEPs) thực thi:
├── ALLOW → Mở kết nối, cấp quyền tối thiểu
└── DENY → Chặn kết nối, ghi log sự cố
↓

Trong suốt phiên truy cập, hành vi được giám sát liên tục
↓

Nếu có dấu hiệu bất thường → PE đánh giá lại → thu hồi quyền giữa chừng
↓

Hết thời gian phiên (thường vài giờ) → Yêu cầu xác thực lại từ đầu

---

### 7.3. VÍ DỤ THỰC TẾ VỀ ZERO TRUST POLICY

**Tình huống:** Một user muốn truy cập HR Database.

**Điều kiện bắt buộc (ALL):**

- ✅ User thuộc nhóm `HR_Staff` hoặc `IT_Admin`
- ✅ Đã xác thực MFA thành công
- ✅ Thiết bị đang dùng đã được cài bản vá mới nhất, có antivirus và mã hóa ổ đĩa
- ✅ Đang kết nối từ mạng nội bộ công ty hoặc VPN
- ✅ Thời gian truy cập trong giờ làm việc (8h-18h)
- ✅ Hành vi bình thường (không tải quá nhiều dữ liệu cùng lúc)

**Kết quả:**

- Nếu tất cả đều đạt → Policy Engine ra lệnh **ALLOW** cho PEP (VD: API Gateway)
- PEP cho phép request đi qua, nhưng chỉ với quyền **READ** (không có DELETE hay UPDATE)
- Mọi thao tác đều được ghi log đầy đủ để phục vụ điều tra sau này

**Kịch bản bất thường:**

- Sau 30 phút, user bỗng nhiên yêu cầu tải xuống 10,000 file → **Hành vi bất thường**
- Policy Engine lập tức đánh giá lại → hạ Trust Score → gửi lệnh **DENY**
- PEP chặn ngay yêu cầu, không cho tải tiếp
- Hệ thống gửi cảnh báo đến Security Team

---

### 7.4. TÓM TẮT ZERO TRUST

| Thành phần | Vai trò | Chức năng |
|------------|---------|-----------|
| **Control Plane** | "Bộ não" | Quyết định **ALLOW** hay **DENY** |
| **Data Plane** | "Cánh tay" | Thực thi quyết định thông qua PEPs |

**Nguyên tắc cốt lõi:**
- 🔐 Mọi thứ đều phải được xác minh, không có ngoại lệ
- 🌐 Mạng không đáng tin → Micro-segmentation
- 🧠 Danh tính thích ứng + Chính sách động + Giám sát liên tục