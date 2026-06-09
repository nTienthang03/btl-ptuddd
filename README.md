# BÀI TẬP LỚN - PHÁT TRIỂN ỨNG DỤNG TRÊN THIẾT BỊ DI ĐỘNG

## Thông tin sinh viên

* **Môn học:** Phát triển ứng dụng trên thiết bị di động - TEE0419
* **Sinh viên thực hiện:** Nguyễn Tiến Thắng
* **Mã sinh viên:** K225480106058
* **Lớp:** K58 KTP
* **Tên bài tập:** Xây dựng ứng dụng di động bằng MIT App Inventor và Android Studio

---

## 1. Mục tiêu bài tập

Bài tập lớn gồm 2 phần chính:

1. Xây dựng ứng dụng bằng **MIT App Inventor**.
2. Xây dựng ứng dụng tương đương bằng **Android Studio**, sử dụng ngôn ngữ **Java**.

Mục tiêu của bài tập là giúp sinh viên hiểu quy trình tạo ứng dụng di động từ mức kéo thả trực quan đến mức lập trình Android gốc. Ngoài ra, bài tập còn yêu cầu tìm hiểu cách thiết kế giao diện, xử lý sự kiện, sử dụng WebView, gọi API, khai báo quyền trong AndroidManifest và tổ chức tài nguyên trong project.

---

# PHẦN 1: ỨNG DỤNG MIT APP INVENTOR

## 2. Giới thiệu App MIT App Inventor

Ứng dụng được xây dựng bằng công cụ MIT App Inventor. App gồm 3 màn hình chính:

* **Screen1:** About - hiển thị thông tin cá nhân và có nút chuyển sang 2 màn hình còn lại.
* **Screen2:** Giải bài toán đơn giản - giải phương trình bậc nhất dạng `ax + b = 0`.
* **Screen3:** WebView - hiển thị một trang web có sẵn, hỗ trợ giao diện điện thoại.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3832ddfa-e4be-4407-9a46-532a84ec2581" />

---


## 3. Quy trình tạo ứng dụng trên MIT App Inventor

### Bước 1: Tạo project

Truy cập trang MIT App Inventor:

```text
https://ai2.appinventor.mit.edu/
```

Sau đó đăng nhập bằng tài khoản Google và tạo project mới:

```text
Projects → Start new project
```

Tên project được đặt theo nội dung bài tập và mã sinh viên:

```text
MIT_GiaiToan_WebView_K225480106058
```

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/970cf6f8-16a8-49b4-89bd-49d1e5031044" />


### Bước 2: Tạo 3 Screen

Trong project, tạo 3 màn hình:

```text
Screen1
Screen2
Screen3
```

Ý nghĩa từng màn hình:

| Screen  | Chức năng                           |
| ------- | ----------------------------------- |
| Screen1 | About, hiển thị thông tin sinh viên |
| Screen2 | Giải phương trình ax + b = 0        |
| Screen3 | Hiển thị trang web bằng WebViewer   |

---

## 4. Thiết kế Screen1 - About

Screen1 dùng để hiển thị thông tin cá nhân và có 2 nút chuyển màn hình.

Các component sử dụng:

| Component             | Mục đích                              |
| --------------------- | ------------------------------------- |
| Label                 | Hiển thị họ tên, MSSV, lớp, môn học   |
| Button                | Chuyển sang màn hình giải toán        |
| Button                | Chuyển sang màn hình WebView          |
| VerticalArrangement   | Sắp xếp các thành phần theo chiều dọc |
| HorizontalArrangement | Sắp xếp 2 nút theo chiều ngang        |

Thông tin hiển thị:

```text
BÀI TẬP LỚN MOBILE
Họ tên: Nguyễn Tiến Thắng
MSSV: K225480106058
Lớp: K58 KTP
Môn học: Phát triển ứng dụng trên thiết bị di động
Tên ứng dụng: App giải toán và WebView
```

Xử lý chuyển màn hình bằng Blocks:

```text
when GiaiToan.Click
do open another screen screenName "Screen2"

when web.Click
do open another screen screenName "Screen3"
```

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e308d662-745a-4087-bf9f-fc6c7612ac04" />


## 5. Thiết kế Screen2 - Giải toán

Screen2 dùng để giải phương trình bậc nhất:

```text
ax + b = 0
```

Các component sử dụng:

| Component | Tên đặt | Mục đích                |
| --------- | ------- | ----------------------- |
| TextBox   | NhapA   | Nhập hệ số a            |
| TextBox   | NhapB   | Nhập hệ số b            |
| Button    | NutGiai | Thực hiện giải toán     |
| Label     | KetQua  | Hiển thị kết quả        |
| Button    | QuayLai | Quay lại màn hình trước |

### Lưu ý khi thiết kế TextBox

Để chữ “Nhập hệ số a” và “Nhập hệ số b” chỉ là chữ mờ gợi ý, cần cấu hình:

```text
Text: để trống
Hint: Nhập hệ số a
NumbersOnly: bật
```

Tương tự với ô nhập b:

```text
Text: để trống
Hint: Nhập hệ số b
NumbersOnly: bật
```

Không được nhập chữ gợi ý vào thuộc tính `Text`, vì khi đó app sẽ hiểu đó là dữ liệu thật.

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f0161585-ef12-40ee-bf0a-73b297c68dda" />


## 6. Logic giải phương trình trong MIT App Inventor

Quy tắc xử lý:

| Trường hợp        | Kết quả                      |
| ----------------- | ---------------------------- |
| a hoặc b rỗng     | Vui lòng nhập đủ a và b      |
| a = 0 và b = 0    | Phương trình có vô số nghiệm |
| a = 0 và b khác 0 | Phương trình vô nghiệm       |
| a khác 0          | Nghiệm x = -b/a              |

Block xử lý chính:

```text
when NutGiai.Click
do
    if NhapA.Text = "" or NhapB.Text = ""
        set KetQua.Text to "Vui lòng nhập đủ a và b"
    else if NhapA.Text = 0 and NhapB.Text = 0
        set KetQua.Text to "Phương trình có vô số nghiệm"
    else if NhapA.Text = 0
        set KetQua.Text to "Phương trình vô nghiệm"
    else
        set KetQua.Text to join "Nghiệm x = " ((0 - NhapB.Text) / NhapA.Text)
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3094e98e-2029-4395-af09-dd22d2efc5d4" />


Công thức nghiệm:

```text
x = -b / a
```

Trong App Inventor biểu diễn là:

```text
(0 - NhapB.Text) / NhapA.Text
```

---

## 7. Thiết kế Screen3 - WebView

Screen3 sử dụng component WebViewer để mở trang web có sẵn.

Các component sử dụng:

| Component | Tên đặt    | Mục đích                |
| --------- | ---------- | ----------------------- |
| Button    | QuayLai2   | Quay lại màn hình trước |
| WebViewer | WebHienThi | Hiển thị trang web      |

Khi mở Screen3, WebViewer truy cập đường dẫn:

```text
https://k58kmt.tdh.io.vn/?masv=K225480106058
```

Block xử lý:

```text
when Screen3.Initialize
do call WebHienThi.GoToUrl
url "https://k58kmt.tdh.io.vn/?masv=K225480106058"
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/81a2f81d-bca5-4ddd-8ca2-b99113896187" />


Nút quay lại:

```text
when QuayLai2.Click
do close screen
```

---



## 8. Mô tả thanh công cụ MIT App Inventor

MIT App Inventor có các khu vực chính:

| Khu vực        | Chức năng                                   |
| -------------- | ------------------------------------------- |
| Palette        | Chứa các component để kéo thả vào giao diện |
| Viewer         | Khu vực xem trước giao diện app             |
| Components     | Danh sách các component đã dùng             |
| Properties     | Thay đổi thuộc tính component               |
| Media / Assets | Upload hình ảnh, âm thanh, file dữ liệu     |
| Designer       | Thiết kế giao diện                          |
| Blocks         | Lập trình logic bằng block                  |

---

## 9. Bản chất của kéo thả và Blocks

Trong MIT App Inventor, lập trình được thực hiện bằng cách kéo thả các khối lệnh. Mỗi block đại diện cho một câu lệnh, một điều kiện, một sự kiện hoặc một phép toán.

Ví dụ:

```text
when Button.Click
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b2c747bf-01db-4fcd-9d1b-84bc60b6afa5" />

có ý nghĩa tương tự một sự kiện click trong lập trình truyền thống.

### Ưu điểm của Blocks

* Dễ sử dụng với người mới học.
* Trực quan, dễ hiểu.
* Giảm lỗi cú pháp.
* Phù hợp để tạo app nhanh.
* Không cần nhớ nhiều câu lệnh lập trình.

### Nhược điểm của Blocks

* Khi app lớn, block dễ bị rối.
* Khó quản lý logic phức tạp.
* Không linh hoạt bằng viết code.
* Khó tái sử dụng ở quy mô lớn.

---

## 10. Copy/Paste block bằng Backpack

Backpack là công cụ dùng để lưu và tái sử dụng block.

Cách dùng:

1. Kéo block cần lưu vào Backpack.
2. Chuyển sang Screen hoặc project khác.
3. Mở Backpack và kéo block ra dùng lại.

Lợi ích:

* Copy block nhanh.
* Tái sử dụng logic.
* Tiết kiệm thời gian.
* Phù hợp khi nhiều Screen có xử lý giống nhau.

---

## 11. Sử dụng Assets trong MIT App Inventor

Assets là nơi lưu các file đi kèm ứng dụng như:

* Hình ảnh.
* Âm thanh.
* File văn bản.
* File JSON.
* File HTML.

Khi build app, các file trong Assets sẽ được đóng gói vào trong ứng dụng. Nhờ đó app có thể sử dụng dữ liệu ngay cả khi không có Internet.

Ví dụ ứng dụng:

```text
App hướng dẫn giải phương trình bậc nhất
```

Dữ liệu có thể lưu trong file:

```text
huongdan.txt
```

Nội dung file gồm:

```text
Công thức phương trình bậc nhất: ax + b = 0
Nếu a khác 0 thì x = -b/a
Nếu a = 0 và b = 0 thì phương trình có vô số nghiệm
Nếu a = 0 và b khác 0 thì phương trình vô nghiệm
```

Lợi ích của dữ liệu offline:

* Không cần mạng vẫn xem được.
* Dữ liệu đi kèm app.
* Phù hợp với app học tập, app hướng dẫn, app tra cứu.

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5e1eaa51-28a9-4597-9591-ad799ee3be01" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f2d7f2f9-7cd6-499d-93b0-779a7c974d97" />

## Kết quả 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a2a85e06-a303-4f4e-9bdb-c05c56971ce4" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d6b02ccf-3caf-43da-a8a6-da5d364e01ac" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/42ffdd52-b5de-4d3e-a843-fa2a5a2f3d58" />


# PHẦN 2: ỨNG DỤNG ANDROID STUDIO

## 12. Giới thiệu App Android Studio

App2 được xây dựng bằng Android Studio, sử dụng ngôn ngữ Java.

App gồm 3 Activity:

| Activity      | Chức năng                           |
| ------------- | ----------------------------------- |
| MainActivity  | About, hiển thị thông tin sinh viên |
| SolveActivity | Giải toán và gửi API                |
| WebActivity   | Hiển thị WebView                    |

Ứng dụng Android Studio có chức năng tương đương với app MIT App Inventor nhưng được xây dựng bằng code Java và giao diện XML.

---

## 13. Tạo project Android Studio

Các bước thực hiện:

1. Mở Android Studio.
2. Chọn `New Project`.
3. Chọn mẫu `Empty Views Activity`.
4. Đặt tên project:

```text
MobileBTL
```

5. Package name:

```text
com.example.mobilebtl
```

6. Language:

```text
Java
```

7. Minimum SDK:

```text
API 24 hoặc cao hơn
```

8. Chọn Finish để tạo project.

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/10f77404-3b5e-4e2a-8dcc-07c1b677eff7" />

## 14. Cấu trúc project Android Studio

Các thư mục quan trọng:

| Thư mục/File                  | Chức năng                     |
| ----------------------------- | ----------------------------- |
| manifests/AndroidManifest.xml | Khai báo quyền, activity, app |
| java/com.example.mobilebtl    | Chứa code Java                |
| res/layout                    | Chứa giao diện XML            |
| res/values/strings.xml        | Chứa chuỗi văn bản            |
| res/values/colors.xml         | Chứa màu                      |
| res/values/themes.xml         | Chứa theme                    |
| build.gradle                  | Cấu hình build project        |
| assets                        | Chứa dữ liệu đi kèm app       |

---


## 15. Các file chính của App2

### File Java

```text
MainActivity.java
SolveActivity.java
WebActivity.java
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d5d59cba-cfea-4bc0-af37-73c142a57117" />

### File layout XML

```text
activity_main.xml
activity_solve.xml
activity_web.xml
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a0088438-6a17-499b-a95e-839e122048f2" />


### File cấu hình và tài nguyên

```text
AndroidManifest.xml
strings.xml
```

---

## 16. MainActivity - Màn hình About

MainActivity hiển thị thông tin cá nhân và có 2 nút:

* Nút mở màn hình giải toán.
* Nút mở màn hình WebView.

Code chuyển Activity:

```java
btnOpenSolve.setOnClickListener(v -> {
    Intent intent = new Intent(MainActivity.this, SolveActivity.class);
    startActivity(intent);
});

btnOpenWeb.setOnClickListener(v -> {
    Intent intent = new Intent(MainActivity.this, WebActivity.class);
    startActivity(intent);
});
```

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5460ab67-bd5d-47c4-a99f-ac14c983077c" />


## 17. SolveActivity - Giải toán và gửi API

SolveActivity thực hiện giải phương trình:

```text
ax + b = 0
```

Các trường hợp xử lý:

| Input           | Output                       |
| --------------- | ---------------------------- |
| a hoặc b rỗng   | Vui lòng nhập đủ dữ liệu     |
| a = 0, b = 0    | Phương trình có vô số nghiệm |
| a = 0, b khác 0 | Phương trình vô nghiệm       |
| a khác 0        | Nghiệm x = -b/a              |

Sau khi giải xong, app gửi dữ liệu bằng phương thức POST tới API:

```text
https://k58kmt.tdh.io.vn/api
```

JSON gửi đi:

```json
{
  "app_by": "K225480106058",
  "input": {
    "a": 2,
    "b": 1,
    "c": 3,
    "name": "hello tắc kè"
  },
  "output": {
    "ketluan": "Nghiệm x = -0.50",
    "abc": "xyz",
    "nghiem": -0.5
  }
}
```

Kết quả API trả về:

```json
{
  "ok": 1,
  "stt": 1234
}
```

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/19cb78ac-76c6-46ac-afd2-e8e6be920df8" />

## 18. WebActivity - WebView

WebActivity sử dụng WebView để truy cập trang web bằng phương thức GET:

```text
https://k58kmt.tdh.io.vn/?masv=K225480106058
```

Đoạn code chính:

```java
private static final String WEB_URL = "https://k58kmt.tdh.io.vn/?masv=K225480106058";

webView.setWebViewClient(new WebViewClient());

WebSettings settings = webView.getSettings();
settings.setJavaScriptEnabled(true);
settings.setDomStorageEnabled(true);

webView.loadUrl(WEB_URL);
```

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/55592dfb-d290-47f7-bf8b-8ce7431a432b" />


## 19. Build APK và chạy thử

Sau khi hoàn thành code, thực hiện build APK:

```text
Build → Generate App Bundles or APKs → Generate APK
```

File APK được tạo tại:

```text
app/build/outputs/apk/debug/app-debug.apk
```

Cài app vào BlueStacks bằng cách kéo file APK vào cửa sổ BlueStacks.

---
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9b590b2c-d490-44b7-aeae-1312cf9a6c34" />

# Kết Quả
Giao diện 1
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6cbfb7e0-d305-49f6-89fd-45ca00fbc674" />


## 20. Kiểm thử App2

Các trường hợp kiểm thử:

### Test giải phương trình

| a    | b    | Kết quả                      |
| ---- | ---- | ---------------------------- |
| 2    | 1    | Nghiệm x = -0.50             |

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/0dfc5924-6ec5-450a-983a-1ed078f264aa" />

###Test API : Sau khi bấm nút giải, app gửi dữ liệu lên:
### Kiểm tra log

Vào trang:

```text
https://k58kmt.tdh.io.vn/
```

Tìm theo MSSV:

```text
K225480106058
```

---

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1ea4ecba-75c5-4a97-ad34-7a1a0d0716a2" />


### Test WebView

Mở Activity WebView, app truy cập:

```text
https://k58kmt.tdh.io.vn/?masv=K225480106058
```
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/d0061f0b-2b30-4698-8235-1daf63953588" />



# PHẦN 3: TRẢ LỜI CÂU HỎI THEO YÊU CẦU

## 21. AndroidManifest.xml mô tả gì?

AndroidManifest.xml là file cấu hình quan trọng của ứng dụng Android. File này mô tả thông tin tổng quan của app như tên app, icon, theme, danh sách Activity, quyền truy cập và Activity khởi chạy đầu tiên.

Ví dụ trong bài, app cần Internet để gọi API và mở WebView nên phải khai báo:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

---

## 22. App cần quyền để làm gì? Khai báo như thế nào?

App cần quyền Internet để:

* Gửi JSON bằng POST tới API.
* Mở trang web bằng WebView.
* Truy cập địa chỉ `https://k58kmt.tdh.io.vn`.

Khai báo quyền trong AndroidManifest.xml:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

Dòng này đặt bên trong thẻ `<manifest>` nhưng nằm ngoài thẻ `<application>`.

---

## 23. Vòng đời của một Activity Android là gì?

Vòng đời Activity gồm các hàm chính:

| Hàm         | Ý nghĩa                     |
| ----------- | --------------------------- |
| onCreate()  | Activity được tạo           |
| onStart()   | Activity bắt đầu hiển thị   |
| onResume()  | Activity sẵn sàng tương tác |
| onPause()   | Activity bị che một phần    |
| onStop()    | Activity không còn hiển thị |
| onDestroy() | Activity bị hủy             |

Trong bài, hàm quan trọng nhất là `onCreate()` vì dùng để gắn layout và khởi tạo các component.

---

## 24. Vì sao project có sẵn hàm onCreate?

Khi tạo Activity, Android Studio tự sinh hàm `onCreate()` vì đây là điểm bắt đầu của Activity. Trong hàm này, lập trình viên thường gọi:

```java
setContentView(R.layout.activity_main);
```

Dòng này dùng để liên kết Activity Java với file giao diện XML.

---

## 25. Code Java kiểm tra quyền như thế nào?

Với quyền Internet, Android chỉ cần khai báo trong Manifest, không cần hỏi quyền lúc chạy.

Với các quyền nguy hiểm như Camera, Location, Storage thì cần kiểm tra bằng code:

```java
if (checkSelfPermission(Manifest.permission.CAMERA) != PackageManager.PERMISSION_GRANTED) {
    requestPermissions(new String[]{Manifest.permission.CAMERA}, 100);
}
```

Ý nghĩa:

* Kiểm tra app đã có quyền chưa.
* Nếu chưa có thì yêu cầu người dùng cấp quyền.
* Giúp app tránh bị lỗi khi truy cập tài nguyên nhạy cảm.

---

## 26. res/layout là gì?

`res/layout` là thư mục chứa các file XML mô tả giao diện của ứng dụng.

Ví dụ trong bài:

```text
activity_main.xml
activity_solve.xml
activity_web.xml
```

Mỗi file XML mô tả bố cục và component của một màn hình.

---

## 27. Hardcode là gì? Vì sao nên tránh?

Hardcode là viết trực tiếp chuỗi vào XML hoặc Java.

Ví dụ hardcode:

```xml
android:text="Giải bài toán"
```

Cách đúng là đưa chuỗi vào `strings.xml`:

```xml
<string name="btn_solve">Giải bài toán</string>
```

Sau đó tham chiếu:

```xml
android:text="@string/btn_solve"
```

Ưu điểm:

* Dễ sửa nội dung.
* Dễ dịch đa ngôn ngữ.
* Dễ bảo trì.
* Android có thể tự chọn tài nguyên theo ngôn ngữ, theme, khu vực.

---

## 28. Cú pháp tham chiếu tài nguyên là gì?

Cú pháp tham chiếu tài nguyên trong XML:

```xml
@string/tên_chuỗi
@color/tên_màu
@drawable/tên_hình
@layout/tên_layout
```

Ví dụ:

```xml
android:text="@string/app_name"
android:background="@color/purple_500"
```

Trong Java dùng:

```java
getString(R.string.app_name)
```

---

## 29. OS hỗ trợ tự lấy tài nguyên theo Location, Language, Theme như thế nào?

Android cho phép tạo nhiều thư mục tài nguyên khác nhau:

```text
values/strings.xml
values-en/strings.xml
values-vi/strings.xml
values-night/colors.xml
```

Khi người dùng đổi ngôn ngữ hoặc theme, Android tự động chọn tài nguyên phù hợp.

Ví dụ:

* Máy dùng tiếng Việt → lấy chuỗi trong `values-vi`.
* Máy dùng tiếng Anh → lấy chuỗi trong `values-en`.
* Máy bật dark mode → lấy màu trong `values-night`.

Điều này giúp app dễ hỗ trợ đa ngôn ngữ và giao diện sáng/tối.

---

## 30. Đối tượng chứa trong layout là gì?

Đối tượng chứa là component dùng để gom các component con lại và sắp xếp theo một quy luật.

Ví dụ:

* LinearLayout: sắp xếp con theo chiều ngang hoặc dọc.
* ScrollView: cho phép cuộn khi nội dung dài.
* ConstraintLayout: sắp xếp theo ràng buộc.

Trong bài, sử dụng LinearLayout:

```xml
<LinearLayout
    android:orientation="vertical">
</LinearLayout>
```

Ý nghĩa: các component con được xếp theo chiều dọc.

Nếu muốn xếp ngang:

```xml
android:orientation="horizontal"
```

---

## 31. Gravity là gì?

`gravity` dùng để căn nội dung bên trong View hoặc Layout.

Ví dụ:

```xml
android:gravity="center"
```

Ý nghĩa: căn giữa nội dung.

Các giá trị thường dùng:

```text
center
left
right
top
bottom
center_horizontal
center_vertical
```

---

## 32. Code tương tác với layout như thế nào?

Để code Java tương tác với giao diện, cần gán `id` cho component trong XML.

Ví dụ XML:

```xml
<TextView
    android:id="@+id/txtResult" />
```

Trong Java:

```java
TextView txtResult = findViewById(R.id.txtResult);
txtResult.setText("Kết quả");
```

Nếu muốn tránh hardcode:

```java
txtResult.setText(getString(R.string.result_default));
```

---

## 33. Event click là gì?

Event click là sự kiện xảy ra khi người dùng bấm vào một component như Button hoặc TextView.

Trong Java có thể viết theo 2 cách.

### Cách 1: Dùng Lambda

```java
btnSolve.setOnClickListener(v -> {
    solveEquation();
});
```

### Cách 2: Dùng View.OnClickListener

```java
btnSolve.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        solveEquation();
    }
});
```

Muốn xử lý sự kiện, layout cần có component có `id`, sau đó Java lấy component bằng `findViewById()` và gắn sự kiện `setOnClickListener()`.

---

## 34. Assets là gì?

Assets là thư mục chứa file dữ liệu đi kèm ứng dụng. Các file này được đóng gói vào app khi build.

Ví dụ có thể lưu:

```text
assets/huongdan.txt
assets/data.json
assets/index.html
assets/images/logo.png
```

---

## 35. Copy file vào Assets bằng Windows Explorer thì điều gì xảy ra?

Khi copy file vào thư mục `assets`, các file này sẽ đi theo app sau khi compiler/build. Người dùng cài app sẽ có sẵn các file đó trong ứng dụng.

App có thể truy cập file trong assets bằng cú pháp Java:

```java
InputStream is = getAssets().open("huongdan.txt");
```

---

## 36. Lợi ích của Assets là gì?

Assets giúp app có sẵn dữ liệu offline.

Lợi ích:

* Không cần Internet vẫn dùng được.
* Dữ liệu được đóng gói cùng app.
* Phù hợp với app học tập, app hướng dẫn, app tra cứu.
* Tốc độ đọc dữ liệu nhanh.
* Giảm phụ thuộc vào server.

---

## 37. Ứng dụng dữ liệu Assets trong bài

Trong bài có thể đặt vấn đề:

```text
Xây dựng app hướng dẫn giải phương trình bậc nhất ax + b = 0.
```

Dữ liệu chuẩn bị trước:

```text
Công thức, lý thuyết, ví dụ mẫu, các trường hợp đặc biệt.
```

Dữ liệu có thể lưu dưới dạng:

```text
TXT hoặc JSON
```

Đối tượng hiển thị:

```text
TextView, WebView hoặc ListView
```

Nếu dữ liệu là JSON, app có thể đọc JSON rồi parse thành danh sách để hiển thị. Nếu dữ liệu là TXT, app có thể đọc trực tiếp và hiển thị bằng TextView.

---

## 38. MIT App Inventor và Android Studio khác nhau như thế nào?

| Tiêu chí         | MIT App Inventor | Android Studio               |
| ---------------- | ---------------- | ---------------------------- |
| Cách lập trình   | Kéo thả block    | Viết code Java/Kotlin        |
| Độ khó           | Dễ hơn           | Khó hơn                      |
| Tốc độ tạo app   | Nhanh            | Chậm hơn                     |
| Khả năng mở rộng | Hạn chế          | Mạnh hơn                     |
| Quản lý code     | Khó khi app lớn  | Tốt hơn                      |
| Phù hợp          | Người mới học    | Lập trình Android chuyên sâu |

---

# 39. Kết luận

Qua bài tập lớn, em đã thực hiện được hai ứng dụng di động bằng MIT App Inventor và Android Studio.

Với MIT App Inventor, em hiểu được cách tạo app bằng kéo thả component, thay đổi thuộc tính và xử lý logic bằng Blocks. Công cụ này phù hợp với người mới bắt đầu vì dễ sử dụng, trực quan và không cần viết nhiều code.

Với Android Studio, em hiểu được cấu trúc project Android, cách thiết kế giao diện bằng XML, cách xử lý sự kiện bằng Java, cách khai báo quyền trong AndroidManifest, cách sử dụng WebView và cách gọi API bằng phương thức POST. Đây là môi trường mạnh hơn, phù hợp để phát triển ứng dụng chuyên nghiệp.

Bài tập giúp em nắm được quy trình phát triển ứng dụng di động từ mức cơ bản đến nâng cao, đồng thời hiểu rõ hơn sự khác nhau giữa công cụ kéo thả và lập trình Android gốc.

---


