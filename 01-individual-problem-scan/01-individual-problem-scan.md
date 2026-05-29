# 01 — Individual Problem Scan

## Scan rộng

Nam scan 5 problems từ trải nghiệm thực tế của một sinh viên năm cuối theo đuổi AI Engineer (hướng Computer Vision - Nhận diện tổn thương qua ảnh y tế).

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | Cập nhật bảng theo dõi siêu tham số (Excel/Notion) thủ công sau mỗi lần run model | Nam | Mất 5-10 phút sau mỗi lần chạy thí nghiệm, dễ ghi sai số. |
| 2 | Tốn thời gian | Đọc và tóm tắt 3-5 paper mới (ArXiv) mỗi tuần để tìm giải pháp cải tiến mô hình | Nam | Mất 45-60 phút/paper; khó nhớ hết các chi tiết kiến trúc mạng. |
| 3 | Tốn thời gian | Format và vẽ biểu đồ so sánh kết quả giữa các kiến trúc model khác nhau (VGG, ResNet, Transformer...) | Nam | Mất 30-40 phút loay hoay với `matplotlib` hoặc `seaborn` cho đúng chuẩn học thuật. |
| 4 | AI có thể tốt hơn | Viết phần giải thích nguyên nhân mô hình bị Overfitting/Underfitting dựa trên log Loss & Validation | Nam | Mất nhiều thời gian phân tích thủ công; AI có thể nhận diện pattern của loss curve nhanh hơn. |
| 5 | Lặp lại | Viết báo cáo công việc hàng ngày (Daily Standup) trên Slack/Discord của Lab | Nam, Mentor | Mất 10 phút/ngày để nhớ lại việc đã làm và viết đúng định dạng. |

Vì sao phần scan này mạnh:

- Tập trung vào các tác vụ thực tế của một AI Engineer tập sự (huấn luyện mô hình, đọc nghiên cứu khoa học, viết báo cáo lab).
- Phân biệt rõ các lăng kính (Lặp lại, Tốn thời gian, AI tốt hơn).
- Có số liệu đo lường cụ thể làm bằng chứng (thời gian tiêu tốn, tần suất lặp lại).
- Không bắt đầu bằng giải pháp hay ý tưởng làm Chatbot chung chung.

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Paper Summarization (Tóm tắt paper) | Workflow rất rõ ràng, tốn nhiều thời gian đọc hiểu mỗi tuần, AI hỗ trợ ngôn ngữ rất tốt. | Cách xử lý phần công thức toán học phức tạp và sơ đồ kiến trúc trong PDF. |
| 2 | Phân tích Loss Curves (Overfit/Underfit) | Có pain thật, ảnh hưởng trực tiếp tới việc tinh chỉnh model tiếp theo. | Dữ liệu đầu vào (loss log) cần được tiền xử lý thế nào để AI đọc được chính xác. |
| 3 | Cập nhật siêu tham số thủ công | Tần suất lặp lại cao mỗi khi chạy training. | Vấn đề này có thể giải quyết triệt để bằng script tự động hóa (non-AI). |

## Problem Card #1 — Đọc & tóm tắt paper mới (Paper Summarization)

**Problem 1 câu:**  
Mỗi tuần Nam mất khoảng 4-5 tiếng để tìm, lọc, đọc hiểu và tóm tắt 3-5 bài báo khoa học (AI papers) mới trên ArXiv nhằm cải tiến mô hình nhận diện tổn thương y tế, trong đó bước hiểu chi tiết phương pháp đề xuất (Methodology) và so sánh baseline là tốn thời gian nhất.

**Actor:**  
Sinh viên năm cuối làm khóa luận tốt nghiệp ngành AI (hướng Computer Vision - Y tế).

**Thời điểm / bối cảnh:**  
Giữa tuần, khi cần tìm giải pháp tối ưu cho mô hình hiện tại (ví dụ: mô hình gặp khó khăn với ảnh y tế thiếu sáng hoặc kích thước tổn thương quá nhỏ) hoặc chuẩn bị nội dung thảo luận với lab.

**Current workflow:**  
1. Tìm kiếm các paper liên quan trên ArXiv / Google Scholar (15 phút).
2. Đọc Abstract & Conclusion của ~10 papers để lọc ra 3-5 bài chất lượng để đọc kỹ (15 phút).
3. Tải PDF và đọc lướt qua phần giới thiệu (Introduction) (10 phút).
4. Đọc chi tiết phần Kiến trúc mạng & Phương pháp (Methodology) (25 phút).
5. Đọc phần Thực nghiệm & So sánh Baseline (Experiments) (20 phút).
6. Tổng hợp các điểm chính và lưu lại kết quả so sánh vào Notion (10 phút).

**Bottleneck:**  
Bước 4 và 5: Đọc chi tiết phần Methodology (hiểu kiến trúc mô hình mới) & Experiments (đọc biểu đồ, bảng chỉ số mAP, Precision/Recall so với baseline) mất 45 phút/paper vì nhiều sơ đồ và bảng số liệu phân tán.

**Impact:**  
Tốn khoảng 4-5 tiếng/tuần chỉ để đọc hiểu tài liệu, làm giảm thời gian thực tế dành cho việc code và train mô hình.

**Success metric:**  
- Giảm thời gian đọc và tổng hợp thông tin mỗi paper từ 95 phút xuống dưới 35 phút.
- Nam có thể trình bày lại core idea và phương pháp đề xuất cho mentor/GVHD trong vòng 2 phút mà mentor không cần hỏi lại quá 1 câu để làm rõ bối cảnh.

**Non-AI alternative:**  
- Sử dụng Notion template cố định định hình sẵn các trường thông tin cần điền (Problem, Method, SOTA Metrics, App).
- Dùng các công cụ trực quan hóa liên kết bài báo như Connected Papers hay Semantic Scholar để lọc nhanh bài báo có trích dẫn chất lượng.
- Tổ chức buổi Reading Group trong Lab để chia sẻ tài liệu đọc chung.

**AI hypothesis:**  
Sử dụng AI để phân tích PDF, trích xuất cấu trúc kiến trúc chính (layers, modules) và tự động tạo bảng đối chiếu kết quả thực nghiệm với các baselines tương ứng.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 95 phút

[1 Tìm paper: 15'] 
→ [2 Đọc Abstract/Intro để lọc: 15'] 
→ [3 Đọc lướt Intro bài được chọn: 10'] 
→ [4 Đọc Methodology: 25']  <--- bottleneck
→ [5 Đọc Experiment: 20']   <--- bottleneck
→ [6 Viết tóm tắt Notion: 10']
```

### Draft future workflow

```text
FUTURE STATE — 35 phút

[1 Lọc paper bằng Connected Papers/Semantic Scholar: 10']
→ [2 AI trích xuất cấu trúc kiến trúc & kết quả SOTA: 2']
→ [3 Nam đối chiếu bảng so sánh baseline và kiểm chứng PDF ở các phần công thức/giả thuyết chính: 20'] <-- human boundary
→ [4 Tự động xuất tóm tắt sang Notion: 3']

Fallback: AI trích xuất sai chỉ số -> Nam mở bản PDF gốc để đọc lại phần kết quả/kiến trúc tương ứng.
```

## Problem Cards #2 và #3 — tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| **Phân tích Loss Curves (Overfit/Underfit)** | Nam | Phân tích biểu đồ loss curves và debug code huấn luyện | 40 phút → 15 phút | Workflow | Mức độ mơ hồ cao hơn và phụ thuộc nhiều vào định dạng log thô của từng thư viện train. |
| **Cập nhật siêu tham số thủ công** | Nam | Nhập liệu thủ công các tham số và kết quả run epoch vào Notion/Excel | 10 phút → 0 phút (tự động) | Rule | Có thể giải quyết hoàn toàn bằng script Python tự động log hoặc tích hợp công cụ như WandB (No-AI). |

---

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

