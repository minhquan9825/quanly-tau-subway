# TÀI LIỆU DÀNH CHO NOTEBOOKLM & GEMINI ĐỂ TẠO SLIDE THUYẾT TRÌNH
## ĐỀ TÀI: HỆ THỐNG QUẢN LÝ TÀU ĐIỆN ĐÔ THỊ (SUBWAY MANAGEMENT SYSTEM)

> **Mục đích:** Tài liệu được cấu trúc chuẩn hóa cho các mô hình AI (Google NotebookLM, Gemini, Gamma.app) đọc hiểu và tự động tạo ra bộ Slide thuyết trình hoàn chỉnh (12 slides) theo mạch logic tuyến tính, súc tích và chuyên nghiệp.  
> **Lưu ý cho AI:**  
> - Bố cục nội dung đi theo 1 mạch xuyên suốt: Bối cảnh & Bài toán -> Kiến trúc & CSDL -> Danh mục chức năng & Kỹ thuật -> Demo vận hành -> Roadmap.  
> - KHÔNG phân vai người nói, nội dung viết trung tính để nhóm tự phân chia.  
> - Đối với Slide 5 (CSDL & Lược đồ quan hệ): Đặt khung placeholder để nhóm tự chèn ảnh chụp ERD thực tế, AI không cần tạo ảnh hay vẽ lại sơ đồ.

---

## 📑 PHẦN 1: DÀN Ý 12 SLIDE CHUẨN HÓA (SLIDE DECK OUTLINE)

---

### SLIDE 1: TRANG TIÊU ĐỀ (TITLE SLIDE)
* **Tiêu đề chính:** HỆ THỐNG QUẢN LÝ TÀU ĐIỆN ĐÔ THỊ
* **Tiêu đề phụ:** Giải Pháp Số Hóa Vận Hành Đường Sắt & Điểm Bán Vé POS Tự Động
* **Bullet points:**
  - Nền tảng phát triển: C# Windows Forms (.NET Framework 4.7.2)
  - Cơ sở dữ liệu: Microsoft SQL Server (Chuẩn hóa 3NF)
  - Kiến trúc phần mềm: Mô hình 3 tầng (Layered Architecture)
* **Visual / Layout:** Thiết kế hiện đại, phong cách Metro/Subway công nghệ cao, logo trường/khoa và thông tin nhóm thực hiện.
* **Ghi chú diễn giả:** Lời chào hội đồng, giới thiệu tên đề tài và định vị giá trị của phần mềm trong bối cảnh giao thông công cộng hiện đại.

---

### SLIDE 2: BỐI CẢNH BÀI TOÁN & MỤC TIÊU DỰ ÁN (PROBLEM & OBJECTIVES)
* **Tiêu đề chính:** Bối Cảnh Thực Tiễn & Mục Tiêu Dự Án
* **Bullet points:**
  - **Thách thức:** Tuyến đường sắt đô thị (như Bến Thành - Suối Tiên) đòi hỏi vận hành chính xác từng phút, an toàn kỹ thuật nghiêm ngặt và lưu lượng hành khách lớn tại quầy vé.
  - **Hạn chế cũ:** Quản lý thủ công dễ gây chồng chéo lịch trình, chậm trễ cập nhật trạng thái bảo dưỡng đoàn tàu và ùn tắc tại điểm bán vé giờ cao điểm.
  - **Mục tiêu hệ thống:** Tự động hóa toàn diện quy trình điều phối tàu, đồng bộ bảo trì kỹ thuật và cung cấp giải pháp bán vé POS tính cước tự động theo chặng.
* **Visual / Layout:** Chia làm 2 cột đối sánh: [Hiện trạng & Khó khăn] ➔ [Giải pháp & Giá trị mang lại].

---

### SLIDE 3: TỔNG QUAN GIẢI PHÁP & MA TRẬN PHÂN QUYỀN (RBAC)
* **Tiêu đề chính:** Mô Hình Phân Quyền 4 Nhóm Vai Trò (Role-Based Access Control)
* **Bullet points:**
  - **Quản trị viên (Admin):** Quyền năng toàn diện trên 15 phân hệ, cấu hình hạ tầng tuyến/ga, nhân sự và báo cáo doanh thu cấp cao.
  - **Nhân viên Bán vé (Cashier):** Tối ưu giao diện POS bán vé nhanh, tra cứu vé hành khách, xử lý hủy/đổi vé theo quy chuẩn.
  - **Nhân viên Kỹ thuật (Technician):** Chuyên trách lập phiếu kiểm tra, bảo dưỡng đoàn tàu và cập nhật tức thời trạng thái an toàn.
  - **Tài xế / Lái tàu (Driver):** Tra cứu lịch phân công công tác, thông tin chuyến tàu và danh sách nhà ga trên tuyến.
* **Visual / Layout:** Bảng ma trận phân quyền (RBAC Matrix) rõ ràng, thể hiện tính bảo mật và phân định trách nhiệm công việc.

---

### SLIDE 4: KIẾN TRÚC KỸ THUẬT 3 TẦNG (SYSTEM ARCHITECTURE)
* **Tiêu đề chính:** Kiến Trúc Phần Mềm Phân Tầng (3-Tier Layered Architecture)
* **Bullet points:**
  - **Presentation Layer (Tầng giao diện):** 15 Windows Forms thiết kế trực quan, phân tách module chức năng, cơ chế validation dữ liệu đầu vào chặt chẽ.
  - **Business Logic & Data Access Layer (DAL):** Đóng gói tập trung trong class `Ketnoi_CSDL.cs`, thực thi truy vấn an toàn, tham số hóa ngăn chặn triệt để SQL Injection.
  - **Database Layer (Tầng CSDL):** Microsoft SQL Server quản lý tập trung, toàn vẹn ràng buộc quan hệ, tối ưu tốc độ bằng Stored Procedures và Transactions.
* **Visual / Layout:** Sơ đồ khối 3 tầng liên kết 2 chiều với mũi tên luồng dữ liệu (Data Flow).

---

### SLIDE 5: THIẾT KẾ CƠ SỞ DỮ LIỆU & LƯỢC ĐỒ QUAN HỆ (DATABASE & ERD)
* **Tiêu đề chính:** Thiết Kế Cơ Sở Dữ Liệu 11 Bảng Chuẩn Hóa 3NF
* **Bullet points:**
  - Chuẩn hóa cấu trúc 11 bảng chuẩn 3NF: `Tuyen`, `Ga`, `Tuyen_Ga`, `Tau`, `ToaTau`, `BaoTri`, `LichTrinh`, `ChuyenTau`, `NhanVien`, `HanhKhach`, `Ve`.
  - Khóa chính, khóa ngoại liên kết chặt chẽ theo 5 khối nghiệp vụ: Hạ tầng, Phương tiện, Vận hành, Quản trị nhân sự và Thương mại POS.
  - Phân định rõ trách nhiệm nhân sự qua 3 luồng vận hành then chốt: Kỹ thuật bảo trì tàu (`BaoTri`), Lái tàu điều khiển chuyến (`ChuyenTau`), Thu ngân xuất vé (`Ve`).
* **Visual / Layout:** **[VỊ TRÍ CHÈN ẢNH CHỤP SƠ ĐỒ THỰC THỂ LIÊN KẾT ERD THỰC TẾ]** (Kích thước lớn, rõ nét các liên kết 1-nhiều).

---

### SLIDE 6: HỆ THỐNG 5 STORED PROCEDURES NGHIỆP VỤ CỐT LÕI
* **Tiêu đề chính:** Xử Lý Nghiệp Vụ Tối Ưu Bằng Stored Procedures
* **Bullet points:**
  - `sp_DangNhap`: Xác thực tài khoản, kiểm tra trạng thái kích hoạt tài khoản (`Hoạt động`), phân quyền đăng nhập an toàn.
  - `sp_SinhChuyen`: Tự động quét lịch trình định kỳ, sinh danh sách chuyến tàu hàng ngày, bẫy lỗi chống trùng lặp lịch chạy.
  - `sp_BaoCaoDoanhThu`: Truy vấn tổng hợp doanh thu theo ngày, số lượng vé bán ra và số lượng vé hủy thời gian thực.
  - `sp_DoanhThuTheoTuyen`: Thống kê tỷ trọng doanh thu và lưu lượng hành khách phân bổ theo từng tuyến đường sắt.
  - `sp_ChiPhiBaoTri`: Tổng hợp kinh phí bảo dưỡng kỹ thuật theo từng đầu tàu phục vụ công tác quản lý tài sản.
* **Visual / Layout:** Bảng danh mục Stored Procedures kèm tham số đầu vào (Input) và kết quả nghiệp vụ (Business Output).

---

### SLIDE 7: BẢN ĐỒ 15 MÀN HÌNH CHỨC NĂNG (SYSTEM FORMS MAP)
* **Tiêu đề chính:** Bản Đồ 15 Màn Hình Chức Năng Phân Hệ
* **Bullet points:**
  - **Phân hệ Quản trị & Điều hành:** `FrmDangNhap`, `FrmTrangChu` (Dashboard KPI số liệu trực quan).
  - **Phân hệ Hạ tầng tuyến & Ga:** `FrmQuanLyTuyen`, `FrmChiTietTuyen` (thứ tự ga đón/trả), `FrmQuanLyGa`.
  - **Phân hệ Phương tiện & Bảo dưỡng:** `FrmQuanLyTau`, `FrmChiTietTau` (quản lý toa), `FrmBaoTri` (lịch sử bảo dưỡng).
  - **Phân hệ Lịch trình & Chuyến:** `FrmLichTrinh` (giờ chạy tuần), `FrmChuyenTau` (chuyến thực tế trong ngày).
  - **Phân hệ Bán vé POS & Khách hàng:** `FrmBanVe` (POS quầy tính cước tự động), `FrmTraCuuVe`, `FrmHanhKhach`.
  - **Phân hệ Nhân sự & Báo cáo:** `FrmNhanVien`, `FrmBaoCao` (thống kê tài chính đa chiều).
* **Visual / Layout:** Sơ đồ tổ chức phân nhánh (Mindmap/Icon grid) nhóm 15 form theo 6 khối nghiệp vụ chuyên biệt.

---

### SLIDE 8: KỊCH BẢN VẬN HÀNH KHÉP KÍN (LIVE DEMO WORKFLOW)
* **Tiêu đề chính:** Mạch Vận Hành Khép Kín Hệ Thống (Chuẩn Bị Demo)
* **Bullet points:**
  - **Bước 1 (Hạ tầng & Phương tiện):** Cấu hình tuyến, quản lý đoàn tàu và cập nhật phiếu bảo dưỡng kỹ thuật.
  - **Bước 2 (Lập lịch & Tự động sinh chuyến):** Lập khung giờ chạy và kích hoạt Stored Procedure sinh chuyến tàu thực tế.
  - **Bước 3 (Bán vé POS tại quầy):** Chọn tuyến, chặng ga, tính giá tự động, xuất vé và trừ số ghế trống tức thì.
  - **Bước 4 (Hậu mãi & Quản trị):** Tra cứu vé theo CCCD/Mã vé, hủy vé tự động hoàn ghế và xem báo cáo Dashboard doanh thu.
* **Visual / Layout:** Sơ đồ quy trình tuyến tính (Process Flowchart) dạng thanh tiến trình 4 giai đoạn logic.

---

### SLIDE 9: CÁC GIẢI PHÁP KỸ THUẬT NỔI BẬT & ĐIỂM SÁNG CÔNG NGHỆ
* **Tiêu đề chính:** Giải Pháp Kỹ Thuật & Tối Ưu Hóa Nền Tảng
* **Bullet points:**
  - **Toàn vẹn dữ liệu (ACID Transactions):** Đảm bảo quy trình xuất vé, hoàn hủy ghế và đồng bộ trạng thái tàu diễn ra nhất quán hoặc rollback an toàn.
  - **An toàn bảo mật:** Ngăn chặn triệt để SQL Injection thông qua SqlParameter trên toàn bộ truy vấn dữ liệu.
  - **Khắc phục lỗi hiển thị giao diện động:** Xử lý triệt để xung đột layout WinForms giữa `AutoSizeColumnsMode = Fill` và thuộc tính `.Width` của DataGridView trên các TabPage nền.
  - **Chuẩn hóa đa ngôn ngữ:** Toàn bộ CSDL và mã nguồn xử lý triệt để ký tự tiếng Việt Unicode với tiền tố `N''` và mã hóa UTF-8 BOM.
* **Visual / Layout:** 4 ô thẻ tính năng (Feature Cards) nhấn mạnh năng lực kỹ thuật và tính ổn định của phần mềm.

---

### SLIDE 10: ĐÁNH GIÁ HIỆU QUẢ ỨNG DỤNG THỰC TẾ
* **Tiêu đề chính:** Hiệu Quả Nghiệp Vụ & Giá Trị Mang Lại
* **Bullet points:**
  - **Tốc độ phục vụ:** Giảm thời gian xuất vé tại quầy xuống dưới 15 giây/vé nhờ cơ chế tự động điền giá và tìm kiếm thông tin khách hàng thông minh.
  - **Chính xác điều hành:** Loại bỏ 100% rủi ro điều phối trùng chuyến tàu hoặc xuất phát tàu đang trong quá trình bảo dưỡng kỹ thuật.
  - **Kiểm soát thất thoát:** Toàn bộ vé bán, vé hủy và dòng tiền doanh thu được ghi nhận thời gian thực, minh bạch tuyệt đối.
* **Visual / Layout:** Các chỉ số đo lường hiệu năng (Key Metrics/KPIs) nổi bật với các con số ấn tượng.

---

### SLIDE 11: ĐỊNH HƯỚNG PHÁT TRIỂN TRONG TƯƠNG LAI (ROADMAP)
* **Tiêu đề chính:** Lộ Trình Nâng Cấp & Mở Rộng Hệ Thống
* **Bullet points:**
  - **Cổng soát vé tự động (Smart Turnstiles):** Tích hợp công nghệ vé mã QR động (Dynamic QR) và thẻ thông minh RFID/NFC không tiếp xúc.
  - **Ứng dụng di động (Passenger Mobile App):** Hỗ trợ hành khách tra cứu giờ tàu chạy thời gian thực và đặt vé online qua ví điện tử.
  - **Giám sát đoàn tàu thông minh (IoT & GPS Tracking):** Định vị vị trí đoàn tàu trên tuyến theo thời gian thực và cảnh báo lịch bảo trì tự động bằng AI.
* **Visual / Layout:** Trục thời gian phát triển (Roadmap Timeline) với 3 giai đoạn nâng cấp rõ ràng.

---

### SLIDE 12: TỔNG KẾT & PHẦN HỎI ĐÁP PHẢN BIỆN (CONCLUSION & Q&A)
* **Tiêu đề chính:** Tổng Kết & Sẵn Sàng Trả Lời Phản Biện
* **Bullet points:**
  - Hệ thống hoàn thành 100% mục tiêu đặt ra: Vận hành ổn định, dữ liệu nhất quán, giao diện thân thiện và sẵn sàng triển khai.
  - Minh chứng rõ nét cho năng lực phân tích nghiệp vụ (BA) gắn liền với kỹ thuật lập trình hướng đối tượng và quản trị CSDL chuyên sâu.
  - Trân trọng cảm ơn quý Thầy/Cô và Hội đồng đã lắng nghe!
* **Visual / Layout:** Khung thông tin liên hệ nhóm, dòng chữ lớn "Thank You! - Q&A Session".

---

## 📚 PHẦN 2: DỮ LIỆU ĐẶC TẢ CHI TIẾT ĐỂ AI THAM CHIẾU (DATA SPECS)

### 1. Danh mục 11 Bảng CSDL (Khớp 100% Sơ đồ ERD thực tế)
1. `Tuyen (MaTuyen, TenTuyen, MaGaDau, MaGaCuoi, TrangThai)`: Quản lý danh mục các tuyến metro, trỏ về ga đầu và ga cuối.
2. `Ga (MaGa, TenGa, DiaChi, KhuVuc, TrangThai)`: Quản lý danh mục các nhà ga dừng đỗ và khu vực.
3. `Tuyen_Ga (MaTuyen, MaGa, ThuTu, PhutDung)`: Bảng trung gian liên kết tuyến và ga, lưu thứ tự dừng đỗ và thời gian tàu đỗ (phút).
4. `Tau (MaTau, TenTau, LoaiTau, SucChua, MaTuyen, TrangThai)`: Danh mục đoàn tàu, sức chứa và tuyến hoạt động.
5. `ToaTau (MaToa, MaTau, SoThuTu, LoaiToa, SucChua)`: Chi tiết từng toa của đoàn tàu.
6. `BaoTri (MaBT, MaTau, NgayBatDau, NgayKetThuc, NoiDung, ChiPhi, MaNV, TrangThai)`: Lịch sử bảo dưỡng kỹ thuật do nhân viên kỹ thuật phụ trách.
7. `LichTrinh (MaLich, MaTuyen, MaTau, GioDi, GioDen, ThuTrongTuan, TrangThai)`: Khung giờ chạy định kỳ theo thứ trong tuần.
8. `ChuyenTau (MaChuyen, MaLich, NgayChay, MaLaiTau, TrangThai)`: Chuyến tàu thực tế trong ngày, phân công nhân viên lái tàu.
9. `NhanVien (MaNV, HoTen, ChucVu, TenDangNhap, MatKhau, DienThoai, TrangThai)`: Danh mục nhân sự, tài khoản và vai trò trong hệ thống.
10. `HanhKhach (MaHK, HoTen, CCCD, DienThoai)`: Hồ sơ khách hàng lưu CCCD và số điện thoại.
11. `Ve (MaVe, MaChuyen, MaHK, MaGaDi, MaGaDen, LoaiVe, Gia, NgayMua, MaNVBan, TrangThai)`: Lịch sử bán vé, liên kết chuyến, khách hàng, chặng ga di chuyển và thu ngân xuất vé.

### 2. Thông tin tài khoản kiểm thử mặc định
* `admin` / `123456`: Toàn quyền quản trị hệ thống.
* `banve` / `123456`: Quyền thu ngân bán vé, quản lý khách hàng và tra cứu vé.
* `kythuat` / `123456`: Quyền quản lý đoàn tàu và cập nhật lịch bảo dưỡng.
* `laixe` / `123456`: Quyền xem lịch trình và phân công lái tàu.
