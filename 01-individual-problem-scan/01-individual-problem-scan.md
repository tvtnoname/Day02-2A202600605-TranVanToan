# 01 — Individual Problem Scan

## Scan rộng

Nam scan 5 problems từ trải nghiệm thực tế của một sinh viên năm cuối theo đuổi AI Engineer.

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
Mỗi tuần Nam mất khoảng 3-4 tiếng để đọc và tóm tắt 3-5 bài báo khoa học (AI papers) mới trên ArXiv để tìm ý tưởng cải tiến mô hình, trong đó việc hiểu nhanh phương pháp đề xuất (Methodology) và so sánh baseline là bước tốn thời gian nhất.

**Actor:**  
Sinh viên năm cuối làm khóa luận tốt nghiệp ngành AI.

**Thời điểm / bối cảnh:**  
Giữa tuần, khi cần tìm giải pháp tối ưu cho mô hình hiện tại hoặc chuẩn bị nội dung thảo luận với lab.

**Current workflow:**  
1. Lên ArXiv / Google Scholar tìm các paper liên quan đến bài toán.
2. Tải file PDF về máy và mở bằng công cụ đọc PDF.
3. Đọc lướt qua Abstract, Introduction và Conclusion để lọc các bài chất lượng.
4. Đọc chi tiết phần Methodology và Architecture để hiểu mô hình đề xuất.
5. Đọc phần Experiment để xem kết quả so sánh với baseline.
6. Viết tóm tắt core idea, ưu nhược điểm và ý tưởng ứng dụng vào Notion cá nhân.

**Bottleneck:**  
Bước 4 và 5: Đọc chi tiết Methodology và Experiment mất 30-40 phút/paper vì nhiều công thức toán phức tạp và biểu đồ so sánh khó đọc nhanh.

**Impact:**  
Tốn khoảng 3-4 tiếng/tuần chỉ để đọc hiểu tài liệu, làm giảm thời gian thực tế dành cho việc code và train mô hình.

**Success metric:**  
Giảm thời gian đọc hiểu và viết tóm tắt mỗi paper từ 60 phút xuống dưới 20 phút mà vẫn nắm được 80% cấu trúc kiến trúc chính để áp dụng.

**Non-AI alternative:**  
Đọc blog phân tích paper có sẵn (nếu có) hoặc chỉ đọc abstract/conclusion (nhưng dễ bỏ lỡ các thiết lập thực nghiệm quan trọng).

**AI hypothesis:**  
Sử dụng AI hỗ trợ đọc hiểu PDF, trích xuất cấu trúc kiến trúc mạng chính và so sánh trực tiếp với các baseline hiện có dưới dạng bảng.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 60 phút

[1 Tìm paper: 5'] 
→ [2 Tải PDF: 5'] 
→ [3 Đọc Abstract/Intro: 10'] 
→ [4 Đọc Methodology: 20']  <--- bottleneck
→ [5 Đọc Experiment: 15']   <--- bottleneck
→ [6 Viết tóm tắt Notion: 5']
```

### Draft future workflow

```text
FUTURE STATE — 18 phút

[1 Tìm paper: 5']
→ [2 AI phân tích PDF & cấu trúc hóa core ideas: 3']
→ [3 Nam review tóm tắt cấu trúc + công thức chính: 8'] <-- human boundary
→ [4 Nam lưu vào Notion: 2']

Fallback: AI tóm tắt sai/thiếu -> Nam tự mở bản PDF gốc để đọc lại phần cần làm rõ.
```

## Problem Cards #2 và #3 — tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| **Phân tích Loss Curves (Overfit/Underfit)** | Nam | Phân tích biểu đồ loss curves và debug code huấn luyện | 40 phút → 15 phút | Workflow | Mức độ mơ hồ cao hơn và phụ thuộc nhiều vào định dạng log thô của từng thư viện train. |
| **Cập nhật siêu tham số thủ công** | Nam | Nhập liệu thủ công các tham số và kết quả run epoch vào Notion/Excel | 10 phút → 0 phút (tự động) | Rule | Có thể giải quyết hoàn toàn bằng script Python tự động log hoặc tích hợp công cụ như WandB (No-AI). |
