# Chứng chỉ Associate Android Developer (Associate Android Developer Certification)
Tất cả các thông tin và tài liệu học tập về chứng chỉ này mà tôi đã thu thập được cho đến nay.

**Các đóng góp (Pull Request) luôn được chào đón!**

### Video Giới thiệu (Video Intro)
[![IMAGE ALT TEXT](http://img.youtube.com/vi/GY5Olv1_dB4/0.jpg)](https://youtu.be/GY5Olv1_dB4 "Video Title")

### Thông tin Chung (General information)
- [Thông báo tại Google I/O 2016][google_io_announcement]
- [Thông tin chi tiết về Chứng chỉ Associate Android Developer][certification_specs]
- [Khóa học phát triển ứng dụng Android trên Udacity bao gồm các chủ đề chứng chỉ][developing_apps_udacity]
- [Lộ trình cấp tốc cho Chứng chỉ Associate Android Developer][fast_track]
- [Tài liệu cơ bản về lập trình Android (Android Developer Fundamentals)](https://developers.google.com/training/courses/android-fundamentals)

### Các Chủ đề trong Chứng chỉ (Certification topics)

[Bản sơ đồ - Thông tin Đầy đủ][diagram]

![android_certification_specs](https://user-images.githubusercontent.com/2780145/33994049-0c034582-e0ff-11e7-8696-2284e9c5b3e0.png)

#### Kiểm thử và Gỡ lỗi (Testing and Debugging)
>Viết các kiểm thử để xác minh rằng logic và giao diện người dùng của ứng dụng đang hoạt động như mong đợi và thực thi các kiểm thử đó bằng công cụ phát triển. Các ứng viên cần có khả năng phân tích sự cố sập ứng dụng (app crash) và tìm các lỗi phổ biến như lỗi bố cục (layout) và rò rỉ bộ nhớ (memory leaks). Điều này bao gồm việc làm việc với trình gỡ lỗi (debugger) để chạy từng bước qua mã ứng dụng nhằm xác minh hành vi mong đợi.

- Viết và chạy kiểm thử đơn vị cục bộ trên JVM (local JVM unit test)
  - [[Fragmented Podcast] Tập 78: Mười chiến lược kiểm thử với Michael Bailey](http://fragmentedpodcast.com/episodes/78/)
  - Bắt đầu với kiểm thử (Getting Started with Testing)
    - [Tài liệu Đào tạo Lập trình viên Android][testing_and_debuggin_getting_started_testing]
    - [Khóa học Kiểm thử Phần mềm trên Udacity][testing_and_debuggin_udacity_course]
    - [Khóa học Kiểm thử trong Android trên Treehouse][treehouse_testing_course]
  - [Xây dựng các Kiểm thử Đơn vị Hiệu quả][testing_and_debugging_building_effective_unit_test]
  - [Danh sách phát: Các mẫu Kiểm thử Android][testing_debuggin_play_list_android_testing_patterns]
  - [Android Testing Codelab (Hướng dẫn thực hành kiểm thử)][testing_and_debugging_testing_codelab]
  - [Các mẫu Kiểm thử Android][testing_and_debugging_android_test_samples]
  - [Bản thiết kế Kiểm thử Android (Android Testing Blueprint)][testing_and_debugging_android_testing_blue_print]
  - [Giới thiệu về kiểm thử phần 1, tác giả @riggaroo][testing_and_debugging_intro_testing_reggaroo]
  - [Giới thiệu về kiểm thử phần 2, tác giả @riggaroo][testing_and_debugging_intro_testing_reggaroo_1]
  - [Giới thiệu về kiểm thử phần 3, tác giả @riggaroo][testing_and_debugging_intro_testing_reggaroo_3]
- Viết và chạy kiểm thử giao diện người dùng (UI test) trên thiết bị
  - [[Fragmented Podcast] Tập 78: Mười chiến lược kiểm thử với Michael Bailey](http://fragmentedpodcast.com/episodes/78/)
  - [Tự động hóa các Kiểm thử Giao diện Người dùng][testing_debuggin_ui_testing]
  - [Espresso (Thư viện kiểm thử giao diện)][testing_and_debuggin_espresso]
  - [UI Automator (Kiểm thử tương tác hệ thống)][testing_and_debuggin_ui_automator]
  - [Espresso nâng cao tại Google I/O 2016][testing_and_debugging_google_io]
  - [Espresso nâng cao trong Android (Big Android BBQ 2016)][testing_and_debugging_advanced_android_espresso_bbq]
  - [Bảng tra nhanh Espresso (Espresso cheat sheet)][testing_and_debugging_espresso_cheat_sheet]
  - [Chuỗi bài học Espresso trên Caster][testing_and_debugging_espresso_serie_caster]

- Tái hiện lỗi từ mô tả bài toán
  - [Experts App Clinic: Các thực hành tốt nhất khi xây dựng ứng dụng cho hàng tỷ người dùng][testing_and_debugging_experts_app_clinic]
- Sử dụng nhật ký hệ thống (system log) để xuất thông tin gỡ lỗi
     - [[Trang lập trình viên Android] Ghi và Xem Log với Logcat](https://developer.android.com/studio/debug/am-logcat.html)
     - [[Khóa học Udacity] Ghi log trong phát triển ứng dụng Android](https://youtu.be/i8CELIzOXCs)
- Gỡ lỗi và sửa lỗi sập ứng dụng (ngoại lệ chưa được bắt - uncaught exception)
   - [[Trang lập trình viên Android] Gỡ lỗi ứng dụng của bạn](https://developer.android.com/studio/debug/index.html)
- Gỡ lỗi và sửa lỗi liên quan đến vòng đời Activity (activity lifecycle)
   - [[Trang lập trình viên Android] Gỡ lỗi ứng dụng của bạn](https://developer.android.com/studio/debug/index.html)
- Gỡ lỗi và sửa lỗi liên kết dữ liệu với view (data binding)
    - [[Trang lập trình viên Android] Gỡ lỗi ứng dụng của bạn](https://developer.android.com/studio/debug/index.html)

#### Giao diện Người dùng (UI) và Trải nghiệm Người dùng (UX) của Ứng dụng
>Triển khai các thành phần trực quan và điều hướng trong thiết kế của ứng dụng. Điều này bao gồm việc xây dựng bố cục (layout) – sử dụng cả mã XML và Java – bao gồm các thành phần UI tiêu chuẩn cũng như các view tùy chỉnh (custom views). Các ứng viên nên có kiến thức thực tế về cách sử dụng kiểu giao diện (view styles) và các thuộc tính chủ đề (theme attributes) để áp dụng một diện mạo nhất quán trên toàn bộ ứng dụng. Hiểu biết về cách đưa vào các tính năng mở rộng đối tượng người dùng thông qua khả năng tiếp cận (accessibility) và địa phương hóa (localization) cũng là một yêu cầu.

- Thiết kế phác thảo các màn hình chính và luồng điều hướng của ứng dụng
  - [[Khóa học Udacity] Hoàn thiện UI - Khả năng tiếp cận (Accessibility)](https://www.udacity.com/course/new-android-fundamentals--ud851)
  - [[Khóa học Udacity] Hoàn thiện UI - Trau chuốt Giao diện](https://www.udacity.com/course/new-android-fundamentals--ud851)
  - [[Code Labs Android] Sử dụng ConstraintLayout để thiết kế giao diện](https://codelabs.developers.google.com/codelabs/constraint-layout/#0)
  
- Mô tả các tương tác giữa UI, tác vụ nền (background task) và lưu trữ dữ liệu bền vững (data persistence)
- Xây dựng bố cục (layout) bằng mã XML hoặc Java
  - [Tạo giao diện người dùng Android bằng mã Java][http://www.techotopia.com/index.php/Creating_an_Android_User_Interface_in_Java_Code]
- Tạo một lớp view tùy chỉnh (custom view class) và thêm nó vào bố cục
  - [[Khóa học Team Treehouse] Các Custom Views trong Android](https://teamtreehouse.com/library/custom-views-in-android)
- Triển khai một chủ đề ứng dụng tùy chỉnh (custom application theme)
  - [[Trang lập trình viên Android] Styles và Themes](https://developer.android.com/guide/topics/ui/themes.html)
  - [[Trang CodePath] Phát triển Theme tùy chỉnh](https://guides.codepath.com/android/Developing-Custom-Themes)
  - [[Trang Android Studio] Thiết kế App Themes với Theme Editor](https://developer.android.com/studio/write/theme-editor.html)
  - [[Khóa học Udacity] Thiết kế ứng dụng Android: Styles và Themes](https://www.udacity.com/course/new-android-fundamentals--ud851)
- Áp dụng style tùy chỉnh cho một nhóm các widget phổ biến
  - [Tài liệu của Android Developers về Widget][android_developers_about_widget]
  - [Hội thảo về Widgets trên TreeHouse][treehouse_widget_workshop]
- Định nghĩa danh sách phần tử RecyclerView
  - [[Trang lập trình viên Android] Recycler View](https://developer.android.com/guide/topics/ui/layout/recyclerview.html)
  - [[CodePath] Sử dụng Recycler View](https://guides.codepath.com/android/using-the-recyclerview)
  - [[Khóa học Treehouse] Danh sách và Bộ chuyển đổi trong Android](https://teamtreehouse.com/library/android-lists-and-adapters)
  - [[Khóa học Udacity] Bài học RecyclerView](https://www.udacity.com/course/new-android-fundamentals--ud851)
- Liên kết dữ liệu cục bộ vào danh sách RecyclerView
  - [[Trang lập trình viên Android] Recycler View](https://developer.android.com/guide/topics/ui/layout/recyclerview.html)
  - [[CodePath] Sử dụng Recycler View](https://guides.codepath.com/android/using-the-recyclerview)
  - [[Khóa học Treehouse] Danh sách và Bộ chuyển đổi trong Android](https://teamtreehouse.com/library/android-lists-and-adapters)
  - [[Khóa học Udacity] Bài học RecyclerView](https://www.udacity.com/course/new-android-fundamentals--ud851)
- Triển khai điều hướng dựa trên menu hoặc ngăn kéo (menu-based or drawer navigation)
  - [[Trang lập trình viên Android] Tạo một Navigation Drawer][ui_ux_android_page_creating_drawer]
  - [[Blog Android Developers] Android Design Support Library Navigation View][ui_ux_android_developer_blog_navigation_view]
  - [[Blog Team Treehouse] Cách thêm một Navigation Drawer trong Android][ui_ux_team_treehouse_blog_navigation_drawer]
  - [[Blog Antonio Leiva] Thư viện hỗ trợ thiết kế: Navigation View][ui_ux_navigation_view]
  - [[Các mẫu phát triển Android] Tập 8: Navigation Drawer, DrawerLayout, và NavigationView](https://www.youtube.com/watch?v=DkT0vS14Um0&feature=youtu.be&list=PLWz5rJ2EKKc-lJo_RGGXL2Psr8vVCTWjM)
- Địa phương hóa văn bản UI của ứng dụng sang một ngôn ngữ khác
  - [[Trang lập trình viên Android] Địa phương hóa với Tài nguyên (Resources)](https://developer.android.com/guide/topics/resources/localization.html)
  - [[Trang lập trình viên Android] Hỗ trợ các Ngôn ngữ và Văn hóa khác nhau](https://developer.android.com/training/basics/supporting-devices/languages.html)
  - [[Khóa học Treehouse] Địa phương hóa trong Android](https://teamtreehouse.com/library/localization-in-android)
  - [[Trang lập trình viên Android] Danh sách kiểm tra địa phương hóa](https://developer.android.com/distribute/best-practices/launch/localization-checklist.html)
  - [[Trang lập trình viên Android] Lớp NumberFormat](https://developer.android.com/reference/java/text/NumberFormat.html)
  - [[Trang lập trình viên Android] Lớp DateFormat](https://developer.android.com/reference/java/text/DateFormat.html)
- Áp dụng mô tả nội dung (content descriptions) cho các view để phục vụ khả năng tiếp cận (accessibility)
    - [[Trang lập trình viên Android] Khả năng tiếp cận](https://developer.android.com/guide/topics/ui/accessibility/index.html)
    - [[Khóa học Udacity] Thiết kế ứng dụng Android: Khả năng tiếp cận](https://www.udacity.com/course/new-android-fundamentals--ud851)
- Thêm các điểm móc tiếp cận (accessibility hooks) vào một view tùy chỉnh
     - [[Trang lập trình viên Android] Xây dựng các Custom Views có thể tiếp cận được](https://developer.android.com/guide/topics/ui/accessibility/custom-views.html)

#### Các thành phần cơ bản của Ứng dụng (Fundamental Application Components)
>Hiểu biết về các thành phần ứng dụng cấp cao của Android ([Activity](https://www.youtube.com/playlist?list=PLWy8DQlwJkdw5GZHEj4ZhR4cayR-ou6Hh), [Service](https://www.youtube.com/playlist?list=PLWy8DQlwJkdzW-dHvL1py-vyF6vYEmDmw), [Broadcast Receiver](https://www.youtube.com/playlist?list=PLWy8DQlwJkdwtBDTpP3tsjx0wXhR2shOq), [Content Provider](https://www.youtube.com/playlist?list=PLWy8DQlwJkdy2_bBHMQgGyrN4784K3Go0)) và vòng đời đi kèm với mỗi thành phần đó. Thí sinh cần mô tả được các loại logic ứng dụng phù hợp nhất cho từng thành phần và liệu thành phần đó đang thực thi ở chế độ nổi (foreground) hay chạy ngầm (background). Điều này bao gồm các chiến lược để xác định cách thức và thời điểm thực hiện công việc chạy ngầm.

- Mô tả các yêu cầu chức năng và phi chức năng chính của ứng dụng
- Tạo một Activity hiển thị tài nguyên bố cục (layout resource)
- Tải dữ liệu cục bộ từ đĩa bằng cách sử dụng một [Loader](https://www.youtube.com/playlist?list=PLWy8DQlwJkdxBxNe9D9P12DtWWgNcGqGf) trên một luồng chạy ngầm (background thread)
  - [[Khóa học Udacity] Tải dữ liệu bằng CursorLoader][db_udacity]
- Truyền tải các thay đổi dữ liệu thông qua một [Loader](https://www.youtube.com/playlist?list=PLWy8DQlwJkdxBxNe9D9P12DtWWgNcGqGf) tới giao diện người dùng UI
  - [[Khóa học Udacity] Tải dữ liệu bằng CursorLoader][db_udacity]
- [Lên lịch cho một tác vụ nhạy cảm về thời gian bằng cách sử dụng báo thức (alarms)](https://github.com/firebase/firebase-jobdispatcher-android)
  - [[Khóa học Udacity] Thiết kế ứng dụng Android: Các tác vụ chạy ngầm](https://www.udacity.com/course/new-android-fundamentals--ud851)
- Lên lịch cho một tác vụ chạy ngầm bằng cách sử dụng [JobScheduler](https://www.youtube.com/playlist?list=PLWy8DQlwJkdw_gbIbmGs4wplosYZen3kAm)
  - [[Khóa học Udacity] Thiết kế ứng dụng Android: Các tác vụ chạy ngầm](https://www.udacity.com/course/new-android-fundamentals--ud851)
- Thực thi một tác vụ chạy ngầm bên trong một [Service](https://www.youtube.com/playlist?list=PLWy8DQlwJkdzW-dHvL1py-vyF6vYEmDmw)
  - [[Khóa học Udacity] Thiết kế ứng dụng Android: Các tác vụ chạy ngầm](https://www.udacity.com/course/new-android-fundamentals--ud851)
  - [[Android Performance Patterns Season 4 ep6] Mẫu hiệu năng của Service](https://www.youtube.com/watch?v=NJsq0TU0qeg)
  - [[Trang lập trình viên Android] Services](https://developer.android.com/guide/components/services.html)
  - [[Trang lập trình viên Android] Tạo một Background Service](https://developer.android.com/training/run-background-service/create-service.html)
- Triển khai điều hướng ngăn xếp tác vụ phi tiêu chuẩn (deep links)
   - [[Trang lập trình viên Android] Cho phép liên kết sâu cho nội dung ứng dụng](https://developer.android.com/training/app-indexing/deep-linking.html)
   - [[Khóa học Team Treehouse] Liên kết sâu (Deep Links)](https://teamtreehouse.com/library/deep-links)
   - [[Blog Jayway] Tiết lộ về Browseable Category](https://blog.jayway.com/2009/09/24/the-browsable-category-revealed/)
- Tích hợp mã từ một thư viện hỗ trợ bên ngoài (external support library)

#### Lưu trữ Dữ liệu Bền vững (Persistent Data Storage)
>Xác định các trường hợp sử dụng thích hợp cho [dữ liệu bền vững](https://www.youtube.com/playlist?list=PLWy8DQlwJkdzafwjoVUcx9283oIbJQvFC) cục bộ và thiết kế các giải pháp để triển khai lưu trữ dữ liệu bằng cách sử dụng các tệp tin (files), cấu hình ưu tiên (preferences) và cơ sở dữ liệu (databases). Điều này bao gồm việc triển khai các chiến lược đóng gói dữ liệu tĩnh đi kèm với ứng dụng, lưu trữ dữ liệu tạm thời (caching) từ các nguồn từ xa và quản lý dữ liệu riêng tư do người dùng tạo ra. Thí sinh cũng nên mô tả được các tính năng của nền tảng cho phép ứng dụng lưu trữ dữ liệu một cách an toàn và chia sẻ dữ liệu đó với các ứng dụng khác một cách bảo mật.

- Định nghĩa một lược đồ cơ sở dữ liệu (database schema); bao gồm các bảng, trường dữ liệu và các chỉ mục (indices)
  - [[Trang lập trình viên Android] Lưu dữ liệu trong Cơ sở dữ liệu SQL][db_android_guide_database]
  - [[Khóa học Udacity] Lưu trữ dữ liệu][db_udacity]
  - [[Team Treehouse] Lưu trữ dữ liệu bền vững trong Android][db_treehouse_data_persistence]
- Tạo một tệp cơ sở dữ liệu riêng tư cho ứng dụng (application-private database file)
- Xây dựng các câu truy vấn cơ sở dữ liệu trả về kết quả đơn lẻ
  - [[Trang lập trình viên Android] Đọc thông tin từ cơ sở dữ liệu][db_android_guide_database_read]
- Xây dựng các câu truy vấn cơ sở dữ liệu trả về nhiều kết quả
  - [[Trang lập trình viên Android] Đọc thông tin từ cơ sở dữ liệu][db_android_guide_database_read]
- Chèn các mục mới vào cơ sở dữ liệu
  - [[Trang lập trình viên Android] Đưa thông tin vào cơ sở dữ liệu][db_android_guide_database_write]
- Cập nhật hoặc xóa các mục hiện có trong cơ sở dữ liệu
  - [[Trang lập trình viên Android] Cập nhật Cơ sở dữ liệu][db_android_guide_database_update]
  - [[Trang lập trình viên Android] Xóa thông tin từ cơ sở dữ liệu][db_android_guide_database_delete]
- Khai báo một cơ sở dữ liệu cho các ứng dụng khác thông qua [Content Provider](https://www.youtube.com/playlist?list=PLWy8DQlwJkdy2_bBHMQgGyrN4784K3Go0)
  - [[Khóa học Udacity] Cách sử dụng một Content Provider][persistent_data_storage_udacity_how_to_use_content_provider]
  - [[Khóa học Udacity] Giới thiệu về Content Providers][db_udacity]
- Đọc và phân tích các tài nguyên thô (raw resources) hoặc các tệp tài sản (asset files)
  - [[Team Treehouse] Lưu trữ dữ liệu bền vững trong Android][db_treehouse_data_persistence]
- Tạo dữ liệu cấu hình bền vững (preference data) từ dữ liệu nhập của người dùng
  - [[Khóa học Udacity] Thiết kế ứng dụng Android: Preferences](https://www.udacity.com/course/new-android-fundamentals--ud851)
- Bật/tắt logic ứng dụng dựa trên các giá trị cấu hình ưu tiên (preference values)
  - [[Khóa học Udacity] Thiết kế ứng dụng Android: Preferences](https://www.udacity.com/course/new-android-fundamentals--ud851)

#### Tích hợp Hệ thống Nâng cao (Enhanced System Integration)
>Mở rộng các ứng dụng để tích hợp với các giao diện bên ngoài trải nghiệm ứng dụng cốt lõi thông qua các thông báo (notifications) và widget ứng dụng (app widgets). Điều này bao gồm việc hiển thị thông tin cho người dùng thông qua các thành phần này và cập nhật thông tin đó liên tục. Thí sinh cũng nên hiểu cách cung cấp điều hướng thích hợp từ các giao diện bên ngoài này vào tác vụ chính của ứng dụng, bao gồm cả việc xử lý thích hợp các liên kết sâu (deep links).

- Tạo một app widget hiển thị trên màn hình chính của thiết bị
  - [[Tài liệu Android Developers] Về Widget][android_developers_about_widget]
  - [[Hội thảo TreeHouse] Thực hành với Widgets][treehouse_widget_workshop]
  - [[Các mẫu phát triển Android] Tập 2: Ứng dụng của bạn trên màn hình chính của họ: Widgets](https://www.youtube.com/watch?v=crsmPedDyoU)
- Triển khai một tác vụ để cập nhật app widget theo chu kỳ
  - [[Trang lập trình viên Android] Widget][android_developers_about_widget]
  - [[Hội thảo TreeHouse] Thực hành với Widgets][treehouse_widget_workshop]
- Tạo và hiển thị một thông báo cho người dùng
  - [[Trang lập trình viên Android] Xây dựng một Notification](https://developer.android.com/training/notify-user/build-notification.html)
  - [[Khóa học Udacity] Thiết kế ứng dụng Android: Các tác vụ chạy ngầm](https://www.udacity.com/course/new-android-fundamentals--ud851)

[google_io_announcement]:<https://www.youtube.com/watch?v=Yu2oGere_Mc&index=13&list=PLWz5rJ2EKKc8jQTUYvIfqA9lMvSGQWtte>
[certification_specs]:<https://www.udacity.com/google-certifications>


<!--( BEGINNING Testing and Debugging)--> 

[testing_and_debuggin_getting_started_testing]:<https://developer.android.com/training/testing/start/index.html>
[testing_and_debugging_android_testing_blue_print]:<https://github.com/googlesamples/android-testing-templates>
[testing_and_debugging_testing_codelab]:<https://codelabs.developers.google.com/codelabs/android-testing/#1>
[testing_and_debugging_building_effective_unit_test]:<https://developer.android.com/training/testing/unit-testing/index.html>
[testing_and_debugging_android_test_samples]:<https://github.com/googlesamples/android-testing>
[testing_debuggin_ui_testing]:<https://developer.android.com/training/testing/ui-testing/index.html>
[testing_and_debuggin_espresso]:<https://google.github.io/android-testing-support-library/docs/espresso/index.html>
[testing_and_debuggin_ui_automator]:<https://google.github.io/android-testing-support-library/docs/uiautomator/index.html>
[testing_and_debugging_google_io]:<https://www.youtube.com/watch?v=isihPOY2vS4&index=29&list=PLWz5rJ2EKKc8jQTUYvIfqA9lMvSGQWtte>
[testing_debuggin_play_list_android_testing_patterns]:<https://www.youtube.com/watch?v=W8LJjfkTKik&list=PLWz5rJ2EKKc-6HWg_jyP0U1zrVLHn65b2>
[testing_and_debugging_advanced_android_espresso_bbq]:<https://www.youtube.com/watch?v=hfoAC9gdC74&list=PLWz5rJ2EKKc_HyE1QX9heAgTPdAMqc50z&index=6>
[testing_and_debugging_experts_app_clinic]:<https://www.youtube.com/watch?v=Fhj7IIsAgyE&index=61&list=PLWz5rJ2EKKc8jQTUYvIfqA9lMvSGQWtte>
[testing_and_debugging_intro_testing_reggaroo]:<https://riggaroo.co.za/introduction-automated-android-testing/>
[testing_and_debugging_intro_testing_reggaroo_1]:<https://riggaroo.co.za/automated-android-testing-part-2-setup/>
[testing_and_debugging_intro_testing_reggaroo_3]:<https://riggaroo.co.za/introduction-android-testing-part3/>
[testing_and_debugging_espresso_cheat_sheet]:<https://google.github.io/android-testing-support-library/docs/espresso/cheatsheet/>
[testing_and_debugging_espresso_serie_caster]:<https://caster.io/series/espresso>
[testing_and_debuggin_udacity_course]:<https://www.udacity.com/course/software-testing--cs258>
[treehouse_testing_course]:<https://teamtreehouse.com/library/testing-in-android>

<!--( END Testing and Debugging)-->

[persistent_data_storage_udacity_how_to_use_content_provider]:<https://www.udacity.com/course/how-to-use-a-content-provider--ud258>
[diagram]:<https://coggle.it/diagram/V4zu4UNht0Q0XiTy/0a02ec0ffa8bc95928de4478d1ae1f45a85a8e16cddc07f5180bc9f18b2c63e1>
[developing_apps_udacity]:<https://www.udacity.com/course/ud851>
[fast_track]:<https://www.udacity.com/course/associate-android-developer-fast-track--nd818>
[ui_ux_team_treehouse_blog_navigation_drawer]:<http://blog.teamtreehouse.com/add-navigation-drawer-android>

<!--(BEGINNING Application User Interface (UI) and User Experience (UX))-->

<!--(BEGINNING Persistent Data Storage)-->
  [db_android_guide_database]:<https://developer.android.com/training/basics/data-storage/databases.html>
  [db_android_guide_database_read]:<https://developer.android.com/training/basics/data-storage/databases.html#ReadDbRow>
  [db_android_guide_database_write]:<https://developer.android.com/training/basics/data-storage/databases.html#WriteDbRow>
  [db_android_guide_database_update]:<https://developer.android.com/training/basics/data-storage/databases.html#UpdateDbRow>
  [db_android_guide_database_delete]:<https://developer.android.com/training/basics/data-storage/databases.html#DeleteDbRow>
  [db_udacity]:<https://in.udacity.com/course/android-basics-data-storage--ud845/>
  [db_treehouse_data_persistence]:<https://teamtreehouse.com/library/android-data-persistence/>
<!--(END Persistent Data Storage)-->

[android_developers_about_widget]:<https://developer.android.com/guide/topics/appwidgets/index.html>
[treehouse_widget_workshop]:<https://teamtreehouse.com/library/android-widgets>
[ui_ux_android_page_creating_drawer]:<https://developer.android.com/training/implementing-navigation/nav-drawer.html>
[ui_ux_android_developer_blog_navigation_view]:<https://android-developers.googleblog.com/2015/05/android-design-support-library.html>
[ui_ux_navigation_view]:<https://antonioleiva.com/navigation-view/>

<!--(END Application User Interface (UI) and User Experience (UX))-->

--- Tài liệu Tham khảo ---
-------------------------

    Tài liệu hướng dẫn này được dịch hoàn toàn từ bản gốc với rất ít thay đổi:
    https://github.com/Amejia481/Associate-Android-Developer-Certification
    Xin gửi lời cảm ơn sâu sắc nhất tới tác giả!! :)
