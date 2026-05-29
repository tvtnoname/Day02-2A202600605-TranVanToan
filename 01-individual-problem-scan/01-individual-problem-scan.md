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
