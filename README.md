# VietLauncher – Launcher Android TV tiếng Việt

Cách lấy file APK (không cần cài Android Studio):
1. Tạo repo mới trên GitHub, tải toàn bộ thư mục này lên (giữ nguyên thư mục `.github`).
2. Vào tab **Actions** → **Build APK** → **Run workflow**.
3. Khi chạy xong, tải APK ở mục **Artifacts** (giải nén file zip).
4. Cài lên TV:  adb connect <IP-TV>:5555  rồi  adb install app-debug.apk
5. Bấm nút Home trên remote, chọn "Màn hình chính" → "Luôn luôn" để đặt làm launcher mặc định.

Muốn đổi các app trên dock: sửa mảng DOCK_PREF trong MainActivity.java.

## Tùy chỉnh (nút "Tùy chỉnh" ở góc trên bên phải)
- **Hình nền**: 5 nền có sẵn, hoặc chọn ảnh từ thiết bị.
  Nếu TV không có trình chọn tệp, chép ảnh vào thư mục ứng dụng bằng ADB:
  adb push anh.jpg /sdcard/Android/data/vn.launcher.tv/files/wallpapers/
  rồi vào Tùy chỉnh → Hình nền → "Chọn ảnh từ thư mục ứng dụng".
- **Âm thanh di chuyển**: bật/tắt tiếng "tách" khi chuyển qua lại giữa các mục.

## Cập nhật
- Nút **Cài đặt** (có icon) mở menu: Hình nền, Âm thanh di chuyển, Cài đặt hệ thống của TV.
- Dưới đồng hồ có dòng lịch âm: [ Âm lịch: ngày/tháng - Can Chi ].
- Ô ứng dụng trong suốt 60% (hằng số TILE_ALPHA trong MainActivity.java), bo góc 32dp (tile_bg.xml).

## Icon và thông tin
- Icon ứng dụng + banner (hiện trong menu ứng dụng của Android TV): quả táo trắng trên nền đỏ (res/drawable/ic_launcher.xml, banner.xml).
- Cài đặt → **Thông tin**: nội dung đọc từ res/values/info.xml (info_url = http://facebook.com/TruongAlone).

## Bản cập nhật mới
- Lịch âm nằm ngay dưới ngày dương lịch (cùng một cột, cạnh đồng hồ).
- Ô ứng dụng: bo góc nhẹ (14dp), nền trắng trong suốt giống nút Cài đặt.
- Menu Cài đặt: Cài đặt hệ thống (đầu tiên), Hình nền, Âm thanh, Thông tin — đều có icon.
- Icon launcher hiện trong lưới "Tất cả ứng dụng" (bấm vào để mở menu Cài đặt).
- Icon/banner ứng dụng: quả táo trắng trên nền trắng trong suốt.

## Bản cập nhật (Home, thông báo, tên, nhấn giữ, viền, hiệu ứng)
- Sửa lỗi bấm Home bị nhấp nháy: không dựng lại giao diện khi danh sách app không đổi.
- Nút đầu thanh trên: mặc định "Tìm kiếm giọng nói" (Google Assistant); hiện "USB đã kết nối" khi cắm USB; hiện bài hát khi đang phát nhạc (cấp quyền tại Cài đặt → Hiện bài hát đang phát).
- Lời chào kèm tên (Cài đặt → Tên hiển thị: bật/tắt, đổi tên).
- Nhấn giữ OK trên ô ứng dụng: Di chuyển / Ẩn / Xóa. Ứng dụng đã ẩn hiện lại trong Cài đặt → Ứng dụng đã ẩn.
- Ô trong "Tất cả ứng dụng" có thêm viền bao ngoài mờ hơn.
- Mở ứng dụng có hiệu ứng phóng to mượt từ ô ứng dụng.

## Bản cập nhật lớn
- Sửa lỗi menu không đóng: mọi menu tự đóng khi bấm Home / mở app, luôn chỉ có 1 menu.
- Thời tiết (Open-Meteo): nhiệt độ, nắng/mưa, thấp–cao, % mưa; vị trí tự nhận bằng GPS/mạng (cần quyền vị trí), nếu không có thì theo IP.
- Cài đặt → Đặt launcher mặc định: hệ thống hỏi / hướng dẫn ADB Wi-Fi, USB (tự điền IP TV, nút Sao chép lệnh) / khôi phục launcher gốc.
- Cài đặt → Ngôn ngữ: Tiếng Việt / English.
- Khung 2 kênh TV phía trên thanh app (FPT Play, VTVgo, TV360...); nhấn giữ để đổi ứng dụng.
- Thanh dung lượng + RAM dưới giờ.
- Đếm ngược ngày lễ Việt Nam kèm trái tim đỏ.
- Thông báo đỏ mùng 1, 14, 15, cuối tháng âm lịch.
- Cài đặt → Hiển thị: bật/tắt từng mục trên.

## Cập nhật: nút tắt TV, FPT Play, viền sáng
- Nút "Tắt TV" (icon nguồn) cạnh nút Cài đặt, bật/tắt trong Cài đặt → Hiển thị. Dùng ADB nội bộ gửi phím SLEEP (chuyển TV sang chế độ chờ).
- Đã bỏ hàng kênh. Cài đặt → Khung kênh TV → "Mở FPT Play vào mục Truyền hình": đặt liên kết hoặc dãy phím điều hướng (ví dụ RIGHT RIGHT CENTER); có mục dò liên kết của FPT Play.
- Ô ứng dụng đang chọn: viền dày 6dp nhấp nháy đỏ ↔ trắng.
