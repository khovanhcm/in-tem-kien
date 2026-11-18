# In tem kiện A5

Trang in tem kiện khổ **A5 ngang** cho Kho vận Hồ Chí Minh, chạy trên GitHub Pages.

## Cách dùng
1. Nhập **Mã kho** → trang tự hiện Tên kho và Lộ trình.
2. Nhập **Số kiện** và **Loại hàng hoá**.
3. Nhiều kho một lần: **Tải file Excel mẫu** → điền cột Mã kho, Số kiện (thêm cột "Loại hàng hoá" nếu cần) → **Nhập file Excel**.
4. Bấm **In ngay** (in luôn kho đang nhập), hoặc **Enter / Thêm vào danh sách** để gom nhiều kho rồi bấm **In tất cả**.

Mỗi kho in số tem bằng số kiện, đánh số 1/N, 2/N … N/N. Ngày in lấy theo ngày máy tính.

## Bố cục tem (theo sheet "BỐ CỤC")
Tem chỉ in giá trị (không in nhãn mục), mọi ô canh giữa, đen trắng.

| Cột trái (68%) | Cột phải (32%) |
|---|---|
| Dải đen: LOẠI HÀNG HOÁ | Dải đen: Ngày in |
| Lộ trình | SỐ KIỆN |
| **Mã kho** (to tối đa) | **1**/10 (to tối đa, một dòng) |
| Tên kho | |

## Quy tắc dữ liệu
- Nguồn: Google Sheets "TUYẾN GNNB TGDĐ-ĐMX-AK-AVA", sheet **Tuyến Tổng hợp**, xuất ra file `tuyen.csv` trong repo.
- Tên kho = cột C (TÊN KHO) theo Mã kho (cột B).
- Lộ trình: nếu cột K (Hình thức vận chuyển) = **GNNB** → in cột I (TÊN KTT PHỤ TRÁCH); ngược lại → in **"Nhất Tín"**.

Cập nhật `tuyen.csv` khi file tuyến thay đổi: nhờ Claude chạy lại, hoặc tự tạo file CSV 4 cột `MA_KHO,TEN_KHO,TEN_KTT_PHU_TRACH,HINH_THUC_VAN_CHUYEN` rồi upload ghi đè.

## In thẳng ra máy in (không hiện hộp thoại)
1. Windows: Cài đặt → Bluetooth & thiết bị → **Máy in & máy quét** → chọn máy in → **Đặt làm mặc định** (tắt "Để Windows quản lý máy in mặc định").
2. Lần đầu in: chọn khổ **A5**, hướng **Ngang**, lề **Không có**, bỏ tích "Đầu trang và chân trang".
3. Tạo lối tắt Chrome → chuột phải → Properties → ô **Target** thêm vào cuối: ` --kiosk-printing` → mở trang bằng lối tắt này. Bấm in là Chrome in thẳng ra máy in mặc định.
