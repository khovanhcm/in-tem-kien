# Ghi chú dự án cho Claude – In tem kiện A5

Đọc file này trước khi sửa.

## Bối cảnh
- Người dùng: quản lý kho vận HCM. Trả lời tiếng Việt, ngắn gọn, thẳng vào việc.
- Yêu cầu gốc: Google Sheets "IN ĐỊA CHỈ IT" id `19C1PQ0vUbDBamoUd_EZk025QQcnc_4Au2neu9nZB68w` (sheet "1.RULE", "BỐ CỤC").
- Dữ liệu tuyến: Google Sheets id `1DXsen120vKs_2xjLW3a4MWV3YDDHtyfK8mzHugw1Ejw`, sheet "Tuyến Tổng hợp" (gid 1063511435). Cột B mã kho, C tên kho, I tên KTT phụ trách, K hình thức vận chuyển.
- `tuyen.csv` sinh từ sheet đó (bỏ mã trùng, giữ dòng đầu). Để cập nhật: đọc lại sheet bằng Google Sheets connector (kết quả lớn được lưu ra file), dựng lại CSV, đẩy lên repo.

## Đã chốt
- Tem A5 ngang, chỉ in giá trị (không nhãn mục), mọi ô canh giữa. Cột trái 68%: dải đen Loại hàng hoá (chữ trắng, in hoa), Lộ trình, Mã kho (to tối đa), Tên kho. Cột phải 32%: dải đen Ngày in, ô xám tiêu đề "SỐ KIỆN", số kiện một dòng "i" to + "/N" nhỏ bằng nửa, to tối đa theo ô. Chữ số dùng Barlow Condensed 800, chữ dùng Barlow; font nằm trong thư mục fonts/ của repo. Dải đen dùng print-color-adjust: exact để in được cả khi tắt "Đồ hoạ nền".
- Nhập nhiều kho bằng Excel: nút "Tải file Excel mẫu" (cột Mã kho, Số kiện) và "Nhập file Excel" (nhận cả file khác mẫu nếu có cột chứa "mã kho"/"kho" và "kiện"/"số lượng"; cột "Loại hàng hoá" không bắt buộc).
- Ngày in = ngày máy tính. Số kiện chạy từ 1 đến N.
- Lộ trình: K = "GNNB" → cột I; ngược lại "Nhất Tín".
- In bằng window.print() theo máy in mặc định của Windows; in không hộp thoại bằng Chrome `--kiosk-printing`.
- Giao diện cùng bộ màu với dashboard đơn Online (nền chàm, thẻ oải hương, Lexend). Tem in đen trắng, Arial đậm.

## Việc còn mở
- Chờ người dùng chạy thử in thật trên máy in kho.
