# 02 — Group Problem Statement

## Group convergence

Nhóm 3 người, mỗi người share top 3. Tổng cộng 9 candidates.


### Gom trùng / cluster

| Cluster | Candidates included | Pattern chung |
|---|---|---|
| **Tóm tắt & tổng hợp kiến thức** | - Paper Summarization <br>- Đọc quá nhiều tài liệu AI mới <br>- Chưa có hệ thống tổng hợp kiến thức từ course + note + GitHub | Tìm kiếm, chọn lọc và chuyển đổi thông tin chuyên môn kỹ thuật từ nhiều nguồn rời rạc thành kiến thức có cấu trúc để học tập và nghiên cứu. |
| **Xử lý & Chuẩn bị dữ liệu** | - Làm sạch dữ liệu Excel trước khi Import DB <br>- Tạo mock data chuẩn ràng buộc cho SQL Server <br>- Cập nhật siêu tham số thủ công | Chuẩn bị, làm sạch hoặc sinh dữ liệu theo đúng cấu trúc/ràng buộc trước khi đưa vào hệ thống. Thường lặp lại và có thể chuẩn hóa bằng Rule hoặc script. |
| **Giám sát & Phân tích kỹ thuật** | - Phân tích Loss Curves <br>- Phân tích Root Cause từ System Logs | Đọc hiểu log/biểu đồ kỹ thuật để chẩn đoán nguyên nhân lỗi và đưa ra quyết định xử lý. Bottleneck nằm ở việc đọc thủ công và cần hiểu ngữ cảnh. |
| **Truyền thông & Phối hợp** | - Nhiều kênh liên lạc thông báo rời rạc  | Thông tin phân tán qua nhiều kênh, dễ bỏ sót thông báo quan trọng. |

## Shortlist và score

Chấm điểm các ứng viên tiềm năng nhất (chọn đại diện tốt nhất từ mỗi cluster) để đưa ra đồng thuận:

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Tổng hợp kiến thức Course+Note+GitHub** (Bạn A) | 5 | 5 | 5 | 5 | 5 | 4 | 5 | 34 |
| **Paper Summarization** (Nam) | 5 | 5 | 4 | 5 | 5 | 5 | 4 | 33 |
| **Làm sạch dữ liệu Excel** (Bạn B) | 4 | 5 | 4 | 4 | 4 | 5 | 4 | 30 |
| **Root Cause từ System Logs** (Bạn B) | 5 | 5 | 4 | 5 | 3 | 4 | 3 | 29 |
| **Phân tích Loss Curves** (Nam) | 4 | 4 | 4 | 3 | 4 | 3 | 4 | 26 |

Nhóm chọn: **Tổng hợp kiến thức Course+Note+GitHub**

Vì sao chọn:
- Đây là nỗi đau thực tế và cực kỳ nhức nhối đối với cả nhóm và hầu hết học viên học AI. Khi học lý thuyết trong slide/course (chứa đầy công thức toán học, sơ đồ trừu tượng), ghi chép note cá nhân rời rạc, và code thực hành (các repository trên GitHub, notebook) bị đứt gãy. Khi cần ôn tập hoặc làm dự án, nhóm phải lục tìm và đối chiếu chéo rất mất thời gian.
- Có workflow và baseline thời gian rõ ràng để so sánh (thời gian ôn tập, tra cứu đối chiếu lý thuyết - code).
- Dễ dàng thực hiện trong lab vì nhóm có sẵn slide bài giảng lý thuyết và các repository chứa mã nguồn tương ứng của môn học.

Vì sao không chọn các ứng viên khác:
- *Paper Summarization*: Dù workflow rõ nhưng các công cụ tóm tắt PDF thông thường (như SciSummary, ChatPDF) đã giải quyết khá tốt. Vấn đề không chỉ là tóm tắt một bài báo riêng lẻ mà là kết nối các nguồn học liệu đa dạng để thực hành.
- *Root Cause từ System Logs*: Ý tưởng hay nhưng cấu trúc log của mỗi hệ thống doanh nghiệp rất khác nhau, khó có dữ liệu thực tế đầy đủ để thử nghiệm và demo trong lab.
- *Làm sạch dữ liệu Excel*: Vấn đề này phần lớn có thể giải quyết triệt để bằng các rule/script python truyền thống (pandas, regex) mà không nhất thiết cần đến sức mạnh của AI.
- *Phân tích Loss Curves*: Rất khó chuẩn hóa vì mỗi mô hình và tập dữ liệu sinh ra các loss curves đặc thù, rủi ro AI đánh giá sai là rất cao.

## Quick validation

Nhóm thực hiện khảo sát nhanh và phỏng vấn trực tiếp học viên trong lớp:

| Nguồn | Số người | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| **Phỏng vấn trực tiếp** | 3 bạn học viên cùng lớp học AI | 3/3 bạn đều thừa nhận dành rất nhiều thời gian (chiếm ~60% thời gian ôn tập) để đối chiếu dòng code trên GitHub đang chạy công thức toán học cụ thể nào trong slide bài giảng. | Không có tín hiệu phản bác trực tiếp, cả 3 đều thấy đây là bottleneck lớn. | Tập trung AI vào bước **ánh xạ (mapping) và giải thích chi tiết mối liên hệ** giữa các đoạn code quan trọng và các phần lý thuyết/công thức tương ứng trong slide bài học. |
| **Discord Poll (Lớp học)** | 10 học viên | 8/10 người thường xuyên bị mất dấu mối liên hệ giữa lý thuyết toán của mô hình và code hiện thực thực tế sau 1-2 tuần học. | 2/10 người chỉ tập trung chạy code chạy được và tinh chỉnh tham số theo cảm tính, không quan tâm đối chiếu công thức toán. | Bổ sung phần tóm tắt ngắn gọn trực quan về lý thuyết toán đi kèm ngay trong phần chú thích code do AI tạo ra để học viên dễ tiếp cận. |

Insight sau validation:
```text
Pain thật không nằm ở việc thiếu tài liệu học tập (slide bài giảng hay code GitHub đều có sẵn), mà là sự đứt gãy trong việc "dịch chuyển" giữa ngôn ngữ toán học (slide) và ngôn ngữ lập trình (code thực tế), khiến việc ôn tập và hiểu bản chất mô hình mất rất nhiều thời gian.
```

## Research giải pháp

Nhóm tìm các hướng công cụ hiện có để phân tích ưu nhược điểm:

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Obsidian / Notion | https://obsidian.md / https://www.notion.so | Lưu trữ tài liệu học tập, viết note cá nhân | Quản lý ghi chú tốt, liên kết backlinks mạnh mẽ | Phải tự tạo liên kết thủ công bằng tay, không tự động hiểu code hay slide | Là destination lưu trữ note cuối cùng, cần AI làm trung gian kết nối |
| NotebookLM | https://notebooklm.google.com/ | Chat và tổng hợp thông tin từ nhiều tài liệu tải lên | Hiểu ngữ cảnh tài liệu PDF/slide rất tốt, trích xuất chính xác thông tin text | Không thể import và phân tích sâu cấu trúc code từ link GitHub repo một cách trực tiếp | NotebookLM tốt để hiểu lý thuyết slide, nhưng cần tích hợp thêm luồng xử lý mã nguồn để sinh mapping |
| GitHub Copilot / Cursor | https://github.com/features/copilot | Giải thích code và hỗ trợ viết code trực tiếp trong IDE | Hiểu sâu mã nguồn, luồng chạy, các biến và thư viện | Không có ngữ cảnh của slide bài học bên ngoài (PDF/PPT) để đối chiếu trực tiếp | Cần nạp cả code và slide PDF vào cùng một ngữ cảnh LLM để sinh ra mapping hai chiều |

Research takeaway:
```text
Không nên tự build một hệ thống RAG phức tạp từ đầu. Hướng đi tối ưu là Workflow: 
Sử dụng script để lấy nội dung code chính và cấu trúc project GitHub -> Nạp Slide bài giảng PDF + Code thô vào LLM (Claude/Gemini) -> LLM sinh ra Markdown Note chứa liên kết 2 chiều (VD: "Hàm Forward ở dòng 35-50 trong model.py chính là hiện thực hóa công thức tính Attention tại trang 12 của Slide") -> Học viên review và lưu vào Notion/Obsidian.
```

## Workflow before/after

Nội dung workflow:

```text
CURRENT STATE — 5 bước, 120 phút/chủ đề ôn tập

[1 Đọc lại slide lý thuyết để nắm vững công thức toán: 20']
→ [2 Mở GitHub repo, tìm kiếm các file code hiện thực hóa chính: 20']
→ [3 Đọc code, đối chiếu thủ công từng dòng code xem chạy công thức toán nào trong slide: 40'] <-- bottleneck
→ [4 Tự viết tay/gõ note tổng hợp giải thích mối liên hệ vào Notion: 30'] <-- bottleneck
→ [5 Lưu trữ và tổ chức lại note học tập để ôn tập: 10']

FUTURE STATE — 4 bước, 35 phút/chủ đề ôn tập

[1 Gom Slide PDF và copy link file code chính từ GitHub: 5']  -- Manual / Rule
→ [2 Chạy AI workflow: Nạp PDF + Code thô -> AI tự động phân tích và sinh draft Note ánh xạ chi tiết (code-to-slide mapping): 3']  -- AI Workflow step
→ [3 Học viên review ghi chú của AI, chạy thử code trên VS Code để verify lại lý thuyết: 22']  -- Human boundary (Trọng tâm học tập)
→ [4 Export ghi chú đã được verify và lưu vào Obsidian/Notion: 5']  -- Tool/Rule hỗ trợ

Fallback:
AI giải thích sai hoặc map nhầm dòng code -> Học viên tự mở file code gốc tra cứu thủ công và sửa lại ghi chú.

Bottleneck mới:
Học viên review và chạy thử code để verify. Đây là bottleneck chấp nhận được vì đó là hoạt động học tập chủ động bắt buộc phải diễn ra để ghi nhớ kiến thức, thay thế cho việc gõ note và đối chiếu thủ công mất thời gian trước đây.
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Tổng thời gian/chủ đề | 120 phút | Dưới 35 phút | Giảm thiểu thời gian tra cứu, tăng thời gian thực hành |
| Số bước | 5 | 4 | Tối giản hóa việc đối chiếu thủ công |
| Bước thủ công nặng | 2/5 (bước 3, 4) | 1/4 (bước 3) | Chỉ tập trung vào review học tập, không tốn công gõ note/đối chiếu |
| Bottleneck chính | Đối chiếu lý thuyết - code | Review & Verify code thực tế | Chuyển dịch từ "tra cứu thủ công" sang "học chủ động" |
| Risk mới | Không có | AI giải thích sai/ảo tưởng mối liên kết giữa toán và code | Cần người đọc chạy thử code và đối chiếu PDF gốc |

## Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Học viên tự học AI hoặc Sinh viên ngành Khoa học dữ liệu / AI. |
| **Workflow** | Học lý thuyết từ slide bài giảng -> Tìm code mẫu tương ứng trên GitHub -> Đối chiếu thủ công xem dòng code nào chạy công thức nào -> Tự gõ ghi chú vào Notion để ôn tập. |
| **Bottleneck** | Bước đối chiếu thủ công lý thuyết (toán, sơ đồ kiến trúc trong slide PDF) và code (các file .py, notebook trên GitHub) tốn 40 phút vì cú pháp lập trình và ký hiệu toán học thường không đồng nhất. |
| **Impact** | Tốn 2-3 tiếng cho mỗi chủ đề bài học, dẫn đến mệt mỏi, dễ bỏ cuộc hoặc học vẹt code mà không hiểu bản chất toán đằng sau. |
| **Success Metric** | Giảm tổng thời gian tổng hợp lý thuyết-code xuống dưới 35 phút; học viên giải thích rõ được hàm code tương ứng với slide nào cho mentor trong 3 phút. |
| **Boundary** | AI không thay thế việc học viên chạy code và hiểu bài; AI không tự ý viết code mới ngoài phạm vi tài liệu; AI chỉ giải thích dựa trên slide và code được cung cấp. |

## Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Dùng template note mẫu trên Notion + quy ước đặt tên biến code giống hệt ký hiệu slide | Đủ nếu giảng viên thiết kế slide và code đồng bộ 100% từ đầu | Hầu hết GitHub repos bên ngoài và slide môn học không đồng bộ ký hiệu, không thể scale | Dùng làm format lưu trữ note, không tự liên kết được |
| **Workflow** | Input (PDF Slide + Code) -> AI phân tích map code-theory -> Tạo Markdown Note -> Học viên Review -> Lưu Notion | Đủ vì quy trình tuyến tính, đầu vào tĩnh (slide + code file cố định), mục tiêu là sinh tài liệu chú thích | AI giải thích sai ký hiệu toán, map nhầm dòng code | **Chọn** |
| **Agent** | Agent tự động phát hiện slide mới, tự động crawl GitHub liên quan, tự debug code và tạo wiki tương tác | Chỉ cần khi nguồn học liệu thay đổi liên tục và cần AI tự quyết định lộ trình học hộ | Quá phức tạp, chi phí cao, rủi ro hallucination làm hỏng kiến thức nền tảng của học viên | Chưa chọn |

Mức chọn:

```text
Workflow.
```

Vì sao:
- Dữ liệu đầu vào (Slide PDF, Code GitHub) là tĩnh và có cấu trúc rõ ràng.
- Tác vụ ánh xạ và giải thích code dựa trên bối cảnh slide là thế mạnh của LLM (Context window lớn, hiểu mã nguồn tốt).
- Học viên vẫn phải review ở cuối để học và kiểm chứng, do đó kiểm soát được rủi ro ảo tưởng (hallucination) của AI.
- Chưa cần Agent vì không có các quyết định động phức tạp hay yêu cầu tương tác thời gian thực với môi trường.

## Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Học viên tự học AI hoặc Sinh viên ngành Khoa học dữ liệu / AI. |
| **Workflow** | Đọc slide lý thuyết -> Tìm code mẫu trên GitHub -> Đối chiếu thủ công lý thuyết với code -> Ghi chép note tổng hợp vào Notion. |
| **Bottleneck** | Đối chiếu thủ công giữa công thức toán/sơ đồ trong slide PDF và các dòng hiện thực hóa trong code GitHub tốn 40 phút/chủ đề bài học do không đồng nhất ký hiệu. |
| **Impact** | Tốn 2-3 tiếng/bài học, gây nản lòng, giảm hiệu suất thực hành, dễ dẫn đến học vẹt code. |
| **Success Metric** | Giảm tổng thời gian xuống dưới 35 phút/chủ đề; học viên trình bày chính xác phần mapping code-lý thuyết cho mentor trong 3 phút mà không bị nhầm lẫn. |
| **Boundary** | AI không học hộ, không tự ý viết thêm code ngoài slide, chỉ giải thích dựa trên tài liệu được cung cấp. |
| **AI intervention point** | Sau khi học viên thu thập đủ slide PDF bài giảng và link file code GitHub tương ứng, trước khi tiến hành đối chiếu viết ghi chú. |
| **Mức chọn** | Workflow: trích xuất code + nạp slide vào LLM để sinh draft mapping note, học viên review. |
| **Rủi ro & người thật kiểm tra** | Risk: AI giải thích sai/map nhầm dòng code với công thức toán. Người thật kiểm tra: Học viên chạy thử code với dữ liệu test và đối chiếu lại với slide PDF ở phần công thức chính trước khi lưu. |

## Final decision

Decision:

```text
Go với scope nhỏ.
```

Pilot nhỏ nhất:
- Chọn 1 chủ đề học cụ thể mà nhóm đã học (ví dụ: Thuật toán K-Means Clustering hoặc Convolutional Layer trong CNN) đã có slide PDF bài giảng và file code mẫu Python.
- Nạp cả slide PDF và file code vào Claude/ChatGPT thông qua prompt thiết kế sẵn để yêu cầu sinh ghi chú ánh xạ (mapping table và code annotation).
- Từng thành viên đối chiếu ghi chú do AI tạo ra với hiểu biết của mình, đo thời gian đọc hiểu và số lượng lỗi sai/nhầm lẫn của AI.
- Đánh giá xem ghi chú đó có giúp hiểu code nhanh hơn không.

Exit / rollback:
- Nếu AI map sai hoặc giải thích sai công thức toán học cốt lõi (>30% số lượng mapping) trong 2 lần thử nghiệm liên tiếp -> Quay lại cách học truyền thống (đọc thủ công và viết note bằng template Notion).
- Nếu việc review ghi chú của AI và chạy thử code kiểm chứng vẫn tốn quá 60 phút/chủ đề -> Hạ thấp scope của AI: chỉ dùng AI để giải thích các hàm code khó hiểu, không bắt AI map toàn bộ slide với code.

Decision rationale:
- Bài toán thực tế, giải quyết được pain point lớn của học viên công nghệ.
- Workflow rõ ràng, đầu vào (PDF Slide, Code file) dễ thu thập và chuẩn hóa.
- AI can thiệp vào bước dịch và liên kết, giúp tiết kiệm thời gian gõ note và tra cứu.
- Có ranh giới rõ ràng: học viên phải review và chạy code (đảm bảo việc học thật).
