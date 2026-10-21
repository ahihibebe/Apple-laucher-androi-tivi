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
