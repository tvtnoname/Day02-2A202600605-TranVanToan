# 01 — Individual Problem Scan

## Scan rộng

Toàn scan 5 problems từ trải nghiệm thực tế của một sinh viên năm cuối theo đuổi AI Engineer (hướng Computer Vision - Nhận diện tổn thương qua ảnh y tế).

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | Cập nhật bảng theo dõi siêu tham số (Excel/Notion) thủ công sau mỗi lần run model | Toàn | Mất 5-10 phút sau mỗi lần chạy thí nghiệm, dễ ghi sai số. |
| 2 | Tốn thời gian | Đọc và tóm tắt 3-5 paper mới (ArXiv) mỗi tuần để tìm giải pháp cải tiến mô hình | Toàn | Mất 45-60 phút/paper; khó nhớ hết các chi tiết kiến trúc mạng. |
| 3 | Tốn thời gian | Format và vẽ biểu đồ so sánh kết quả giữa các kiến trúc model khác nhau (VGG, ResNet, Transformer...) | Toàn | Mất 30-40 phút loay hoay với `matplotlib` hoặc `seaborn` cho đúng chuẩn học thuật. |
| 4 | AI có thể tốt hơn | Viết phần giải thích nguyên nhân mô hình bị Overfitting/Underfitting dựa trên log Loss & Validation | Toàn | Mất nhiều thời gian phân tích thủ công; AI có thể nhận diện pattern của loss curve nhanh hơn. |
| 5 | Lặp lại | Viết báo cáo công việc hàng ngày (Daily Standup) trên Slack/Discord của Lab | Toàn | Mất 10 phút/ngày để nhớ lại việc đã làm và viết đúng định dạng. |

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
Mỗi tuần Toàn mất khoảng 6-8 tiếng để tìm, lọc, đọc hiểu và tóm tắt 3-5 bài báo khoa học (AI papers) mới trên ArXiv nhằm cải tiến mô hình nhận diện tổn thương y tế, trong đó bước giải mã phương pháp đề xuất (Methodology) với các công thức toán phức tạp và đối chiếu bảng baseline trong PDF là tốn thời gian nhất.

**Actor:**  
AI Research / CV Engineer (hoặc Học viên cao học/Sinh viên năm cuối làm khóa luận tốt nghiệp ngành AI hướng Computer Vision - Y tế).

**Thời điểm / bối cảnh:**  
Giữa tuần, khi cần tìm giải pháp tối ưu cho mô hình hiện tại (ví dụ: mô hình gặp khó khăn với ảnh y tế thiếu sáng hoặc kích thước tổn thương quá nhỏ) hoặc chuẩn bị nội dung thảo luận chuyên môn.

**Current workflow (Tính trung bình cho mỗi paper được chọn đọc kỹ):**  
1. Tìm kiếm và chọn lọc: Tìm trên ArXiv / Google Scholar và đọc lướt Abstract/Conclusion của ~10 papers để chọn ra 3-5 bài đọc kỹ (45 phút - khoảng 4.5 phút/bài bao gồm thao tác tìm, tải và lọc).
2. Đọc lướt phần giới thiệu (Introduction) & công việc liên quan (Related Work) của bài được chọn (15 phút).
3. Đọc chi tiết phần Kiến trúc mạng & Phương pháp (Methodology), nỗ lực giải nghĩa các công thức toán và ký hiệu (notation) (35 phút).
4. Đọc phần Thực nghiệm & So sánh Baseline (Experiments), đối chiếu các chỉ số mAP, Precision/Recall nằm rải rác ở các bảng (25 phút).
5. Tổng hợp các điểm chính và lưu lại kết quả so sánh vào Notion (15 phút).
*Tổng thời gian thực tế tiêu tốn cho mỗi paper chất lượng: ~90 phút.*

**Bottleneck:**  
Bước 3 và 4: Giải nghĩa các công thức toán phức tạp, ký hiệu (notation) không chuẩn hóa trong phần Methodology và đối chiếu thủ công các bảng chỉ số hiệu năng (mAP, Precision/Recall) so với baseline trong phần Experiments. Mất trung bình 60 phút/paper cho hai bước này.

**Impact:**  
Tốn khoảng 6-8 tiếng/tuần chỉ để đọc hiểu tài liệu chuyên ngành, làm giảm thời gian thực tế dành cho việc code và huấn luyện mô hình.

**Success metric:**  
- Giảm thời gian từ khi mở paper đến khi hoàn thành cấu trúc tóm tắt (Core Idea, Architecture logic, Key Metrics) xuống dưới 30 phút/paper.
- Độ chính xác trích xuất thông tin (đặc biệt là các chỉ số chính và cấu trúc layer chính) đạt trên 95% sau khi kiểm chứng nhanh bằng mắt hoặc so sánh với code thực tế.

**Non-AI alternative:**  
- Tìm và đọc trực tiếp source code chính thức (official GitHub) hoặc các bài blog giải thích của cộng đồng (Medium, PapersWithCode) để hiểu logic mô hình thay vì cố đọc công thức toán trong PDF.
- Sử dụng Notion template cố định định hình sẵn các trường thông tin cần điền (Problem, Method, SOTA Metrics, App).
- Dùng các công cụ trực quan hóa liên kết bài báo như Connected Papers hay Semantic Scholar để lọc nhanh bài báo có trích dẫn chất lượng.

**AI hypothesis:**  
Sử dụng LLM (thông qua giao diện Chat sẵn có như Claude Projects/ChatGPT) với một bộ System Prompt chuyên dụng được thiết kế riêng để đọc hiểu cấu trúc PDF học thuật, dịch giải công thức toán phức tạp sang ngôn ngữ tự nhiên, trích xuất cấu trúc layer và tổng hợp bảng so sánh baseline. Tránh tự xây dựng hệ thống Agent riêng quá sớm khi chưa tối ưu hóa Prompting.

**Quick gut:**  
Workflow.

### Draft current workflow

```text
CURRENT STATE — 90 phút/paper (không tính 45 phút tìm & lọc ban đầu)

[1 Đọc lướt Intro & Related Work: 15'] 
→ [2 Đọc chi tiết Methodology (Giải mã Toán/Notation): 35']  <--- bottleneck
→ [3 Đọc chi tiết Experiment (Đối chiếu Baseline/Table): 25']  <--- bottleneck
→ [4 Tổng hợp thủ công vào Notion: 15']
```

### Draft future workflow

```text
FUTURE STATE — 30 phút/paper

[1 Đọc lướt nhanh Intro & Related Work: 5']
→ [2 LLM dịch giải công thức toán & cấu trúc module chính: 5']
→ [3 Toàn kiểm chứng chéo phần công thức quan trọng và đối chiếu baseline từ PDF/Code: 15'] <-- human boundary
→ [4 Xuất tóm tắt tự động sang Notion: 5']

Fallback: LLM dịch sai ký hiệu/chỉ số -> Toàn mở bản PDF gốc hoặc check source code chính thức để đối chiếu nhanh.
```

## Problem Cards #2 và #3 — tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| **Phân tích Loss Curves (Overfit/Underfit)** | Toàn | Phân tích biểu đồ loss curves và debug code huấn luyện | 40 phút → 15 phút | Workflow | Mức độ mơ hồ cao hơn và phụ thuộc nhiều vào định dạng log thô của từng thư viện train. |
| **Cập nhật siêu tham số thủ công** | Toàn | Nhập liệu thủ công các tham số và kết quả run epoch vào Notion/Excel | 10 phút → 0 phút (tự động) | Rule | Có thể giải quyết hoàn toàn bằng script Python tự động log hoặc tích hợp công cụ như WandB (No-AI). |
