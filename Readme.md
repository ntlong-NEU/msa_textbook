# GIÁO TRÌNH PHÂN TÍCH THỐNG KÊ NHIỀU CHIỀU VỚI PYTHON  
**(Multivariate Statistical Analysis with Python)**

---

## 📋 GIỚI THIỆU
Dự án biên soạn giáo trình điện tử sử dụng **Jupyter Book**.  
Sách hỗ trợ xuất bản ra hai định dạng: **Website (HTML)** để đọc online và **PDF (LaTeX)** để in ấn.

**Nhóm tác giả:**
- TS. Nguyễn Mạnh Thế  
- TS. Vũ Thị Bích Ngọc  
- TS. Nguyễn Tuấn Long  

---

## 🛠 PHẦN 1: CHUẨN BỊ MÔI TRƯỜNG
Trước khi thực hiện bất kỳ lệnh nào, hãy đảm bảo bạn đang ở thư mục gốc và đã kích hoạt môi trường ảo.

1. Mở Terminal trong VS Code  
2. Kích hoạt môi trường ảo `msa_env`:

```powershell
.\msa_env\Scripts\activate
```

*(Dấu hiệu thành công: Đầu dòng lệnh có chữ `(msa_env)` màu xanh)*

---

## 🌐 PHẦN 2: XUẤT BẢN WEBSITE (HTML)
Dùng để xem trước nội dung, kiểm tra công thức toán và code Python.

**Lệnh Build:**
```powershell
.\msa_env\Scripts\jupyter-book.exe build noi_dung
```

**Xem kết quả:**
- Vào thư mục: `noi_dung/_build/html`  
- Mở file `index.html`  
*(Khuyên dùng "Live Server" của VS Code để xem đẹp nhất)*

---

## 📄 PHẦN 3: XUẤT BẢN PDF (IN ẤN)

### Cách 1: Tự động (Khuyên dùng khi đã cài đủ Tools)
Yêu cầu máy phải có sẵn **Perl** và **Latexmk**

```powershell
.\msa_env\Scripts\jupyter-book.exe build noi_dung --builder pdflatex
```

---

### Cách 2: Thủ công (Chắc chắn thành công 100%)

**Bước 1: Tạo mã nguồn LaTeX**
```powershell
.\msa_env\Scripts\jupyter-book.exe build noi_dung --builder pdflatex
```

*(Bỏ qua các lỗi báo đỏ ở cuối, chỉ cần thấy dòng “The LaTeX files are in...” là được)*

---

**Bước 2: Di chuyển vào thư mục in ấn**
```powershell
cd noi_dung\_build\latex
```

---

**Bước 3: Biên dịch ra PDF (chạy 2 lần liên tiếp)**
```powershell
xelatex Giao_trinh_PTTK_Da_bien.tex
```

*(Nếu không thấy file tên như trên, dùng `dir` hoặc `ls` để tìm file `.tex` và thay thế)*

---

## 🧹 PHẦN 4: SỬA LỖI & DỌN DẸP (TROUBLESHOOTING)

### 1. Lệnh dọn dẹp (Clean)
Xóa sạch các file build cũ để tạo lại từ đầu.

**Cách dùng lệnh:**
```powershell
.\msa_env\Scripts\jupyter-book.exe clean noi_dung
```

**Cách thủ công (sạch nhất):**
- Vào thư mục `noi_dung`
- Xóa hoàn toàn thư mục `_build`

---

### 2. Các lỗi thường gặp

| Lỗi | Nguyên nhân & Cách khắc phục |
|-----|-----------------------------|
| **PermissionError (WinError 32)** | Đang mở file PDF hoặc thư mục `_build` → Đóng file, đóng VS Code/Explorer rồi chạy lại |
| **Failed to run make.bat (WinError 2)** | Thiếu Perl/Make → Dùng cách thủ công (Cách 2) |
| **Tên file "projectnamenotset"** | Cache chưa xóa → Xóa `_build` rồi build lại |

---

## 📂 CẤU TRÚC THƯ MỤC QUAN TRỌNG

- `noi_dung/` → Nội dung sách  
- `noi_dung/_config.yml` → Cấu hình (tên sách, tác giả, font...)  
- `noi_dung/_toc.yml` → Mục lục  
- `noi_dung/logo.png` → Logo hiển thị  
