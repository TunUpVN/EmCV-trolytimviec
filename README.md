# EmCV – Trợ lý tìm việc

**Dùng ngay:** https://tunupvn.github.io/EmCV-trolytimviec/

Công cụ miễn phí giúp người tìm việc ở Việt Nam bớt việc lọc tin và sửa CV thủ công:

- **Tìm job** trên TopCV, VietnamWorks, CareerViet, Glints, JobsGO… theo tiêu chí của bạn. Tin đã hết hạn tự bị loại.
- **Chấm độ phù hợp** giữa hồ sơ của bạn và từng tin tuyển dụng, chỉ ra điểm mạnh, khoảng trống và câu nên hỏi nhà tuyển dụng.
- **Viết lại CV 2 trang A4 và thư xin việc** cho từng job, chỉ dùng kinh nghiệm thật trong hồ sơ gốc của bạn, không bịa thêm.
- **Bạn duyệt, sửa, rồi tự nộp.** App không tự gửi gì cho nhà tuyển dụng.
- **Theo dõi kết quả:** đã nộp, được gọi phỏng vấn, chờ kết quả, nhận offer, bị từ chối…, kèm ngày phỏng vấn, vòng, người liên hệ, phản hồi.
- **Xuất bảng Excel** (.xlsx) gồm tổng quan theo trạng thái, danh sách đơn đã ứng tuyển và các job chưa nộp.

Tất cả nằm trong **một file `index.html`**, không cần cài đặt, không có máy chủ. Dữ liệu lưu ngay trong trình duyệt của bạn.

![Ảnh màn hình](docs/screenshot.png)

## Dùng ngay

**Cách 1, trên web:** mở https://tunupvn.github.io/EmCV-trolytimviec/

**Cách 2, trên máy:** tải file `index.html` về rồi mở bằng Chrome, Edge hoặc Firefox.

## Cần chuẩn bị

Một **API key của Claude** (Anthropic):

1. Đăng ký tại [console.anthropic.com](https://console.anthropic.com), nạp credit.
2. Vào **Settings → API Keys**, tạo key mới (dạng `sk-ant-...`).
3. Trong app, vào tab **Cài đặt**, dán key, bấm **Kiểm tra kết nối** rồi **Lưu cài đặt**.

Chi phí tính theo lượt dùng API, thường vài trăm đến vài nghìn đồng cho mỗi lần chấm điểm hoặc viết CV; tìm job tốn hơn vì Claude phải tìm trên web. Xem giá tại [claude.com/pricing](https://claude.com/pricing#api).

> Lưu ý: tính năng tìm job dùng công cụ web search của Claude API. Nếu tài khoản của bạn thuộc một tổ chức, quản trị viên cần bật web search trong Console.

## Cách dùng

1. **Hồ sơ gốc:** điền họ tên, liên hệ, ảnh, và toàn bộ kinh nghiệm thật theo mẫu có sẵn. Ghi càng cụ thể (số liệu, kết quả) thì CV càng mạnh. Mục *"Chưa xác nhận"* là những thứ bạn chưa làm, để Claude không tự đưa vào CV.
2. **Tiêu chí tìm job:** từ khóa vị trí (mỗi dòng một), địa điểm, ưu tiên, loại trừ.
3. **Job:** bấm **Tìm job bằng Claude**, hoặc **+ Thêm job thủ công** rồi dán JD.
4. Với mỗi job:
   - Mở link, chép JD đầy đủ vào **Sửa JD**. Kết quả tìm kiếm thường chỉ có tóm tắt, và các trang tuyển dụng hay chặn đọc tự động.
   - Kiểm tra **hạn nộp**. Nhãn vàng nghĩa là chưa rõ hạn.
   - **Chấm độ phù hợp**, rồi **Tạo CV và thư**.
   - Xem trước, sửa nhanh, đổi màu, rồi **In / Lưu CV thành PDF**. Trong hộp thoại in, chọn *Lưu thành PDF*, khổ A4, lề *Không*, bật *Đồ họa nền*. File PDF có chữ thật, hệ thống lọc CV tự động (ATS) đọc được.
   - Sao chép thư, tự nộp, rồi bấm **Đánh dấu đã nộp**.
5. Khi có phản hồi, mở job trong mục **Đã ứng tuyển** và cập nhật ô **Kết quả tuyển dụng**. Bấm **Xuất bảng Excel** để có file theo dõi.

## Dữ liệu và quyền riêng tư

- Hồ sơ, job và API key chỉ lưu trong trình duyệt của bạn (localStorage), không có máy chủ trung gian.
- Khi bạn bấm các nút dùng Claude, nội dung hồ sơ và JD được gửi thẳng tới `api.anthropic.com` để xử lý.
- Xóa dữ liệu trình duyệt hoặc đổi máy sẽ **mất dữ liệu**. Hãy dùng **Cài đặt → Xuất file sao lưu** thường xuyên. File sao lưu không chứa API key.
- Đừng dùng app trên máy tính công cộng, vì API key nằm trong trình duyệt.

## Tự triển khai bản riêng

Bấm **Fork** để có bản của riêng bạn, rồi vào **Settings → Pages**, chọn branch `main`, thư mục `/ (root)`, bấm **Save**. Hoặc chỉ cần tải file `index.html` về và mở bằng trình duyệt.

## Giới hạn

- Kết quả tìm job phụ thuộc vào công cụ tìm kiếm. Có thể sót tin, và đôi khi có tin cũ lọt qua, nên luôn mở link kiểm tra.
- Claude được dặn không bịa kinh nghiệm, nhưng bạn vẫn phải **đọc lại CV trước khi nộp**.
- Mẫu CV hiện tối ưu cho tiếng Việt, 2 trang A4. Nội dung dài quá sẽ có cảnh báo tràn trang.

## Giấy phép

[MIT](LICENSE): dùng, sửa, chia sẻ tự do.
