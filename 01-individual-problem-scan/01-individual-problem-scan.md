# 01 — Individual Problem Scan

## Scan rộng

Nam scan 5 problems từ trải nghiệm thực tế của bản thân - một sinh viên năm cuối đang thực hiện khóa luận tốt nghiệp về **"Nhận diện hành vi bất thường trong video giám sát sử dụng Spatio-Temporal Graph Neural Networks (ST-GNN)"**.

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | **Lặp lại** | Cập nhật bảng theo dõi siêu tham số (Excel/Notion) thủ công sau mỗi lần run model | Nam | Mất 5-10 phút sau mỗi lần chạy thí nghiệm, dễ ghi sai số hoặc thiếu phiên bản code tương ứng. |
| 2 | **Tốn thời gian** | Đọc và tóm tắt 3-5 paper mới (ArXiv) mỗi tuần để tìm giải pháp cải tiến mô hình | Nam | Mất 45-60 phút/paper; khó nhớ hết các chi tiết kiến trúc mạng và cấu hình hyperparameter của họ. |
| 3 | **Tốn thời gian** | Format và vẽ biểu đồ so sánh kết quả giữa các kiến trúc model khác nhau (VGG, ResNet, Transformer...) | Nam | Mất 30-40 phút loay hoay với `matplotlib` hoặc `seaborn` cho đúng chuẩn định dạng bài báo khoa học. |
| 4 | **AI có thể tốt hơn** | Viết phần giải thích nguyên nhân mô hình bị Overfitting/Underfitting dựa trên log Loss & Validation | Nam | Mất nhiều thời gian phân tích thủ công; AI có thể nhận diện các pattern phổ biến của loss curve nhanh hơn. |
| 5 | **Pain từ người khác** | GVHD/Mentor phàn nàn vì báo cáo tiến độ tuần chỉ chứa số liệu thô (raw metrics), thiếu phân tích so sánh với baseline của Lab | GVHD, Mentor | GVHD mất thêm 15-20 phút họp mỗi tuần để hỏi dồn dập nhằm làm rõ Nam đã cải tiến những gì. |

Vì sao phần scan này mạnh:

- Tập trung vào các tác vụ thực tế của một AI Engineer tập sự (huấn luyện mô hình, đọc nghiên cứu khoa học, viết báo cáo lab).
- Phân biệt rõ các lăng kính (Lặp lại, Tốn thời gian, AI tốt hơn, Pain từ người khác).
- Có số liệu đo lường cụ thể làm bằng chứng (thời gian tiêu tốn, tần suất lặp lại).
- Không bắt đầu bằng giải pháp hay ý tưởng làm Chatbot chung chung.

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | **Paper Summarization (Tóm tắt paper)** | Workflow rất rõ ràng, tốn nhiều thời gian đọc hiểu mỗi tuần, AI hỗ trợ xử lý thông tin ngôn ngữ cực tốt. | Cách xử lý phần công thức toán học phức tạp và sơ đồ kiến trúc trong PDF. |
| 2 | **Phân tích Loss Curves (Overfit/Underfit)** | Có pain thật, ảnh hưởng trực tiếp tới việc đưa ra quyết định tối ưu model tiếp theo. | Dữ liệu đầu vào (loss log) cần được tiền xử lý thế nào để AI đọc được chính xác. |
| 3 | **Cập nhật siêu tham số thủ công** | Tần suất lặp lại cao mỗi khi chạy training. | Vấn đề này có thể giải quyết triệt để bằng script tự động hóa (non-AI). |

## Problem Card #1 — Đọc & tóm tắt paper mới (Paper Summarization)

**Problem 1 câu:**  
Mỗi tuần Nam mất khoảng 3-4 tiếng để đọc và tóm tắt 3-5 bài báo khoa học mới trên ArXiv để tìm ý tưởng cải tiến mô hình ST-GNN của mình, trong đó việc hiểu nhanh phương pháp đề xuất (Methodology) và so sánh baseline là bước tốn thời gian nhất.

**Actor:**  
Sinh viên năm cuối làm khóa luận tốt nghiệp ngành AI (Topic: Nhận diện hành vi bất thường bằng ST-GNN).

**Thời điểm / bối cảnh:**  
Giữa tuần, khi cần tìm giải pháp tối ưu cho mô hình hiện tại hoặc chuẩn bị nội dung thảo luận với lab.

**Current workflow:**  
1. Lên ArXiv / Google Scholar tìm các paper liên quan đến bài toán. (5 phút)
2. Tải file PDF về máy và mở bằng công cụ đọc PDF. (5 phút)
3. Đọc lướt qua Abstract, Introduction và Conclusion để lọc ra các bài chất lượng và phù hợp nhất. (10 phút)
4. Đọc chi tiết phần Methodology để trích xuất cấu trúc kiến trúc mạng chính và các công thức tối ưu hóa. (20 phút - **Bottleneck**)
5. Đọc phần Experiment để trích xuất các bảng dữ liệu kết quả thử nghiệm so sánh với baseline. (15 phút - **Bottleneck**)
6. Viết tóm tắt core idea, ưu nhược điểm và ý tưởng ứng dụng vào Notion cá nhân. (5 phút)

**Bottleneck:**  
Bước 4 và 5: Đọc chi tiết Methodology và Experiment để đối chiếu số liệu. Cụ thể là mất quá nhiều thời gian để trích xuất cấu trúc siêu tham số (hyperparameters), bảng so sánh kết quả vì chúng bị chia nhỏ thành nhiều phần trong PDF hoặc sử dụng ký hiệu phức tạp.

**Impact:**  
Tốn khoảng 3-4 tiếng/tuần chỉ để đọc hiểu tài liệu, làm giảm thời gian thực tế dành cho việc code và train mô hình.

**Success metric (Observable):**  
- Giảm thời gian đọc hiểu và viết tóm tắt mỗi paper từ 60 phút xuống dưới 20 phút.
- Sau khi đọc bản tóm tắt, Nam có thể trình bày trực tiếp core idea và 2 điểm cải tiến chính của paper đó cho Mentor trong 3 phút mà Mentor không phải hỏi vặn lại các điểm mơ hồ về kiến trúc mạng.

**Non-AI alternative:**  
- Sử dụng các Notion template cấu trúc sẵn để ghi chép có hệ thống.
- Đọc trực tiếp file cấu hình `.yaml` hoặc file `README.md` trong link Github chính thức đính kèm của bài viết (nếu có) thay vì đọc file PDF thô.
- Mô hình thảo luận nhóm (Reading Group): chia mỗi thành viên trong lab đọc kỹ 1 bài rồi thuyết trình lại cho nhau nghe.

**AI hypothesis:**  
Sử dụng AI phân tách từng bước: trước tiên trích xuất bảng kết quả thực nghiệm và thông số cấu hình chính từ PDF, sau đó giải thích chi tiết cơ chế hoạt động mạng (ST-GNN) so sánh trực tiếp với baseline hiện tại của Nam.

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
→ [2 AI bước 1: Trích xuất bảng kết quả & thông số hyperparameter từ PDF: 2']
→ [3 AI bước 2: Gợi ý giải thích so sánh kiến trúc so với baseline của Nam: 1']
→ [4 Nam review chéo kết quả AI trích xuất với bản PDF gốc: 8'] <-- human boundary (Kiểm soát hallucination)
→ [5 Nam lưu vào Notion: 2']

Fallback: AI tóm tắt sai/thiếu -> Nam tự mở bản PDF gốc để đọc lại phần cần làm rõ.
```

---

## Problem Cards #2 và #3 — tóm tắt

| Card | Actor | Bottleneck | Metric | Quick gut | Vì sao chưa chọn làm #1 |
|---|---|---|---|---|---|
| **Phân tích Loss Curves (Overfit/Underfit)** | Nam | Phân tích biểu đồ loss curves và debug code huấn luyện | 40 phút → 15 phút | Workflow | Mức độ mơ hồ cao hơn và phụ thuộc nhiều vào định dạng log thô của từng thư viện train. |
| **Cập nhật siêu tham số thủ công** | Nam | Nhập liệu thủ công các tham số và kết quả run epoch vào Notion/Excel | 10 phút → 0 phút (tự động) | Rule | Có thể giải quyết hoàn toàn bằng script Python tự động log hoặc tích hợp công cụ như WandB (No-AI). |

---

## Chọn card muốn pitch nhất

* **Card tôi muốn pitch nhất:** Đọc & tóm tắt paper mới (Paper Summarization)
* **Vì sao:** Đây là công việc lặp lại có tính hệ thống cao trong nghiên cứu AI. Giải quyết được bài toán này giúp giải phóng đáng kể quỹ thời gian đọc hiểu lý thuyết để Nam tập trung vào coding/training thực tế.
* **Câu hỏi tôi muốn nhóm challenge:** Làm thế nào để đảm bảo AI trích xuất đúng các ký hiệu toán học và cấu trúc đồ thị (Spatial-Temporal) phức tạp trong paper mà không bị lỗi hiển thị hoặc hiểu sai ngữ cảnh thuật toán?
