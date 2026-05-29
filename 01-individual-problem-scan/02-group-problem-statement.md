# 02 — Group Problem Statement

## Group convergence

Nhóm 3-4 người, mỗi người share top 3. Tổng cộng khoảng 9 candidates (3 của Nam + 6 của các bạn khác trong lab).

| Cluster | Candidate examples | Pattern chung |
|---|---|---|
| Tóm tắt & tổng hợp kiến thức | - Paper Summarization (Nam)<br>- Đọc quá nhiều tài liệu AI mới (RAG, MCP, Agent...) để theo kịp lớp (Bạn A)<br>- Chưa có hệ thống tự tổng hợp kiến thức từ course + note + GitHub (Bạn B) | Tìm kiếm, chọn lọc và chuyển đổi thông tin chuyên môn kỹ thuật lớn từ nhiều nguồn để nghiên cứu và học tập. |
| Báo cáo & Cập nhật tiến độ | - Cập nhật siêu tham số thủ công (Nam)<br>- Viết daily standup trên Slack/Discord (Nam)<br>- Nhiều kênh liên lạc thông báo rời rạc (Bạn B)<br>- Tự thiết kế slide báo cáo tiến độ tuần từ kết quả train (Bạn C) | Cấu trúc hóa các thông tin và dữ liệu kỹ thuật thành định dạng báo cáo, phân phối thông tin tới người khác. |
| Giám sát & Phân tích kỹ thuật | - Phân tích Loss Curves (Overfit/Underfit) (Nam)<br>- Tự động phát hiện lỗi và gửi cảnh báo khi train model qua đêm (Bạn C) | Theo dõi quá trình huấn luyện mô hình thời gian thực để chẩn đoán lỗi và đưa ra quyết định xử lý kỹ thuật. |

## Shortlist và score

Chấm điểm các ứng viên tiềm năng nhất để đưa ra đồng thuận:

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Paper Summarization** | 5 | 5 | 5 | 5 | 5 | 5 | 5 | 35 |
| **Tổng hợp kiến thức từ Course+Note+GitHub** | 4 | 3 | 4 | 4 | 3 | 4 | 4 | 26 |
| **Phân tích Loss Curves** | 4 | 4 | 4 | 3 | 4 | 3 | 4 | 26 |

Nhóm chọn: **Paper Summarization (Tóm tắt paper)**

Vì sao chọn:
- Đây là tác vụ có quy trình (workflow) rõ ràng, lặp lại hàng tuần đối với tất cả sinh viên làm khóa luận hoặc nghiên cứu AI.
- Dấu hiệu đau đớn (pain evidence) rất rõ ràng khi Nam và các bạn phải "save hàng chục tab nhưng đọc không hết" hoặc tốn 4-5 tiếng/tuần mà vẫn bỏ sót chi tiết quan trọng.
- Success metric rõ rệt về mặt thời gian và khả năng truyền đạt (giảm thời gian đọc, cải thiện chất lượng thảo luận học thuật).
- Dễ dàng triển khai thử nghiệm thực tế ngay trong lab.

Vì sao không chọn các ứng viên khác:
- *Tổng hợp kiến thức*: Độ mơ hồ về nguồn dữ liệu (course slides, personal notes, code repos) quá cao, khó gom và làm sạch dữ liệu trong thời gian ngắn.
- *Phân tích Loss Curves*: Quá phụ thuộc vào framework (PyTorch/Tensorflow) và kiểu kiến trúc mô hình (CNN, RNN, Transformer), khó xây dựng một luồng chuẩn hóa.

## Quick validation

Nhóm thực hiện phỏng vấn nhanh và làm khảo sát nhỏ trong lớp học:

| Nguồn | Số người | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| **Quick Interview** | 3 bạn sinh viên khóa luận AI | 3/3 bạn đều thừa nhận dành hơn 50% thời gian nghiên cứu để cố hiểu phần Methodology và so sánh Baseline. | 1 bạn cho biết thường xem video Youtube giải thích paper hơn là tự đọc. | Tập trung AI vào việc làm rõ phần cấu trúc mạng (Architecture) và bảng so sánh Baseline. |
| **Lớp học (Discord Poll)** | 8 học viên AI | 6/8 người thường xuyên bookmark hàng chục bài báo nhưng chỉ đọc kỹ được 1-2 bài vì ngợp thuật toán. | 2/8 người chỉ đọc Abstract và Conclusion của paper chứ không đi sâu. | Bổ sung phần lọc sơ bộ chất lượng paper trước khi đưa vào luồng tóm tắt chi tiết. |

Insight sau validation:
```text
Pain thật không nằm ở việc "thiếu nguồn paper" mà là việc tốn quá nhiều thời gian đọc sâu Methodology để quyết định xem paper đó có thực sự giải quyết được lỗi mô hình hiện tại của mình hay không.
```
