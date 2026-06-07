
# BÀI TẬP LỚN

## Môn học: Phát triển ứng dụng trên thiết bị di động - TEE0419

**Sinh viên thực hiện:** Nguyễn Tiến Thắng
**Mã sinh viên:** K225480106058
**Lớp:** K58 KTP

---

# PHẦN 1. APP TRÊN MIT APP INVENTOR

## 1.1. Mục tiêu

Xây dựng một ứng dụng bằng công cụ **MIT App Inventor** gồm 3 màn hình:

* **Screen1 - About:** Giới thiệu bản thân và có nút chuyển sang 2 màn hình còn lại.
* **Screen2 - Giải bài toán đơn giản:** Giải phương trình bậc nhất dạng `ax + b = 0`.
* **Screen3 - WebView:** Hiển thị một trang web có sẵn, hỗ trợ giao diện điện thoại.

Ứng dụng tập trung vào quy trình tạo phần mềm bằng cách kéo thả giao diện và kéo thả block xử lý sự kiện.

---

## 1.2. Thiết kế Screen1 - About

### Chức năng

Screen1 dùng để giới thiệu thông tin sinh viên và điều hướng sang các màn hình khác.

### Thành phần sử dụng

| Thành phần          | Chức năng                              |
| ------------------- | -------------------------------------- |
| VerticalArrangement | Chứa các đối tượng theo chiều dọc      |
| Label               | Hiển thị tiêu đề và thông tin cá nhân  |
| Button              | Chuyển sang Screen2 và Screen3         |
| Image               | Hiển thị ảnh đại diện hoặc logo trường |

### Nội dung hiển thị

Thông tin gồm:

* Họ tên: Nguyễn Tiến Thắng
* MSSV: K225480106058
* Lớp: K58 KTP
* Môn học: Phát triển ứng dụng trên thiết bị di động
* Tên ứng dụng: App giải toán và hiển thị WebView

### Cách kéo thả và thay đổi thuộc tính

Trong MIT App Inventor, sinh viên mở phần **Designer**, sau đó kéo các thành phần từ bảng **Palette** sang vùng thiết kế.

Ví dụ:

* Kéo `VerticalArrangement` vào màn hình để gom các thành phần con.
* Kéo `Label` vào để hiển thị thông tin.
* Kéo `Button` vào để tạo nút bấm.
* Kéo `Image` vào để hiển thị ảnh.

Sau khi kéo thả, thay đổi thuộc tính ở bảng **Properties**:

* `Text`: thay đổi nội dung hiển thị.
* `FontSize`: chỉnh cỡ chữ.
* `TextColor`: chỉnh màu chữ.
* `BackgroundColor`: chỉnh màu nền.
* `Width`: đặt `Fill parent` để chiếm toàn bộ chiều ngang.
* `Height`: đặt `Automatic` hoặc số cụ thể.
* `TextAlignment`: căn giữa nội dung.

Việc thay đổi thuộc tính giúp giao diện dễ nhìn, phù hợp với màn hình điện thoại và giúp người dùng thao tác thuận tiện hơn.

---

## 1.3. Thiết kế Screen2 - Giải bài toán đơn giản

### Bài toán chọn

Giải phương trình bậc nhất:

```text
ax + b = 0
```

Kết quả:

* Nếu `a = 0` và `b = 0`: phương trình có vô số nghiệm.
* Nếu `a = 0` và `b ≠ 0`: phương trình vô nghiệm.
* Nếu `a ≠ 0`: phương trình có nghiệm `x = -b / a`.

### Thành phần sử dụng

| Thành phần | Chức năng                     |
| ---------- | ----------------------------- |
| Label      | Hiển thị tiêu đề và hướng dẫn |
| TextBox    | Nhập hệ số a                  |
| TextBox    | Nhập hệ số b                  |
| Button     | Thực hiện giải toán           |
| Label      | Hiển thị kết quả              |
| Button     | Quay lại Screen1              |

### Quy trình xử lý

Người dùng nhập `a`, `b`, sau đó bấm nút **Giải**. App lấy dữ liệu từ TextBox, chuyển sang số và kiểm tra các trường hợp của phương trình.

---

## 1.4. Thiết kế Screen3 - WebView

### Chức năng

Screen3 sử dụng WebView để hiển thị một trang web có sẵn.

Trang web sử dụng:

```text
https://k58kmt.tdh.io.vn?masv=K225480106058
```

### Thành phần sử dụng

| Thành phần | Chức năng               |
| ---------- | ----------------------- |
| WebViewer  | Hiển thị trang web      |
| Button     | Quay lại màn hình chính |

### Ý nghĩa

WebView giúp ứng dụng có thể hiển thị nội dung web ngay bên trong app, không cần mở trình duyệt ngoài. Trang web cần hỗ trợ giao diện điện thoại để người dùng xem dễ dàng trên màn hình nhỏ.

---

## 1.5. Mô tả thanh công cụ trong MIT App Inventor

MIT App Inventor gồm các khu vực chính:

### Palette

Chứa các thành phần để kéo thả vào ứng dụng, ví dụ:

* User Interface: Label, Button, TextBox, Image.
* Layout: VerticalArrangement, HorizontalArrangement.
* Media: Image, Sound.
* Connectivity: Web.
* Sensors: LocationSensor, Clock.
* Storage: TinyDB.
* User Interface nâng cao: WebViewer.

### Viewer

Là vùng mô phỏng màn hình điện thoại. Sinh viên kéo thả các thành phần vào đây để thiết kế giao diện.

### Components

Hiển thị danh sách các thành phần đã được thêm vào app.

### Properties

Cho phép thay đổi thuộc tính của từng thành phần như chữ, màu sắc, kích thước, căn lề.

### Media

Dùng để upload ảnh, âm thanh hoặc file dữ liệu vào app.

---

## 1.6. Mô tả bản chất của block trong MIT App Inventor

Trong MIT App Inventor, phần xử lý logic được thực hiện bằng cách kéo thả các **block**.

Block có bản chất giống như các câu lệnh lập trình. Thay vì viết code bằng tay, sinh viên ghép các khối lệnh lại với nhau.

Ví dụ:

Khi người dùng bấm nút Giải:

```text
when ButtonGiai.Click do
    lấy giá trị a
    lấy giá trị b
    kiểm tra điều kiện
    hiển thị kết quả
```

Block thường gồm:

* Block sự kiện: xử lý khi người dùng click nút.
* Block điều kiện: if/else.
* Block toán học: cộng, trừ, nhân, chia.
* Block biến: lưu dữ liệu tạm thời.
* Block điều hướng: mở màn hình khác.

---

## 1.7. Ưu điểm của kéo thả block so với viết code

### Ưu điểm

* Dễ học với người mới bắt đầu.
* Giảm lỗi cú pháp.
* Trực quan, dễ hiểu luồng xử lý.
* Phù hợp để làm app đơn giản nhanh.
* Không cần cài đặt môi trường lập trình phức tạp.
* Có thể kiểm thử trực tiếp trên điện thoại.

### Nhược điểm

* Khó quản lý khi app lớn.
* Khó tối ưu hiệu năng.
* Không linh hoạt bằng viết code Java/Kotlin.
* Giao diện và chức năng nâng cao bị hạn chế.
* Khó làm việc nhóm với dự án lớn.
* Khi nhiều block, màn hình dễ rối.

---

## 1.8. Copy paste block bằng Backpack

Trong MIT App Inventor có công cụ **Backpack** để sao chép block.

### Cách sử dụng

* Kéo block cần sao chép vào biểu tượng Backpack.
* Chuyển sang Screen khác hoặc Project khác.
* Mở Backpack và kéo block ra để dùng lại.

### Ý nghĩa

Backpack giúp tái sử dụng block, giảm thời gian làm lại các logic giống nhau. Ví dụ, block quay lại màn hình chính hoặc block kiểm tra dữ liệu nhập có thể dùng lại ở nhiều screen.

---

# PHẦN 2. APP1 ANDROID STUDIO - ỨNG DỤNG DỮ LIỆU CHUẨN BỊ TRƯỚC TRONG ASSETS

## 2.1. Ý tưởng app

Tên app:

```text
HuongDanHocAndroid
```

App dùng dữ liệu chuẩn bị trước trong thư mục `assets` để hiển thị nội dung hướng dẫn học Android cơ bản.

Ví dụ dữ liệu gồm các bài học:

* Bài 1: Giới thiệu Android Studio.
* Bài 2: AndroidManifest.xml.
* Bài 3: Vòng đời Activity.
* Bài 4: Layout XML.
* Bài 5: Sự kiện click Button.
* Bài 6: WebView và quyền Internet.

Ứng dụng này có thể chạy offline vì dữ liệu đã được đóng gói sẵn trong app.

---

## 2.2. Đặc thù dữ liệu

Dữ liệu có dạng file JSON đặt trong thư mục:

```text
app/src/main/assets/lessons.json
```

Nội dung dữ liệu:

```json
[
  {
    "title": "Bài 1: Giới thiệu Android Studio",
    "content": "Android Studio là công cụ chính thức để phát triển ứng dụng Android."
  },
  {
    "title": "Bài 2: AndroidManifest.xml",
    "content": "AndroidManifest.xml mô tả thông tin ứng dụng, activity, quyền và cấu hình app."
  },
  {
    "title": "Bài 3: Vòng đời Activity",
    "content": "Activity có các hàm onCreate, onStart, onResume, onPause, onStop và onDestroy."
  },
  {
    "title": "Bài 4: Layout XML",
    "content": "Layout XML dùng để mô tả giao diện người dùng của ứng dụng."
  },
  {
    "title": "Bài 5: Sự kiện Button",
    "content": "Khi người dùng click Button, app có thể chạy một đoạn code xử lý."
  }
]
```

Đặc thù dữ liệu:

* Dữ liệu dạng danh sách.
* Mỗi phần tử có tiêu đề và nội dung.
* Dữ liệu cố định, không cần Internet.
* Có thể đọc trực tiếp từ Assets khi app chạy.

---

## 2.3. Thuật toán xử lý dữ liệu

Thuật toán xử lý đơn giản:

```text
Bước 1: Mở file lessons.json trong thư mục Assets.
Bước 2: Đọc toàn bộ nội dung file.
Bước 3: Chuyển chuỗi JSON thành JSONArray.
Bước 4: Lặp qua từng phần tử.
Bước 5: Lấy title và content.
Bước 6: Ghép nội dung và hiển thị lên TextView.
```

Dữ liệu không cần tiền xử lý phức tạp vì đã được chuẩn bị đúng định dạng JSON.

---

## 2.4. Đối tượng dùng để hiển thị dữ liệu

Có thể dùng:

* `TextView`: hiển thị toàn bộ bài học.
* `ScrollView`: cho phép cuộn khi nội dung dài.
* `LinearLayout`: sắp xếp các TextView theo chiều dọc.

---

## 2.5. Lợi ích của dữ liệu có sẵn trong Assets

* App dùng được khi không có Internet.
* Tốc độ truy cập nhanh.
* Dữ liệu ổn định, không phụ thuộc server.
* Phù hợp với app hướng dẫn, app học tập, app tài liệu, app tra cứu.
* Khi biên dịch, toàn bộ file trong Assets sẽ đi theo app.

---

## 2.6. Cú pháp truy cập file trong Assets

Trong Java:

```java
InputStream is = getAssets().open("lessons.json");
```

Nếu file nằm trong thư mục con:

```java
InputStream is = getAssets().open("data/lessons.json");
```

---

## 2.7. Code đọc dữ liệu từ Assets

File:

```text
MainActivity.java
```

```java
package com.example.huongdanhocandroid;

import android.os.Bundle;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

import org.json.JSONArray;
import org.json.JSONObject;

import java.io.InputStream;
import java.nio.charset.StandardCharsets;

public class MainActivity extends AppCompatActivity {

    TextView txtContent;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        txtContent = findViewById(R.id.txtContent);
        loadLessonsFromAssets();
    }

    private void loadLessonsFromAssets() {
        try {
            InputStream is = getAssets().open("lessons.json");
            int size = is.available();

            byte[] buffer = new byte[size];
            is.read(buffer);
            is.close();

            String json = new String(buffer, StandardCharsets.UTF_8);
            JSONArray array = new JSONArray(json);

            StringBuilder builder = new StringBuilder();

            for (int i = 0; i < array.length(); i++) {
                JSONObject lesson = array.getJSONObject(i);

                String title = lesson.getString("title");
                String content = lesson.getString("content");

                builder.append(title)
                        .append("\n")
                        .append(content)
                        .append("\n\n");
            }

            txtContent.setText(builder.toString());

        } catch (Exception e) {
            txtContent.setText("Lỗi đọc dữ liệu từ Assets: " + e.getMessage());
        }
    }
}
```

---

## 2.8. Layout cho APP1

File:

```text
res/layout/activity_main.xml
```

```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="20dp">

        <TextView
            android:id="@+id/txtTitle"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="@string/app1_title"
            android:textSize="22sp"
            android:textStyle="bold"
            android:gravity="center"
            android:paddingBottom="16dp" />

        <TextView
            android:id="@+id/txtContent"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textSize="16sp" />

    </LinearLayout>
</ScrollView>
```

---

# PHẦN 3. LÝ THUYẾT ANDROID STUDIO

## 3.1. AndroidManifest.xml mô tả gì?

File `AndroidManifest.xml` là file cấu hình quan trọng của ứng dụng Android.

File này mô tả:

* Tên package của app.
* Các Activity có trong app.
* Activity nào là màn hình chạy đầu tiên.
* Các quyền app cần sử dụng.
* Tên ứng dụng.
* Icon ứng dụng.
* Theme ứng dụng.
* Cấu hình phần cứng, dịch vụ, receiver nếu có.

Ví dụ:

```xml
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:theme="@style/Theme.MobileApp"
        android:label="@string/app_name"
        android:icon="@mipmap/ic_launcher">

        <activity android:name=".WebActivity" />
        <activity android:name=".SolveActivity" />

        <activity
            android:name=".MainActivity"
            android:exported="true">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

        </activity>

    </application>

</manifest>
```

---

## 3.2. App cần quyền để do-st thì khai báo như thế nào?

Nếu app cần truy cập Internet, cần khai báo quyền:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

Nếu app cần đọc vị trí, có thể khai báo:

```xml
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
```

Mục đích của khai báo quyền là để hệ điều hành biết ứng dụng muốn sử dụng tài nguyên nào của thiết bị.

---

## 3.3. Vòng đời của một ứng dụng Android

Một Activity trong Android có các hàm vòng đời chính:

| Hàm         | Ý nghĩa                                             |
| ----------- | --------------------------------------------------- |
| onCreate()  | Được gọi khi Activity được tạo lần đầu              |
| onStart()   | Activity bắt đầu hiển thị                           |
| onResume()  | Activity sẵn sàng tương tác với người dùng          |
| onPause()   | Activity bị che một phần hoặc chuẩn bị rời màn hình |
| onStop()    | Activity không còn hiển thị                         |
| onDestroy() | Activity bị huỷ                                     |
| onRestart() | Activity được mở lại sau khi đã dừng                |

Quy trình thường gặp:

```text
onCreate -> onStart -> onResume -> onPause -> onStop -> onDestroy
```

---

## 3.4. Vì sao code tự sinh có sẵn hàm onCreate?

Khi tạo một project Android, Android Studio tự sinh hàm `onCreate()` vì đây là hàm khởi tạo đầu tiên của Activity.

Trong `onCreate()`, lập trình viên thường thực hiện:

* Gắn layout cho Activity bằng `setContentView`.
* Ánh xạ các thành phần giao diện bằng `findViewById`.
* Thiết lập sự kiện click.
* Khởi tạo dữ liệu ban đầu.

Ví dụ:

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}
```

---

## 3.5. Code Java kiểm tra quyền

Một số quyền nguy hiểm như vị trí, camera, bộ nhớ cần kiểm tra khi app chạy.

Ví dụ kiểm tra quyền vị trí:

```java
if (checkSelfPermission(android.Manifest.permission.ACCESS_FINE_LOCATION)
        != PackageManager.PERMISSION_GRANTED) {

    requestPermissions(
            new String[]{android.Manifest.permission.ACCESS_FINE_LOCATION},
            100
    );
} else {
    // Đã có quyền, thực hiện chức năng cần dùng vị trí
}
```

Ý nghĩa:

* `checkSelfPermission`: kiểm tra app đã được cấp quyền chưa.
* `requestPermissions`: xin quyền từ người dùng.
* `PERMISSION_GRANTED`: trạng thái đã được cấp quyền.

Lưu ý: Quyền Internet chỉ cần khai báo trong Manifest, không cần hỏi runtime permission.

---

## 3.6. Giao diện Android mô tả bằng XML

Trong Android Studio, giao diện thường nằm trong thư mục:

```text
res/layout
```

Ví dụ file:

```text
activity_main.xml
```

Layout XML mô tả các thành phần giao diện như Button, TextView, EditText, LinearLayout, WebView.

---

## 3.7. Hardcode là gì?

Hardcode là viết trực tiếp giá trị vào file layout hoặc code.

Ví dụ hardcode không nên dùng:

```xml
android:text="Xin chào"
```

Cách tốt hơn là đưa chuỗi vào file `strings.xml`:

```xml
android:text="@string/hello"
```

File:

```text
res/values/strings.xml
```

```xml
<resources>
    <string name="hello">Xin chào</string>
</resources>
```

---

## 3.8. Cú pháp tham chiếu tài nguyên

Một số cú pháp thường dùng:

```xml
@string/app_name
@color/primary
@drawable/logo
@mipmap/ic_launcher
@layout/activity_main
@style/AppTheme
```

Trong Java:

```java
getString(R.string.app_name);
```

---

## 3.9. Ưu điểm của tham chiếu tài nguyên

* Tránh hardcode.
* Dễ sửa nội dung ở một nơi.
* Dễ hỗ trợ nhiều ngôn ngữ.
* Dễ hỗ trợ nhiều theme sáng/tối.
* Dễ hỗ trợ nhiều kích thước màn hình.
* Giúp code và giao diện rõ ràng hơn.

---

## 3.10. OS hỗ trợ tự động lấy giá trị theo Location, Language, Theme

Android có cơ chế tự động chọn tài nguyên theo cấu hình thiết bị.

Ví dụ:

```text
res/values/strings.xml          -> tiếng mặc định
res/values-vi/strings.xml       -> tiếng Việt
res/values-en/strings.xml       -> tiếng Anh
res/values-night/colors.xml     -> màu cho chế độ tối
res/drawable/                   -> ảnh mặc định
res/drawable-night/             -> ảnh cho dark mode
```

Khi người dùng đổi ngôn ngữ, vùng miền hoặc theme, Android tự lấy tài nguyên phù hợp.

Điều này giúp app:

* Hỗ trợ đa ngôn ngữ.
* Hỗ trợ dark mode/light mode.
* Cá nhân hoá theo thiết lập người dùng.
* Không cần viết quá nhiều code xử lý riêng.

---

## 3.11. Đối tượng chứa trong layout

Đối tượng chứa dùng để gộp các đối tượng con lại và sắp xếp theo quy luật.

Ví dụ `LinearLayout`:

```xml
<LinearLayout
    android:orientation="vertical"
    android:gravity="center">
</LinearLayout>
```

Một số thuộc tính:

| Thuộc tính               | Ý nghĩa                      |
| ------------------------ | ---------------------------- |
| orientation="vertical"   | Sắp xếp con theo chiều dọc   |
| orientation="horizontal" | Sắp xếp con theo chiều ngang |
| gravity="center"         | Căn giữa nội dung bên trong  |
| padding                  | Khoảng cách bên trong        |
| margin                   | Khoảng cách bên ngoài        |

---

## 3.12. Code tương tác với layout và tránh hardcode

Không nên viết:

```java
txtResult.setText("Kết quả là...");
```

Nên viết:

```java
txtResult.setText(getString(R.string.result_text));
```

Hoặc nếu có tham số:

```java
txtResult.setText(getString(R.string.result_value, x));
```

Trong `strings.xml`:

```xml
<string name="result_value">Kết quả: %1$s</string>
```

Cách này giúp nội dung hiển thị phù hợp với Language, Location, Theme của người dùng.

---

## 3.13. Event trong Android

Event là sự kiện người dùng tác động vào app, ví dụ:

* Click Button.
* Click TextView.
* Nhập dữ liệu vào EditText.
* Chạm màn hình.
* Cuộn danh sách.

Khi có sự kiện, app sẽ chạy đoạn code tương ứng.

---

## 3.14. Layout cần làm gì để xử lý sự kiện?

Có 2 cách phổ biến.

### Cách 1: Khai báo onClick trong XML

Trong layout:

```xml
<Button
    android:id="@+id/btnSolve"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:text="@string/solve"
    android:onClick="solveEquation" />
```

Trong Java:

```java
public void solveEquation(View view) {
    // Code xử lý khi click
}
```

### Cách 2: Dùng setOnClickListener trong Java

Trong Java:

```java
Button btnSolve = findViewById(R.id.btnSolve);

btnSolve.setOnClickListener(v -> {
    // Code xử lý khi click
});
```

Cách 2 thường được dùng nhiều hơn vì dễ quản lý code và rõ ràng hơn.

---

# PHẦN 4. APP2 ANDROID STUDIO - APP TƯƠNG ĐƯƠNG MIT APP INVENTOR

## 4.1. Yêu cầu

Tạo app Android Studio gồm 3 Activity:

* `MainActivity`: About và nút chuyển sang 2 Activity còn lại.
* `SolveActivity`: Giải bài toán đơn giản. Sau khi giải xong, gọi API `https://k58kmt.tdh.io.vn/api` để gửi dữ liệu.
* `WebActivity`: Dùng WebView truy cập:

```text
https://k58kmt.tdh.io.vn?masv=K225480106058
```

---

## 4.2. Cấu trúc project

```text
MobileBTL/
│
├── app/
│   ├── src/main/
│   │   ├── java/com/example/mobilebtl/
│   │   │   ├── MainActivity.java
│   │   │   ├── SolveActivity.java
│   │   │   └── WebActivity.java
│   │   │
│   │   ├── res/layout/
│   │   │   ├── activity_main.xml
│   │   │   ├── activity_solve.xml
│   │   │   └── activity_web.xml
│   │   │
│   │   ├── res/values/
│   │   │   ├── strings.xml
│   │   │   └── colors.xml
│   │   │
│   │   └── AndroidManifest.xml
```

---

## 4.3. AndroidManifest.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <uses-permission android:name="android.permission.INTERNET" />

    <application
        android:allowBackup="true"
        android:theme="@style/Theme.MobileBTL"
        android:label="@string/app_name"
        android:usesCleartextTraffic="true"
        android:supportsRtl="true">

        <activity android:name=".WebActivity" />
        <activity android:name=".SolveActivity" />

        <activity
            android:name=".MainActivity"
            android:exported="true">

            <intent-filter>
                <action android:name="android.intent.action.MAIN" />
                <category android:name="android.intent.category.LAUNCHER" />
            </intent-filter>

        </activity>

    </application>

</manifest>
```

---

## 4.4. strings.xml

File:

```text
res/values/strings.xml
```

```xml
<resources>
    <string name="app_name">Mobile BTL</string>

    <string name="student_name">Nguyễn Tiến Thắng</string>
    <string name="student_id">K225480106058</string>
    <string name="student_class">K58 KTP</string>
    <string name="subject_name">Phát triển ứng dụng trên thiết bị di động</string>

    <string name="about_title">Thông tin sinh viên</string>
    <string name="btn_open_solve">Mở màn hình giải toán</string>
    <string name="btn_open_web">Mở WebView</string>

    <string name="solve_title">Giải phương trình bậc nhất ax + b = 0</string>
    <string name="input_a">Nhập hệ số a</string>
    <string name="input_b">Nhập hệ số b</string>
    <string name="btn_solve">Giải bài toán</string>
    <string name="btn_back">Quay lại</string>
    <string name="result_default">Kết quả sẽ hiển thị tại đây</string>
    <string name="invalid_input">Vui lòng nhập đúng hệ số a và b</string>
    <string name="infinite_solution">Phương trình có vô số nghiệm</string>
    <string name="no_solution">Phương trình vô nghiệm</string>
    <string name="one_solution">Phương trình có nghiệm x = %1$.2f</string>
    <string name="api_success">Gửi API thành công. STT: %1$s</string>
    <string name="api_error">Lỗi gửi API: %1$s</string>

    <string name="web_title">WebView</string>
</resources>
```

---

## 4.5. activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    android:padding="24dp">

    <TextView
        android:id="@+id/txtAboutTitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/about_title"
        android:textSize="24sp"
        android:textStyle="bold"
        android:gravity="center"
        android:paddingBottom="20dp" />

    <TextView
        android:id="@+id/txtInfo"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:textSize="17sp"
        android:gravity="center"
        android:paddingBottom="30dp" />

    <Button
        android:id="@+id/btnOpenSolve"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/btn_open_solve" />

    <Button
        android:id="@+id/btnOpenWeb"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/btn_open_web"
        android:layout_marginTop="12dp" />

</LinearLayout>
```

---

## 4.6. MainActivity.java

```java
package com.example.mobilebtl;

import android.content.Intent;
import android.os.Bundle;
import android.widget.Button;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    TextView txtInfo;
    Button btnOpenSolve, btnOpenWeb;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        txtInfo = findViewById(R.id.txtInfo);
        btnOpenSolve = findViewById(R.id.btnOpenSolve);
        btnOpenWeb = findViewById(R.id.btnOpenWeb);

        String info =
                getString(R.string.student_name) + "\n" +
                getString(R.string.student_id) + "\n" +
                getString(R.string.student_class) + "\n" +
                getString(R.string.subject_name);

        txtInfo.setText(info);

        btnOpenSolve.setOnClickListener(v -> {
            Intent intent = new Intent(MainActivity.this, SolveActivity.class);
            startActivity(intent);
        });

        btnOpenWeb.setOnClickListener(v -> {
            Intent intent = new Intent(MainActivity.this, WebActivity.class);
            startActivity(intent);
        });
    }
}
```

---

## 4.7. activity_solve.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical"
        android:padding="24dp">

        <TextView
            android:id="@+id/txtSolveTitle"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="@string/solve_title"
            android:textSize="22sp"
            android:textStyle="bold"
            android:gravity="center"
            android:paddingBottom="20dp" />

        <EditText
            android:id="@+id/edtA"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="@string/input_a"
            android:inputType="numberDecimal|numberSigned" />

        <EditText
            android:id="@+id/edtB"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:hint="@string/input_b"
            android:inputType="numberDecimal|numberSigned"
            android:layout_marginTop="10dp" />

        <Button
            android:id="@+id/btnSolve"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="@string/btn_solve"
            android:layout_marginTop="20dp" />

        <TextView
            android:id="@+id/txtResult"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="@string/result_default"
            android:textSize="18sp"
            android:paddingTop="20dp" />

        <TextView
            android:id="@+id/txtApiResult"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:textSize="16sp"
            android:paddingTop="12dp" />

        <Button
            android:id="@+id/btnBack"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="@string/btn_back"
            android:layout_marginTop="20dp" />

    </LinearLayout>
</ScrollView>
```

---

## 4.8. SolveActivity.java

```java
package com.example.mobilebtl;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

import org.json.JSONObject;

import java.io.OutputStream;
import java.net.HttpURLConnection;
import java.net.URL;
import java.nio.charset.StandardCharsets;

public class SolveActivity extends AppCompatActivity {

    EditText edtA, edtB;
    Button btnSolve, btnBack;
    TextView txtResult, txtApiResult;

    private final String MASV = "K225480106058";
    private final String API_URL = "https://k58kmt.tdh.io.vn/api";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_solve);

        edtA = findViewById(R.id.edtA);
        edtB = findViewById(R.id.edtB);
        btnSolve = findViewById(R.id.btnSolve);
        btnBack = findViewById(R.id.btnBack);
        txtResult = findViewById(R.id.txtResult);
        txtApiResult = findViewById(R.id.txtApiResult);

        btnSolve.setOnClickListener(v -> solveEquation());

        btnBack.setOnClickListener(v -> finish());
    }

    private void solveEquation() {
        try {
            double a = Double.parseDouble(edtA.getText().toString().trim());
            double b = Double.parseDouble(edtB.getText().toString().trim());

            String ketLuan;
            Double nghiem = null;

            if (a == 0 && b == 0) {
                ketLuan = getString(R.string.infinite_solution);
            } else if (a == 0) {
                ketLuan = getString(R.string.no_solution);
            } else {
                nghiem = -b / a;
                ketLuan = getString(R.string.one_solution, nghiem);
            }

            txtResult.setText(ketLuan);

            sendResultToApi(a, b, ketLuan, nghiem);

        } catch (Exception e) {
            txtResult.setText(getString(R.string.invalid_input));
        }
    }

    private void sendResultToApi(double a, double b, String ketLuan, Double nghiem) {
        new Thread(() -> {
            try {
                JSONObject input = new JSONObject();
                input.put("a", a);
                input.put("b", b);
                input.put("c", 0);
                input.put("name", "Nguyen Tien Thang");

                JSONObject output = new JSONObject();
                output.put("ketluan", ketLuan);
                output.put("abc", "Giai phuong trinh bac nhat ax + b = 0");

                if (nghiem == null) {
                    output.put("nghiem", JSONObject.NULL);
                } else {
                    output.put("nghiem", nghiem);
                }

                JSONObject body = new JSONObject();
                body.put("app_by", MASV);
                body.put("input", input);
                body.put("output", output);

                URL url = new URL(API_URL);
                HttpURLConnection conn = (HttpURLConnection) url.openConnection();

                conn.setRequestMethod("POST");
                conn.setRequestProperty("Content-Type", "application/json; charset=UTF-8");
                conn.setDoOutput(true);

                OutputStream os = conn.getOutputStream();
                os.write(body.toString().getBytes(StandardCharsets.UTF_8));
                os.close();

                int responseCode = conn.getResponseCode();

                if (responseCode == HttpURLConnection.HTTP_OK
                        || responseCode == HttpURLConnection.HTTP_CREATED) {

                    java.io.InputStream is = conn.getInputStream();
                    java.util.Scanner scanner = new java.util.Scanner(is).useDelimiter("\\A");
                    String response = scanner.hasNext() ? scanner.next() : "";

                    JSONObject responseJson = new JSONObject(response);
                    String stt = responseJson.optString("stt", "Không có STT");

                    runOnUiThread(() -> {
                        txtApiResult.setText(getString(R.string.api_success, stt));
                    });

                } else {
                    runOnUiThread(() -> {
                        txtApiResult.setText(getString(R.string.api_error, "HTTP " + responseCode));
                    });
                }

                conn.disconnect();

            } catch (Exception e) {
                runOnUiThread(() -> {
                    txtApiResult.setText(getString(R.string.api_error, e.getMessage()));
                });
            }
        }).start();
    }
}
```

---

## 4.9. activity_web.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical">

    <Button
        android:id="@+id/btnBackWeb"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/btn_back" />

    <WebView
        android:id="@+id/webView"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1" />

</LinearLayout>
```

---

## 4.10. WebActivity.java

```java
package com.example.mobilebtl;

import android.os.Bundle;
import android.webkit.WebSettings;
import android.webkit.WebView;
import android.webkit.WebViewClient;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

public class WebActivity extends AppCompatActivity {

    WebView webView;
    Button btnBackWeb;

    private final String WEB_URL = "https://k58kmt.tdh.io.vn?masv=K225480106058";

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_web);

        webView = findViewById(R.id.webView);
        btnBackWeb = findViewById(R.id.btnBackWeb);

        btnBackWeb.setOnClickListener(v -> finish());

        webView.setWebViewClient(new WebViewClient());

        WebSettings settings = webView.getSettings();
        settings.setJavaScriptEnabled(true);
        settings.setDomStorageEnabled(true);
        settings.setLoadWithOverviewMode(true);
        settings.setUseWideViewPort(true);

        webView.loadUrl(WEB_URL);
    }
}
```

---

# PHẦN 5. GIẢI THÍCH CODE APP2

## 5.1. MainActivity

`MainActivity` là màn hình About. Màn hình này hiển thị thông tin sinh viên và có 2 nút:

* Nút mở màn hình giải toán.
* Nút mở màn hình WebView.

Sử dụng `Intent` để chuyển Activity:

```java
Intent intent = new Intent(MainActivity.this, SolveActivity.class);
startActivity(intent);
```

---

## 5.2. SolveActivity

`SolveActivity` cho phép người dùng nhập hệ số `a`, `b` để giải phương trình:

```text
ax + b = 0
```

Sau khi giải, app gửi dữ liệu lên API với cấu trúc JSON:

```json
{
  "app_by": "K225480106058",
  "input": {
    "a": 1,
    "b": 2,
    "c": 0,
    "name": "Nguyen Tien Thang"
  },
  "output": {
    "ketluan": "Phương trình có nghiệm x = -2.00",
    "abc": "Giai phuong trinh bac nhat ax + b = 0",
    "nghiem": -2.0
  }
}
```

Khi server trả về:

```json
{
  "ok": 1,
  "stt": 1234
}
```

App hiển thị STT lên giao diện.

---

## 5.3. WebActivity

`WebActivity` dùng WebView để mở trang:

```text
https://k58kmt.tdh.io.vn?masv=K225480106058
```

Cần khai báo quyền Internet trong Manifest:

```xml
<uses-permission android:name="android.permission.INTERNET" />
```

---

# PHẦN 6. MÔ TẢ QUÁ TRÌNH LÀM BÀI

## 6.1. Quá trình làm MIT App Inventor

### Bước 1

Truy cập MIT App Inventor và tạo project mới.

Tên project:

```text
MIT_GiaiToan_WebView_K225480106058
```

### Bước 2

Tạo 3 Screen:

* Screen1: About.
* Screen2: GiaiToan.
* Screen3: WebView.

### Bước 3

Thiết kế Screen1 bằng các thành phần Label, Button, VerticalArrangement.

### Bước 4

Thiết kế Screen2 bằng TextBox, Button, Label để nhập hệ số và hiển thị kết quả.

### Bước 5

Thiết kế Screen3 bằng WebViewer để hiển thị trang web.

### Bước 6

Kéo thả block xử lý sự kiện click Button:

* Button mở Screen2.
* Button mở Screen3.
* Button giải toán.
* Button quay lại.

### Bước 7

Chạy thử app bằng AI Companion hoặc build APK.

---

## 6.2. Quá trình làm Android Studio APP1

### Bước 1

Tạo project Android Studio bằng Java.

Tên project:

```text
HuongDanHocAndroid
```

### Bước 2

Tạo file dữ liệu trong Assets:

```text
app/src/main/assets/lessons.json
```

### Bước 3

Thiết kế layout gồm ScrollView và TextView.

### Bước 4

Viết code đọc file JSON từ Assets.

### Bước 5

Hiển thị danh sách bài học lên giao diện.

### Bước 6

Chạy thử khi tắt mạng để chứng minh app dùng được offline.

---

## 6.3. Quá trình làm Android Studio APP2

### Bước 1

Tạo project Android Studio bằng Java.

Tên project:

```text
MobileBTL
```

### Bước 2

Tạo 3 Activity:

* MainActivity.
* SolveActivity.
* WebActivity.

### Bước 3

Khai báo Activity và quyền Internet trong AndroidManifest.xml.

### Bước 4

Thiết kế giao diện XML cho từng Activity.

### Bước 5

Viết code Java xử lý chuyển màn hình, giải toán, gọi API và mở WebView.

### Bước 6

Chạy thử app trên máy ảo hoặc điện thoại thật.

### Bước 7

Chụp ảnh minh hoạ quá trình làm bài và kết quả.

---

# PHẦN 7. ẢNH MINH HOẠ CẦN ĐƯA VÀO GITHUB VÀ BÁO CÁO

Sinh viên cần chụp và đưa vào thư mục `images/` các ảnh sau:

```text
images/
├── mit_screen1_about.png
├── mit_screen2_solve.png
├── mit_screen3_webview.png
├── mit_blocks_screen1.png
├── mit_blocks_screen2.png
├── android_project_structure.png
├── android_manifest.png
├── android_main_activity.png
├── android_solve_activity.png
├── android_web_activity.png
├── android_app_about_result.png
├── android_app_solve_result.png
├── android_api_result.png
└── android_webview_result.png
```

Trong README.md có thể chèn ảnh như sau:

```md
![MIT Screen About](images/mit_screen1_about.png)
![Android Solve Result](images/android_app_solve_result.png)
```

---

# PHẦN 8. KẾT LUẬN

Qua bài tập lớn này, sinh viên đã thực hiện được hai cách phát triển ứng dụng Android.

Với MIT App Inventor, sinh viên hiểu được cách tạo app bằng kéo thả giao diện và kéo thả block. Cách này đơn giản, trực quan, phù hợp với người mới học, nhưng hạn chế khi xây dựng ứng dụng lớn.

Với Android Studio, sinh viên hiểu được cấu trúc một project Android thật, biết cách sử dụng AndroidManifest.xml, Activity, vòng đời Activity, layout XML, tài nguyên trong thư mục res, dữ liệu trong Assets, xử lý sự kiện, gọi API và sử dụng WebView.

Ứng dụng hoàn thành đáp ứng đầy đủ yêu cầu của đề bài:

* Có app MIT App Inventor gồm 3 Screen.
* Có app Android Studio sử dụng dữ liệu chuẩn bị trước trong Assets.
* Có app Android Studio tương đương MIT App Inventor gồm 3 Activity.
* Có giải toán đơn giản.
* Có gửi dữ liệu lên API.
* Có WebView truy cập đúng URL kèm mã sinh viên.
* Có mô tả quá trình làm bài để upload GitHub và in báo cáo.

---

# PHẦN 9. LINK THAM KHẢO CẦN GHI TRONG BÁO CÁO

* MIT App Inventor: https://appinventor.mit.edu/
* Android Studio: https://developer.android.com/studio
* Android Manifest: https://developer.android.com/guide/topics/manifest/manifest-intro
* Android Activity Lifecycle: https://developer.android.com/guide/components/activities/activity-lifecycle
* Android WebView: https://developer.android.com/develop/ui/views/layout/webapps/webview

```
```
