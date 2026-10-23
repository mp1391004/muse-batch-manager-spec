# Muse Batch Manager — Product Specification v1.0

Đặc tả sản phẩm chi tiết cho tool tạo video AI hàng loạt: xếp hàng loạt prompt, tham chiếu nhân vật bằng `@tag`, chạy đa luồng qua nhiều tài khoản và theo dõi trực tiếp — kèm module **Flow Studio** kéo-thả image-to-video.

📄 Tài liệu đầy đủ: [muse-batch-manager-spec.pdf](muse-batch-manager-spec.pdf) (15 trang, phiên bản 1.0 — 17/10/2026)

## Mục đích

Team tiếp nhận đọc tài liệu này là build lại được sản phẩm từ đầu mà không cần hỏi lại về hành vi, trạng thái, API nội bộ và tiêu chí nghiệm thu.

- **Đối tượng đọc:** Product, Frontend, Backend / Worker, QA
- **Phạm vi:** Batch Manager + Flow Studio + Account Pool + Reference Library
- **Ngoài phạm vi:** chỉnh sửa video sau tạo, thanh toán, xuất bản lên mạng xã hội, train model

## Nội dung

1. Tổng quan sản phẩm
2. Mô hình tài khoản & luồng thực thi (Account Pool, session, dispatcher, retry/timeout)
3. Kho ảnh tham chiếu (Reference Library)
4. Soạn batch prompt & cơ chế @mention
5. Chạy hàng đợi (Queue Execution)
6. Danh sách video & theo dõi trực tiếp
7. Flow Studio — canvas kéo-thả image-to-video
8. Hợp đồng API nội bộ
9. Yêu cầu phi chức năng & bảo mật
10. Tiêu chí nghiệm thu & kịch bản kiểm thử

Phụ lục A: Bảng trạng thái & mã lỗi · Phụ lục B: Giá trị mặc định

> **Đọc trước khi build:** Mục 2 là phần quan trọng nhất — số luồng song song quyết định kiến trúc dispatcher, cách quản lý session và cách xử lý khi một tài khoản mất kết nối giữa chừng.

## Người liên quan

- [@mp1391004](https://github.com/mp1391004)
- [@pennydinh](https://github.com/pennydinh)
