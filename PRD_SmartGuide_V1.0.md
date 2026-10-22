# PRD V1.0 — SmartGuide: Hệ thống thuyết minh tự động đa ngôn ngữ

**Phiên bản:** 1.0  
**Trạng thái:** Baseline để phân tích, thiết kế và phát triển MVP  
**Địa điểm thử nghiệm:** Dinh Độc Lập / Hội trường Thống Nhất  
**Người thực hiện:** Một sinh viên  
**Nền tảng:** React.js Web, React Native Mobile, Backend Microservices  
**Ngôn ngữ:** Tiếng Việt và tiếng Anh

---

## 1. Tổng quan sản phẩm

### 1.1. Mô tả
SmartGuide là hệ thống thuyết minh số cho phép khách tham quan truy cập nội dung trên Web không cần tài khoản, dùng ứng dụng Mobile quét QR tại điểm tham quan, xem thông tin/hình ảnh/văn bản của từng POI, chọn tiếng Việt hoặc tiếng Anh và nghe audio được tạo tự động bằng dịch vụ Text-to-Speech (TTS). URL QR phải ổn định.

Admin có thể quản lý địa điểm và POI, nhập nội dung theo ngôn ngữ, tạo audio bằng TTS, tải audio thủ công để thay thế, xuất bản/ẩn nội dung, xem hoặc tạo QR và xem thống kê sử dụng cơ bản.

### 1.2. Định vị
MVP thuyết minh tự động đa ngôn ngữ lấy cảm hứng từ SmartGuide, không sao chép toàn bộ sản phẩm thương mại, giao diện, thương hiệu hoặc tài nguyên có bản quyền.

MVP tập trung vào một địa điểm mẫu, một vai trò Admin, hai ngôn ngữ, QR mở nội dung, audio TTS, Web và Mobile, analytics ẩn danh, kiến trúc backend 3 lớp, microservices và CI/CD.

### 1.3. Bối cảnh và vấn đề
Các điểm tham quan có thể thiếu hướng dẫn viên trực tiếp; bảng giới thiệu có thể chỉ hỗ trợ ít ngôn ngữ; khách phải tự tìm thông tin; việc thu âm lại tốn công khi nội dung thay đổi; đơn vị quản lý thiếu dữ liệu về nội dung được quan tâm; khách có thể không muốn đăng ký hoặc cài ứng dụng.

Khách cần mở đúng nội dung nhanh, không đăng nhập, chọn ngôn ngữ, đọc/nghe thuyết minh và dùng Web hoặc Mobile. Admin cần quản lý POI, cập nhật nội dung, tạo audio, phát hành QR và xem thống kê.

### 1.4. Sản phẩm tham khảo
PRD ghi nhận các nguồn nghiên cứu SmartGuide: website chính thức, Web App, trang dành cho đối tác/bảo tàng, App Store và FAQ/tài liệu nội dung. Các ý tham khảo: hướng dẫn du lịch số, audio, đa ngôn ngữ, QR mở nội dung, TTS và audio tải lên. Offline, analytics GPS nâng cao, vé và thanh toán không thuộc MVP. QR nội dung khác QR vé.

---

## 2. Mục tiêu và tiêu chí thành công

### 2.1. Mục tiêu
1. Khách truy cập nội dung công khai không cần đăng nhập.
2. Khách chọn tiếng Việt hoặc tiếng Anh.
3. Khách xem POI và nghe audio.
4. Mobile quét QR và mở đúng POI.
5. Admin quản lý nội dung và audio.
6. Hệ thống tạo audio bằng TTS và tái sử dụng audio đã lưu.
7. Hệ thống ghi nhận analytics ẩn danh.
8. Backend thể hiện kiến trúc 3 lớp và nhiều service giao tiếp qua HTTP.
9. Web, Mobile và Backend có quy trình CI/CD phù hợp.

### 2.2. Tiêu chí thành công (SC)
| ID | Tiêu chí |
|---|---|
| SC-01 | Có ít nhất 5 POI mẫu thuộc Dinh Độc Lập |
| SC-02 | Mỗi POI demo có nội dung tiếng Việt |
| SC-03 | Các POI demo chính có nội dung tiếng Anh |
| SC-04 | Khách mở nội dung không cần tài khoản |
| SC-05 | 100% QR demo mở đúng POI/địa điểm tương ứng |
| SC-06 | Khách chọn ngôn ngữ và nghe audio |
| SC-07 | Audio TTS được lưu để tái sử dụng |
| SC-08 | Admin tạo, sửa, xuất bản và ẩn nội dung được |
| SC-09 | Dashboard hiển thị sáu nhóm event analytics |
| SC-10 | Mobile quét QR bằng camera thật, không chỉ là WebView |
| SC-11 | Các backend service giao tiếp qua HTTP |
| SC-12 | Pipeline CI/CD chạy thành công cho Web, Mobile và Backend |

---

## 3. Phạm vi sản phẩm

### 3.1. Trong MVP

**Khách tham quan**
- Truy cập Web không cần tài khoản.
- Xem địa điểm, danh sách POI và chi tiết POI.
- Xem văn bản và hình ảnh.
- Chọn tiếng Việt/tiếng Anh.
- Nghe audio; phát, tạm dừng và xem tiến độ.
- Quét QR bằng Mobile, mở nội dung từ URL QR.
- Ghi nhận analytics ẩn danh.

**Admin**
- Đăng nhập.
- Quản lý địa điểm và POI.
- Quản lý nội dung theo ngôn ngữ.
- Tạo audio bằng TTS hoặc tải audio thủ công.
- Xuất bản/ẩn POI.
- Xem/tạo QR nội dung.
- Xem dashboard thống kê.

**Kỹ thuật**
- React.js Web.
- React Native Mobile.
- Backend kiến trúc 3 lớp trong từng service.
- Microservices giao tiếp HTTP đồng bộ.
- Một database server trong MVP, schema riêng theo service.
- Lưu trữ file audio/hình ảnh.
- CI/CD.

### 3.2. Ngoài phạm vi MVP
- Vé, thanh toán, đơn hàng, tour thương mại, mã giảm giá, hoàn tiền, QR vé, kiểm soát ra vào, tích hợp GetYourGuide.
- Tài khoản khách, hồ sơ, yêu thích, lịch sử nghe dài hạn, đồng bộ giữa thiết bị.
- GPS tracking, heatmap, geofencing, tự động phát theo vị trí, theo dõi hành trình.
- Offline đầy đủ, tải toàn bộ guide, bản đồ offline và đồng bộ online/offline. Cache audio một guide chỉ được thử nghiệm nếu còn thời gian.
- Multi-tenant hoàn chỉnh, nhiều tổ chức, phân quyền nhiều cấp, phê duyệt nhiều bước, white-label app và quản lý nhiều chi nhánh.

---

## 4. Người dùng và vai trò

### 4.1. Khách tham quan
Không bắt buộc đăng nhập; có thể dùng Web hoặc Mobile, là khách Việt Nam hoặc quốc tế, truy cập trực tiếp hoặc qua QR. Mục tiêu: tìm POI, chọn ngôn ngữ, xem thông tin và nghe thuyết minh.

### 4.2. Admin / Content Manager
Một vai trò duy nhất trong MVP, bắt buộc đăng nhập và được phép quản lý dữ liệu. Mục tiêu: quản lý địa điểm/POI, nhập nội dung đa ngôn ngữ, tạo audio, xuất bản nội dung và xem thống kê.

### 4.3. Hệ thống bên ngoài
Nhà cung cấp TTS, dịch vụ lưu file, camera thiết bị Mobile, trình duyệt Web và môi trường CI/CD.

---

## 5. User stories

### 5.1. Khách tham quan
| ID | User story | Ưu tiên |
|---|---|---|
| US-VIS-01 | Là khách, tôi muốn mở Web không cần đăng nhập để dùng nhanh tại địa điểm | Must |
| US-VIS-02 | Tôi muốn xem danh sách POI để chọn nội dung | Must |
| US-VIS-03 | Tôi muốn xem chi tiết POI trước khi nghe | Must |
| US-VIS-04 | Tôi muốn chọn tiếng Việt hoặc tiếng Anh | Must |
| US-VIS-05 | Tôi muốn nghe audio để không phải đọc toàn bộ văn bản | Must |
| US-VIS-06 | Tôi muốn quét QR trên Mobile để mở đúng nội dung | Must |
| US-VIS-07 | Tôi muốn mở QR bằng trình duyệt nếu không cài app | Must |
| US-VIS-08 | Tôi muốn được thông báo khi nội dung/audio chưa sẵn sàng | Must |
| US-VIS-09 | Tôi muốn vẫn đọc được văn bản khi audio lỗi | Must |
| US-VIS-10 | Tôi muốn có nút phát, tạm dừng và tiến độ audio | Must |

### 5.2. Admin
| ID | User story | Ưu tiên |
|---|---|---|
| US-ADM-01 | Admin đăng nhập để bảo vệ chức năng quản trị | Must |
| US-ADM-02 | Admin tạo địa điểm | Must |
| US-ADM-03 | Admin tạo POI thuộc địa điểm | Must |
| US-ADM-04 | Admin nhập nội dung tiếng Việt và tiếng Anh | Must |
| US-ADM-05 | Admin tải hình ảnh cho POI | Must |
| US-ADM-06 | Admin tạo audio bằng TTS | Must |
| US-ADM-07 | Admin tải audio thủ công thay cho TTS | Must |
| US-ADM-08 | Admin xuất bản hoặc ẩn POI | Must |
| US-ADM-09 | Admin xem/tạo URL và QR cho POI | Must |
| US-ADM-10 | Admin xem thống kê mức độ sử dụng | Must |

### 5.3. Vận hành
| ID | User story | Ưu tiên |
|---|---|---|
| US-OPS-01 | Mỗi service có trách nhiệm riêng để dễ kiểm thử/bảo trì | Must |
| US-OPS-02 | Các service giao tiếp qua HTTP để thể hiện microservices | Must |
| US-OPS-03 | Pipeline tự động kiểm tra và build | Must |
| US-OPS-04 | Có thể deploy Web/Backend và tạo Mobile artifact cho demo | Must |

---

## 6. Luồng nghiệp vụ

### 6.1. Khách truy cập Web
Mở Web → xem địa điểm/guide → chọn địa điểm → xem POI → chọn ngôn ngữ → mở POI → xem nội dung/hình ảnh/audio → đọc hoặc phát audio → hệ thống ghi analytics.

Ngoại lệ:
- Địa điểm/POI không tồn tại: thông báo không tìm thấy.
- POI chưa xuất bản: không hiển thị công khai.
- Thiếu bản dịch: fallback về tiếng Việt.
- Thiếu audio: ẩn nút phát, vẫn hiển thị văn bản.
- Analytics lỗi: không chặn việc xem nội dung.

### 6.2. Quét QR bằng Mobile
Mở app → chọn quét QR → xin quyền camera → quét → đọc URL/định danh POI → mở POI → chọn ngôn ngữ → xem/nghe → ghi nhận `qr_opened`.

Ngoại lệ: QR không hợp lệ thì thông báo; POI không tồn tại thì màn hình lỗi; từ chối camera thì hướng dẫn cấp quyền hoặc cho phép mở URL thủ công; không có audio thì vẫn hiển thị văn bản.

### 6.3. QR bằng trình duyệt
Khách dùng camera/ứng dụng QR ngoài → trình duyệt mở URL → Web xác định POI → hiển thị nội dung → ghi nhận nguồn QR. Không yêu cầu cài app, đăng nhập hoặc cấp quyền camera cho Web.

### 6.4. Admin tạo nội dung
Đăng nhập → tạo/chọn địa điểm → tạo POI → nhập tiếng Việt và tiếng Anh nếu có → tải hình ảnh → tạo TTS hoặc tải audio → kiểm tra → xuất bản → xem URL/QR.

### 6.5. Tạo audio TTS
Admin chọn POI/ngôn ngữ → Audio Service lấy văn bản → gọi TTS → nhận file → lưu file và metadata → trả trạng thái. Nếu thất bại, giữ nguyên văn bản, cho phép thử lại hoặc tải audio thủ công.

### 6.6. Dashboard
Admin đăng nhập → mở Dashboard → frontend yêu cầu Analytics Service → service tổng hợp dữ liệu → dashboard hiển thị số liệu.

---

## 7. Functional Requirements

### 7.1. Nội dung công khai
| ID | Yêu cầu | Ưu tiên |
|---|---|---|
| FR-PUB-01 | Truy cập nội dung công khai không cần đăng nhập | Must |
| FR-PUB-02 | Hiển thị địa điểm đã xuất bản | Must |
| FR-PUB-03 | Hiển thị danh sách POI thuộc địa điểm | Must |
| FR-PUB-04 | Chỉ hiển thị POI Published cho khách | Must |
| FR-PUB-05 | Hiển thị tiêu đề, mô tả, nội dung và hình ảnh nếu có | Must |
| FR-PUB-06 | Báo lỗi khi địa điểm/POI không tồn tại | Must |
| FR-PUB-07 | Web responsive | Must |

### 7.2. Đa ngôn ngữ
| ID | Yêu cầu | Ưu tiên |
|---|---|---|
| FR-LNG-01 | Hỗ trợ tiếng Việt và tiếng Anh | Must |
| FR-LNG-02 | Mỗi nội dung POI gắn mã ngôn ngữ | Must |
| FR-LNG-03 | Khách chọn ngôn ngữ | Must |
| FR-LNG-04 | Thiếu bản dịch thì fallback về tiếng Việt | Must |
| FR-LNG-05 | Cấu trúc dữ liệu có thể mở rộng ngôn ngữ | Must |
| FR-LNG-06 | Lựa chọn ngôn ngữ áp dụng cho giao diện và nội dung | Must |

### 7.3. Audio
| ID | Yêu cầu | Ưu tiên |
|---|---|---|
| FR-AUD-01 | Khách phát audio nếu có | Must |
| FR-AUD-02 | Player hỗ trợ phát, tạm dừng, tiến độ | Must |
| FR-AUD-03 | Chưa có audio thì ẩn nút phát, vẫn hiện văn bản | Must |
| FR-AUD-04 | Admin tạo audio từ văn bản bằng TTS | Must |
| FR-AUD-05 | Lưu audio sau khi tạo thành công | Must |
| FR-AUD-06 | Không gọi lại TTS mỗi lần khách phát audio đã có | Must |
| FR-AUD-07 | Admin tải audio thủ công | Must |
| FR-AUD-08 | Audio thủ công có thể thay thế audio TTS | Must |
| FR-AUD-09 | Khi văn bản đổi, audio liên quan được đánh dấu cần cập nhật/tạo lại | Must |
| FR-AUD-10 | TTS lỗi phải báo Admin, không làm mất văn bản | Must |

### 7.4. QR
| ID | Yêu cầu | Ưu tiên |
|---|---|---|
| FR-QR-01 | Mỗi POI xuất bản có URL ổn định | Must |
| FR-QR-02 | Admin xem/tạo QR từ URL POI | Must |
| FR-QR-03 | QR mở đúng POI/guide | Must |
| FR-QR-04 | Xác định được nguồn truy cập QR | Must |
| FR-QR-05 | Mobile quét QR bằng camera | Must |
| FR-QR-06 | Trình duyệt mở URL QR không cần app | Must |
| FR-QR-07 | QR nội dung không xử lý như QR vé | Must |
| FR-QR-08 | Không triển khai vé, thanh toán hoặc kiểm soát cửa qua QR | Must |
| FR-QR-09 | QR/POI không hợp lệ phải có thông báo dễ hiểu | Must |

### 7.5. Quản trị
| ID | Yêu cầu | Ưu tiên |
|---|---|---|
| FR-ADM-01 | Admin phải đăng nhập trước khi vào khu vực quản trị | Must |
| FR-ADM-02 | MVP chỉ cần một vai trò Admin/Content Manager | Must |
| FR-ADM-03 | Admin tạo/sửa/ẩn địa điểm | Must |
| FR-ADM-04 | Admin tạo/sửa/ẩn POI | Must |
| FR-ADM-05 | Admin nhập nội dung tiếng Việt | Must |
| FR-ADM-06 | Admin nhập nội dung tiếng Anh | Must |
| FR-ADM-07 | Admin tải hình ảnh | Must |
| FR-ADM-08 | Admin xem trạng thái audio theo ngôn ngữ | Must |
| FR-ADM-09 | Admin yêu cầu tạo lại audio | Must |
| FR-ADM-10 | Admin tải audio thủ công | Must |
| FR-ADM-11 | Chỉ cho xuất bản khi có nội dung tiếng Việt tối thiểu | Must |
| FR-ADM-12 | Admin xuất bản/bỏ xuất bản POI | Must |
| FR-ADM-13 | Admin xem URL/QR của POI đã xuất bản | Must |

### 7.6. Analytics
| ID | Yêu cầu | Ưu tiên |
|---|---|---|
| FR-ANA-01 | Ghi nhận `guide_opened` | Must |
| FR-ANA-02 | Ghi nhận `poi_opened` | Must |
| FR-ANA-03 | Ghi nhận `qr_opened` | Must |
| FR-ANA-04 | Ghi nhận `audio_started` | Must |
| FR-ANA-05 | Ghi nhận `audio_completed` | Must |
| FR-ANA-06 | Ghi nhận `language_selected` | Must |
| FR-ANA-07 | Audio hoàn tất khi tiến độ đạt từ 90% | Must |
| FR-ANA-08 | Mỗi phiên nghe chỉ ghi nhận tối đa một completion cho cùng audio | Must |
| FR-ANA-09 | Dùng mã phiên ngẫu nhiên, không cần tài khoản | Must |
| FR-ANA-10 | Không lưu IP, email, số điện thoại hoặc GPS của khách cho analytics | Must |
| FR-ANA-11 | Analytics lỗi không chặn việc xem nội dung | Must |
| FR-ANA-12 | Dashboard tổng hợp theo POI, ngôn ngữ và loại event | Must |

### 7.7. Mobile
| ID | Yêu cầu | Ưu tiên |
|---|---|---|
| FR-MOB-01 | Xây dựng bằng React Native | Must |
| FR-MOB-02 | Xin quyền camera trước khi quét QR | Must |
| FR-MOB-03 | QR hợp lệ mở đúng POI | Must |
| FR-MOB-04 | Hiển thị nội dung và hình ảnh | Must |
| FR-MOB-05 | Phát audio | Must |
| FR-MOB-06 | Báo lỗi camera/QR dễ hiểu | Must |
| FR-MOB-07 | Luồng QR không yêu cầu tài khoản khách | Must |

---

## 8. Acceptance Criteria

### 8.1. Nội dung công khai
- **AC-PUB-01:** Given POI Published, when khách mở URL công khai, then nội dung hiển thị mà không cần đăng nhập.
- **AC-PUB-02:** Khách chưa có tài khoản mở QR mà không bị yêu cầu đăng ký/đăng nhập.
- **AC-PUB-03:** POI chưa xuất bản không hiển thị nội dung chi tiết; hệ thống trả thông báo phù hợp.

### 8.2. Ngôn ngữ
- **AC-LNG-01:** POI có VN và EN; chọn EN thì dùng nội dung/audio EN nếu có.
- **AC-LNG-02:** Chọn EN khi chưa có bản dịch thì hiển thị VN, không báo lỗi hệ thống.
- **AC-LNG-03:** Không thể xuất bản POI thiếu nội dung VN; phải có thông báo lý do.

### 8.3. Audio
- **AC-AUD-01:** Audio hợp lệ và nhấn phát thì audio chạy, UI hiển thị đang phát.
- **AC-AUD-02:** Không có audio thì ẩn nút phát, văn bản vẫn hiển thị.
- **AC-AUD-03:** Audio đã lưu được tái sử dụng; không gọi TTS mỗi lượt nghe.
- **AC-AUD-04:** Yêu cầu TTS thành công thì file và metadata được lưu, trạng thái hoàn tất được trả về.
- **AC-AUD-05:** TTS lỗi thì hiển thị lỗi, giữ văn bản, cho phép thử lại/tải audio.
- **AC-AUD-06:** Audio thủ công được chọn thì khách nghe audio thủ công thay audio TTS.

### 8.4. QR
- **AC-QR-01:** Quét QR của POI Published trên Mobile mở đúng POI.
- **AC-QR-02:** Quét QR bằng camera/app QR bên ngoài mở Web.
- **AC-QR-03:** Mở từ QR được analytics ghi nhận là nguồn QR.
- **AC-QR-04:** QR không hợp lệ báo lỗi, app không bị treo.
- **AC-QR-05:** QR của POI đã ẩn không mở nội dung công khai.
- **AC-QR-06:** QR nội dung không yêu cầu vé, thanh toán hoặc kiểm tra cửa.

### 8.5. Admin
- **AC-ADM-01:** Chưa đăng nhập truy cập Admin thì được chuyển đến đăng nhập.
- **AC-ADM-02:** Admin tạo POI có nội dung VN thì lưu trạng thái Draft.
- **AC-ADM-03:** Admin xuất bản POI đủ điều kiện thì POI Published và công khai.
- **AC-ADM-04:** Không xuất bản được POI thiếu nội dung VN.
- **AC-ADM-05:** Bỏ xuất bản khiến POI không còn xuất hiện trong danh sách công khai.
- **AC-ADM-06:** POI đã xuất bản có URL ổn định và QR tương ứng.

### 8.6. Analytics
- **AC-ANA-01:** Mở guide thành công gửi event `guide_opened`.
- **AC-ANA-02:** Hiển thị POI gửi event `poi_opened`.
- **AC-ANA-03:** Mở POI từ QR gửi event `qr_opened`.
- **AC-ANA-04:** Audio bắt đầu phát gửi event `audio_started`.
- **AC-ANA-05:** Audio 100 giây đạt ít nhất 90 giây thì ghi nhận hoàn tất.
- **AC-ANA-06:** Analytics lỗi không làm gián đoạn nội dung.
- **AC-ANA-07:** Dashboard hiển thị tổng hợp theo loại event, POI và ngôn ngữ.

### 8.7. Mobile
- **AC-MOB-01:** Chưa cấp quyền camera thì app yêu cầu quyền khi bắt đầu quét.
- **AC-MOB-02:** Được cấp quyền và quét QR hợp lệ thì mở đúng nội dung.
- **AC-MOB-03:** Từ chối quyền camera thì hướng dẫn cấp quyền hoặc thông báo không thể quét.
- **AC-MOB-04:** Mobile mở POI có audio và nhấn phát thì audio chạy trên thiết bị.

### 8.8. CI/CD
- **AC-CICD-01:** Thay đổi Web kích hoạt lint/test/build.
- **AC-CICD-02:** Test thất bại thì pipeline thất bại và không deploy bản lỗi.
- **AC-CICD-03:** Kiểm tra thành công thì artifact/phiên bản được deploy lên môi trường demo.
- **AC-CICD-04:** Thay đổi một Backend Service được test/build độc lập.

---

## 9. Non-functional Requirements

### 9.1. Hiệu năng
- **NFR-PERF-01:** Với dữ liệu MVP và tối đa 20 người dùng đồng thời, 95% request đọc nội dung trả trong ≤ 2 giây, không tính tải file audio.
- **NFR-PERF-02:** Nội dung chính của trang POI hiển thị trong ≤ 3 giây trên mạng ổn định.
- **NFR-PERF-03:** Audio có sẵn bắt đầu phát trong ≤ 5 giây sau thao tác trên mạng ổn định.
- **NFR-PERF-04:** Tạo TTS không làm treo giao diện; phải có trạng thái xử lý.
- **NFR-PERF-05:** Gửi analytics không chặn hiển thị nội dung.

### 9.2. Khả dụng
- **NFR-USE-01:** Nội dung công khai không yêu cầu đăng nhập.
- **NFR-USE-02:** Luồng quét QR gồm mở app, chọn scan, cấp quyền nếu cần và quét.
- **NFR-USE-03:** Nút phát/tạm dừng/ngôn ngữ/QR có nhãn rõ.
- **NFR-USE-04:** Thông báo lỗi dễ hiểu.
- **NFR-USE-05:** Web hỗ trợ Desktop và Mobile.
- **NFR-USE-06:** Văn bản luôn hiển thị khi audio không khả dụng.
- **NFR-USE-07:** Giao diện chính hỗ trợ tiếng Việt và tiếng Anh.

### 9.3. Tương thích
- **NFR-COMP-01:** Kiểm thử trên Chrome mới và ít nhất một trình duyệt Chromium khác.
- **NFR-COMP-02:** Web hiển thị trên màn hình Mobile phổ biến.
- **NFR-COMP-03:** Mobile kiểm thử trên Android emulator hoặc thiết bị Android thật.
- **NFR-COMP-04:** Code React Native không khóa thiết kế vào một nền tảng, dù MVP ưu tiên Android.

### 9.4. Bảo mật
- **NFR-SEC-01:** Admin cần xác thực.
- **NFR-SEC-02:** Không lưu mật khẩu dạng plaintext.
- **NFR-SEC-03:** Token/session có thời hạn và cơ chế đăng xuất.
- **NFR-SEC-04:** API quản trị kiểm tra quyền trước thao tác.
- **NFR-SEC-05:** Kiểm tra dữ liệu đầu vào.
- **NFR-SEC-06:** Upload kiểm tra loại và kích thước file.
- **NFR-SEC-07:** Không commit secret, TTS key hoặc thông tin kết nối.
- **NFR-SEC-08:** HTTPS cho demo nếu hạ tầng hỗ trợ.
- **NFR-SEC-09:** Giới hạn CORS cho client hợp lệ.
- **NFR-SEC-10:** Client không truy cập trực tiếp schema/database của service.

### 9.5. Quyền riêng tư
- **NFR-PRIV-01:** Không yêu cầu email, số điện thoại hoặc họ tên khách.
- **NFR-PRIV-02:** Không lưu IP cho analytics MVP.
- **NFR-PRIV-03:** Không lưu GPS.
- **NFR-PRIV-04:** Dùng mã phiên ngẫu nhiên, không phải định danh cá nhân trực tiếp.
- **NFR-PRIV-05:** Chỉ lưu dữ liệu analytics cần thiết.
- **NFR-PRIV-06:** Thông báo ngắn rằng hệ thống ghi nhận sự kiện sử dụng ẩn danh.
- **NFR-PRIV-07:** Có chính sách xóa/thời hạn lưu trữ cấu hình được; mục tiêu demo là không lưu lâu hơn cần thiết.

### 9.6. Bảo trì
- **NFR-MAIN-01:** Mỗi service có trách nhiệm được mô tả rõ.
- **NFR-MAIN-02:** Business logic không đặt trực tiếp trong controller/route handler.
- **NFR-MAIN-03:** Tách Presentation, Application/Business và Data Access.
- **NFR-MAIN-04:** Mỗi service có README chạy và test.
- **NFR-MAIN-05:** Service không truy cập trực tiếp schema của service khác.
- **NFR-MAIN-06:** Lỗi TTS/lưu file có log để debug.

### 9.7. Độ tin cậy
- **NFR-REL-01:** TTS lỗi không làm mất nội dung POI.
- **NFR-REL-02:** Analytics lỗi không làm gián đoạn khách.
- **NFR-REL-03:** URL QR ổn định trong vòng đời POI.
- **NFR-REL-04:** Service trả lỗi có kiểm soát khi dependency không phản hồi.
- **NFR-REL-05:** Audio/hình ảnh có backup hoặc lưu trữ phù hợp môi trường demo.

### 9.8. Accessibility
- **NFR-ACC-01:** Hình ảnh có alt text khi phù hợp.
- **NFR-ACC-02:** Nút chính có nhãn rõ.
- **NFR-ACC-03:** Không truyền đạt thông tin chỉ bằng màu.
- **NFR-ACC-04:** Độ tương phản và cỡ chữ dễ đọc trên Mobile.
- **NFR-ACC-05:** Audio có nội dung văn bản thay thế.

---

## 10. Kiến trúc logic ở mức PRD

### 10.1. Nguyên tắc
- Tách Web, Mobile và Backend.
- Tách Backend thành service có trách nhiệm riêng.
- Mỗi service áp dụng kiến trúc 3 lớp.
- Các service giao tiếp qua HTTP.
- Không truy cập database xuyên service.
- Cho phép triển khai độc lập ở mức phù hợp.
- Có CI/CD cho thành phần chính.

### 10.2. Các service dự kiến

#### Content Service
**Trách nhiệm:** quản lý địa điểm, POI, nội dung đa ngôn ngữ, trạng thái Draft/Published, tham chiếu hình ảnh và slug/URL QR.

**Không chịu trách nhiệm:** tạo TTS, tổng hợp analytics hoặc truy cập trực tiếp dữ liệu của service khác.

#### Audio Service
**Trách nhiệm:** nhận yêu cầu tạo audio, gọi TTS, lưu file/metadata, nhận upload audio, quản lý trạng thái `Pending`, `Processing`, `Ready`, `Failed`, trả thông tin audio.

**Không chịu trách nhiệm:** quản lý POI, xuất bản nội dung hoặc tổng hợp dashboard.

#### Analytics Service
**Trách nhiệm:** nhận event từ Web/Mobile, kiểm tra cấu trúc, lưu event ẩn danh, tổng hợp số liệu và cung cấp dữ liệu dashboard.

**Event tối thiểu:** `guide_opened`, `poi_opened`, `qr_opened`, `audio_started`, `audio_completed`, `language_selected`.

### 10.3. Kiến trúc 3 lớp trong từng service
- **Presentation Layer:** nhận HTTP request, kiểm tra đầu vào cơ bản, gọi Application Layer và trả response/mã lỗi.
- **Application/Business Layer:** xử lý quy tắc nghiệp vụ, điều phối nghiệp vụ và không phụ thuộc trực tiếp vào framework giao tiếp.
- **Data Access Layer:** đọc/ghi dữ liệu, tương tác database/object storage, không chứa logic nghiệp vụ chính.

### 10.4. Database và lưu trữ
- Một database server trong MVP.
- Mỗi service có schema riêng.
- Mỗi service chỉ truy cập schema của mình.
- Chi tiết bảng và API được thiết kế ở tài liệu kỹ thuật riêng, không phải PRD.
- Audio/hình ảnh lưu ở nơi lưu trữ phù hợp; database lưu tham chiếu, không nhúng toàn bộ file vào dữ liệu nghiệp vụ.

### 10.5. Giao tiếp
- HTTP đồng bộ trong MVP; không dùng message broker.
- Content Service cung cấp nội dung cho luồng liên quan Audio Service.
- Client gửi analytics tới Analytics Service qua HTTP.
- Dashboard lấy dữ liệu từ Analytics Service.
- Khi service phụ thuộc không phản hồi, trả lỗi có kiểm soát.

### 10.6. Deep link/QR
- URL QR chứa định danh POI/guide ổn định.
- Mở được bằng trình duyệt và Mobile.
- Có cơ chế xác định nguồn QR.
- Không chứa thông tin vé hoặc thanh toán.

### 10.7. CI/CD
**Web:** cài dependency, lint, unit test, build, deploy demo.  
**Mobile:** cài dependency, lint, test, build APK/artifact, lưu artifact.  
**Backend:** lint/static check, unit test, build từng service, kiểm tra tích hợp cơ bản, deploy demo, health check.

**Bằng chứng nghiệm thu:** pipeline config trong repository, lịch sử pipeline thành công, artifact Mobile, URL Web demo, log/bằng chứng deploy Backend và khả năng build độc lập một service.

---

## 11. Trạng thái nội dung và audio

### 11.1. Trạng thái POI
`Draft → Published → Unpublished` (có thể xuất bản lại nếu đủ điều kiện).

Quy tắc:
- POI mới ở Draft.
- Chỉ xuất bản khi có nội dung tiếng Việt tối thiểu.
- Chỉ POI Published hiển thị công khai.
- Unpublished không xuất hiện trong nội dung công khai.
- QR cũ của POI Unpublished không bị xóa nhưng không mở nội dung công khai.

### 11.2. Trạng thái audio
`Not created → Pending → Processing → Ready` hoặc `Failed`.

Admin có thể thử lại khi Failed, tải audio thủ công và chọn audio thủ công thay cho TTS.

---

## 12. Dữ liệu demo và nội dung

### 12.1. Dữ liệu
- Địa điểm: Dinh Độc Lập / Hội trường Thống Nhất.
- Số lượng: 5–10 POI.
- Mỗi POI có tên, mô tả, nội dung tiếng Việt, nội dung tiếng Anh nếu có, hình ảnh nếu có và audio TTS hoặc audio upload.

### 12.2. Nguồn nội dung
Nội dung do tác giả tự viết, lấy từ nguồn công khai có giấy phép rõ ràng hoặc được trích dẫn đúng quy định. Không sao chép nguyên văn nội dung SmartGuide hoặc nội dung có bản quyền khi chưa được phép.

---

## 13. Giả định

| ID | Giả định |
|---|---|
| ASM-01 | Dự án demo học kỳ, không phải hệ thống thương mại |
| ASM-02 | Một Admin là đủ cho MVP |
| ASM-03 | Khách không cần tài khoản |
| ASM-04 | Địa điểm mẫu là Dinh Độc Lập |
| ASM-05 | MVP chỉ hỗ trợ tiếng Việt và tiếng Anh |
| ASM-06 | Có thể gọi TTS bên ngoài trong quá trình phát triển |
| ASM-07 | Có thể dùng một nơi lưu trữ file audio và hình ảnh |
| ASM-08 | Mobile ưu tiên Android |
| ASM-09 | TTS có thể lỗi; upload audio là phương án dự phòng |
| ASM-10 | Analytics chỉ phục vụ thống kê tổng hợp và đánh giá sản phẩm |

---

## 14. Ràng buộc

### 14.1. Môn học
- Web dùng React.js.
- Mobile dùng React Native.
- Backend thể hiện kiến trúc 3 lớp.
- Backend gồm microservices có trách nhiệm rõ ràng.
- Các service giao tiếp với nhau.
- Web, Mobile và Backend có CI/CD.

### 14.2. Nhân lực
- Một người phát triển.
- Không đủ nguồn lực cho tính năng thương mại/nâng cao.
- Ưu tiên chức năng demo và kiểm thử rõ ràng.

### 14.3. Kỹ thuật
- Phụ thuộc Internet khi gọi TTS hoặc truy cập demo.
- Chưa có offline đầy đủ.
- Không dùng message broker.
- Một database server, schema riêng theo service.
- API chi tiết chưa được định nghĩa trong PRD.

---

## 15. Rủi ro và giảm thiểu

| Rủi ro | Mức ảnh hưởng | Giảm thiểu |
|---|---|---|
| TTS hết quota/không khả dụng | Cao | Lưu audio đã tạo, cho phép upload audio |
| TTS phát âm sai tên riêng | Trung bình | Cho phép thay bằng file thu âm |
| QR mở sai POI | Cao | Kiểm thử từng QR trước demo |
| Mobile chỉ là WebView | Cao | Bắt buộc có camera scan và phát audio native |
| Quá nhiều microservice | Cao | Giới hạn Content, Audio, Analytics |
| Truy cập schema xuyên service | Cao | Quy định ownership và giới hạn quyền database |
| Rò rỉ dữ liệu analytics | Cao | Không lưu IP, GPS, email, số điện thoại |
| Mất audio/hình ảnh | Trung bình | Backup hoặc lưu trữ ổn định |
| Thiếu tiếng Anh | Trung bình | Fallback về tiếng Việt |
| Pipeline lỗi sát ngày bảo vệ | Cao | Chạy thường xuyên, lưu artifact |
| Mở rộng sang vé/thanh toán | Cao | Ghi rõ ngoài phạm vi |
| Analytics không phản ánh số người duy nhất | Thấp | Ghi rõ chỉ là analytics ẩn danh, không phải số người dùng duy nhất tuyệt đối |

---

## 16. Những điều không thuộc cam kết
PRD không cam kết:
- Độ chính xác tuyệt đối của nội dung lịch sử.
- TTS chất lượng như người đọc chuyên nghiệp.
- Offline.
- GPS.
- Thanh toán.
- Khả năng chịu tải thương mại.
- Multi-tenant.
- Phát hành chính thức lên App Store/Google Play.
- Tương thích mọi thiết bị.
- Kiểm soát vé hoặc quyền vào cửa.

---

## 17. Chỉ số nghiệm thu MVP

| Nhóm | Chỉ số |
|---|---|
| Nội dung | Ít nhất 5 POI; mỗi POI có tiếng Việt |
| Đa ngôn ngữ | Các POI chính có tiếng Anh |
| QR | 100% QR demo mở đúng POI |
| Mobile | Quét QR trên Android emulator hoặc thiết bị thật |
| Audio | Có TTS hoặc audio upload cho các POI demo chính |
| Admin | Tạo, sửa, xuất bản và ẩn POI |
| Analytics | Sáu event được ghi nhận và hiển thị dashboard |
| Bảo mật | Khách chưa xác thực không vào Admin |
| Kiến trúc | Ba service có trách nhiệm riêng, giao tiếp HTTP |
| CI/CD | Pipeline Web, Mobile và Backend thành công |
| Hiệu năng | 95% request đọc nội dung dưới 2 giây trong kiểm thử MVP |

---

## 18. Câu hỏi mở cho phiên bản sau
Các câu hỏi này không chặn MVP:
1. Có cần iOS trong nghiệm thu chính thức không?
2. Có cần ngôn ngữ thứ ba không?
3. Có cần nhiều Admin/tổ chức không?
4. Có cần yêu thích không?
5. Có cần offline một guide không?
6. Có cần GPS/bản đồ không?
7. Có cần lưu analytics lâu hơn thời gian demo không?
8. Có cần tách Auth thành service riêng không?
9. Có cần message broker khi mở rộng không?
10. Có cần quy trình duyệt nội dung nhiều bước không?

---

## 19. Kết luận
MVP SmartGuide V1.0 tập trung vào luồng giá trị: khách không cần tài khoản, dùng Web hoặc Mobile để mở nội dung Dinh Độc Lập, quét QR tại POI, chọn tiếng Việt/tiếng Anh và nghe audio TTS. Admin quản lý nội dung, tạo audio, phát hành QR và xem thống kê.

Phạm vi đáp ứng các yêu cầu môn học: React.js Web, React Native Mobile, Backend 3 lớp, microservices giao tiếp HTTP, CI/CD cho Frontend và Backend, analytics/dashboard có thể kiểm thử. Không mở rộng sang vé, thanh toán, GPS hoặc offline.
