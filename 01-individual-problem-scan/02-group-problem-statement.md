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
| **Paper Summarization** (Nam) | 5 | 5 | 5 | 5 | 5 | 5 | 5 | 35 |
| **Root Cause từ System Logs** (Bạn B) | 5 | 5 | 4 | 5 | 3 | 4 | 3 | 29 |
| **Làm sạch dữ liệu Excel** (Bạn B) | 4 | 5 | 4 | 4 | 4 | 5 | 4 | 30 |
| **Tổng hợp kiến thức Course+Note+GitHub** (Bạn A) | 4 | 3 | 4 | 4 | 3 | 4 | 4 | 26 |
| **Phân tích Loss Curves** (Nam) | 4 | 4 | 4 | 3 | 4 | 3 | 4 | 26 |

Nhóm chọn: **Paper Summarization (Tóm tắt paper)**

Vì sao chọn:
- Workflow rõ ràng nhất trong tất cả candidates, lặp lại hàng tuần với mọi sinh viên làm khóa luận hoặc nghiên cứu AI.
- Pain evidence rõ ràng: cả Nam và Bạn A đều gặp vấn đề tương tự ("save hàng chục tab nhưng đọc không hết", tốn 4-5 tiếng/tuần).
- Success metric đo được cả thời gian lẫn chất lượng truyền đạt.
- Nhóm hiểu domain tốt nhất vì cả 3 người đều đọc paper thường xuyên.

Vì sao không chọn các ứng viên khác:
- *Root Cause từ System Logs*: Workflow rõ, impact lớn, nhưng cấu trúc log mỗi dự án khác nhau và nhóm không có log thật để demo trong lab.
- *Làm sạch dữ liệu Excel*: Pain kinh điển nhưng có thể giải quyết triệt để bằng Rule/Script (pandas, regex) mà không cần AI — điểm mạnh nhưng cũng là lý do không cần đào sâu thêm.
- *Tổng hợp kiến thức*: Nguồn dữ liệu (course slides, notes, code repos) quá rời rạc, khó gom và chuẩn hóa trong thời gian lab.
- *Phân tích Loss Curves*: Phụ thuộc vào framework (PyTorch/TF) và kiểu kiến trúc mô hình, khó xây dựng luồng chuẩn hóa chung.


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

## Research giải pháp

Nhóm tìm các hướng đã có sẵn, không giả định phải tự build từ đầu.

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| Semantic Scholar | https://www.semanticscholar.org/ | Tìm kiếm, lọc paper theo trích dẫn, keyword và topic | Lọc nhanh paper chất lượng dựa trên citation graph | Không tóm tắt Methodology/Architecture chi tiết | Dùng để lọc paper ở bước đầu, giảm thời gian tìm kiếm |
| Connected Papers | https://www.connectedpapers.com/ | Trực quan hóa mạng lưới liên kết giữa các paper | Giúp thấy landscape nghiên cứu, tìm paper liên quan nhanh | Không trích xuất nội dung chi tiết | Kết hợp với bước lọc paper, không thay thế bước đọc sâu |
| ChatGPT / Claude (upload PDF) | https://openai.com/chatgpt | Tóm tắt paper, trích xuất key ideas, so sánh phương pháp | Hiểu ngôn ngữ tốt, trích xuất core idea nhanh | Có thể hallucinate số liệu, bỏ sót công thức toán, không đọc hình/sơ đồ kiến trúc tốt | AI draft tóm tắt, người đọc kiểm chứng lại với PDF gốc |
| Paper Digest / SciSummary | https://www.scienceopen.com/ | Tóm tắt tự động paper khoa học | Nhanh, có cấu trúc | Chất lượng tóm tắt không đồng đều, thiếu ngữ cảnh bài toán của mình | Pattern tốt: AI tóm tắt chung, người đọc tự liên hệ với bài toán cụ thể |

Research takeaway:

```text
Không nên xây agent đọc paper tự động từ đầu đến cuối. Hướng hợp lý là Workflow: dùng tool lọc paper (Semantic Scholar / Connected Papers) → upload PDF vào AI để trích xuất cấu trúc kiến trúc và bảng so sánh baseline → Nam review tóm tắt đối chiếu với PDF gốc ở phần công thức/thiết lập thực nghiệm quan trọng.
```

## Workflow before/after

Nội dung workflow:

```text
CURRENT STATE — 6 bước, 95 phút/paper

[1 Tìm paper trên ArXiv/Scholar: 15']
→ [2 Đọc Abstract/Conclusion để lọc: 15']
→ [3 Đọc lướt Introduction: 10']
→ [4 Đọc chi tiết Methodology/Architecture: 25']  <-- bottleneck
→ [5 Đọc Experiments & so sánh Baseline: 20']      <-- bottleneck
→ [6 Viết tóm tắt vào Notion: 10']

FUTURE STATE — 4 bước, 35 phút/paper

[1 Lọc paper bằng Semantic Scholar / Connected Papers: 10']  -- Tool hỗ trợ
→ [2 Upload PDF → AI trích xuất: kiến trúc chính, bảng baseline, key contribution: 3']  -- Workflow step
→ [3 Nam review tóm tắt AI, đối chiếu PDF gốc ở phần công thức & thiết lập thực nghiệm: 20']  -- Human boundary
→ [4 Lưu tóm tắt đã kiểm chứng vào Notion: 2']

Fallback:
AI tóm tắt sai kiến trúc hoặc bịa số liệu baseline → Nam mở PDF gốc đọc lại section tương ứng.

Bottleneck mới:
Nam review + đối chiếu. Đây là bottleneck chấp nhận được vì đó là bước đảm bảo Nam thực sự hiểu paper, không chỉ lướt qua.
```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Tổng thời gian/paper | 95 phút | Dưới 35 phút | Target chính |
| Số bước | 6 | 4 | Gộp bước lọc + đọc lướt; AI xử lý trích xuất |
| Bước thủ công nặng | 3/6 (bước 4, 5, 6) | 1/4 (bước 3) | Nam chỉ review, không đọc toàn bộ từ đầu |
| Bottleneck chính | Đọc Methodology + Experiments | Review + đối chiếu | Human boundary |
| Risk mới | Không có | AI hallucinate số liệu / bỏ sót module quan trọng | Cần đối chiếu PDF gốc |

## Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** | Sinh viên năm cuối làm khóa luận tốt nghiệp ngành AI. |
| **Workflow** | Mỗi tuần tìm paper trên ArXiv → lọc bằng Abstract/Conclusion → đọc chi tiết Methodology & Experiments → viết tóm tắt vào Notion. |
| **Bottleneck** | Bước đọc chi tiết Methodology và Experiments mất 45 phút/paper vì nhiều sơ đồ kiến trúc phức tạp và bảng số liệu phân tán. |
| **Impact** | Tốn 4-5 tiếng/tuần chỉ để đọc hiểu tài liệu, giảm thời gian thực tế dành cho code và train mô hình. |
| **Success Metric** | Giảm thời gian đọc + tóm tắt mỗi paper từ 95 phút xuống dưới 35 phút; Nam trình bày được core idea cho Mentor trong 2 phút mà Mentor không cần hỏi lại quá 1 câu. |
| **Boundary** | AI không thay Nam quyết định paper nào đáng đọc kỹ; AI không tự bịa số liệu thực nghiệm; AI không thay Nam viết phần liên hệ với bài toán khóa luận. |

## Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Notion template cố định + Connected Papers để lọc nhanh + chỉ đọc Abstract/Conclusion | Đủ nếu chỉ cần biết paper có liên quan hay không, không cần hiểu sâu | Bỏ lỡ chi tiết kiến trúc và thiết lập thực nghiệm quan trọng | Dùng cho bước lọc paper, không đủ cho bước đọc sâu |
| **Workflow** | Tool lọc paper → AI trích xuất cấu trúc + bảng baseline từ PDF → Nam review + đối chiếu → Lưu Notion | Hợp vì workflow tuyến tính, AI chỉ hỗ trợ bước trích xuất ngôn ngữ/bảng biểu | AI hallucinate số liệu, bỏ sót module, tóm tắt toán sai | **Chọn** |
| **Agent** | Agent tự tìm paper, tự đọc, tự so sánh với model hiện tại, tự đề xuất hướng cải tiến | Chỉ cần nếu workflow nhiều nhánh và cần tự quyết định paper nào đọc tiếp | Quá rộng, nhiều risk hallucination, mất kiểm soát chất lượng | Chưa chọn |

Mức chọn:

```text
Workflow.
```

Vì sao:
- Bước lọc paper có thể dùng tool/rule (Semantic Scholar, Connected Papers).
- Bước trích xuất cấu trúc và bảng baseline cần AI hỗ trợ ngôn ngữ.
- Nam vẫn review nên hallucination risk kiểm soát được.
- Chưa cần agent vì workflow không cần AI tự quyết paper nào đáng đọc hay tự đề xuất hướng nghiên cứu.

Vì sao không chọn mức đơn giản hơn:
- Rule (chỉ template + đọc Abstract) không đủ vì bottleneck nằm ở việc hiểu Methodology/Experiments — phần này cần AI hỗ trợ trích xuất cấu trúc, không chỉ là format.

## Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** | Sinh viên năm cuối làm khóa luận tốt nghiệp ngành AI. |
| **Workflow** | Tìm paper trên ArXiv/Scholar → lọc bằng Abstract/Conclusion → đọc chi tiết Methodology & Experiments → viết tóm tắt vào Notion. |
| **Bottleneck** | Đọc chi tiết Methodology (hiểu kiến trúc mới) và Experiments (so sánh bảng chỉ số với baseline) mất 45 phút/paper. |
| **Impact** | 4-5 tiếng/tuần cho 3-5 papers; giảm thời gian code và train mô hình. |
| **Success Metric** | Giảm thời gian xuống dưới 35 phút/paper; Nam trình bày core idea cho Mentor trong 2 phút mà Mentor không cần hỏi lại quá 1 câu. |
| **Boundary** | AI không tự chọn paper, không tự bịa số liệu, không thay Nam liên hệ với bài toán khóa luận. |
| **AI intervention point** | Sau khi Nam lọc xong paper đáng đọc, trước bước Nam đọc chi tiết Methodology/Experiments. |
| **Mức chọn** | Workflow: tool lọc paper, AI trích xuất cấu trúc + bảng baseline, Nam review. |
| **Rủi ro & người thật kiểm tra** | Risk: hallucinate số liệu, bỏ sót module kiến trúc, tóm tắt toán sai. Người thật: Nam đối chiếu tóm tắt AI với PDF gốc ở phần công thức và bảng kết quả trước khi lưu. |

## Final decision

Decision:

```text
Go với scope nhỏ.
```

Pilot nhỏ nhất:

- Chọn 3 paper Nam đã đọc trong 2 tuần gần nhất (đã có tóm tắt thủ công làm benchmark).
- Upload PDF vào ChatGPT/Claude với prompt chuẩn: trích xuất kiến trúc chính, key contribution, bảng so sánh baseline.
- Nam đối chiếu output AI với bản tóm tắt thủ công của mình.
- Đo: thời gian tiết kiệm, số lỗi sai/thiếu trong tóm tắt AI, số lần phải mở lại PDF gốc.

Exit / rollback:

- Nếu Nam vẫn phải đọc lại hơn 70% nội dung PDF gốc sau khi đọc tóm tắt AI trong 2 tuần liên tiếp → quay về dùng Notion template + chỉ đọc thủ công.
- Nếu AI bịa số liệu baseline hoặc tóm tắt sai kiến trúc (>2 lần/tuần) → không dùng AI cho phần Experiments, chỉ dùng cho phần tóm tắt ngôn ngữ (Abstract, Related Work).

Decision rationale:

- Problem rõ, workflow rõ, metric rõ.
- Có non-AI components (Semantic Scholar, Connected Papers, Notion template).
- AI nằm ở một bước cụ thể (trích xuất cấu trúc + bảng baseline), không ôm toàn bộ workflow.
- Human review rõ ràng: Nam đối chiếu với PDF gốc trước khi lưu.

---
