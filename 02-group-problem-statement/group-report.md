# Group Report — Day 02

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm |
|-----|-----------|-------------|--------------------|
| 1   | Nguyễn Hoàng Đạt | 2A202601460 | **Domain owner** — pitch candidate được chọn, giải thích bối cảnh embedded, chủ trì vẽ workflow before/after (Phase 5.1-5.2) |
| 2   | Nguyễn Hữu Tuyến | 2A202601520 | **Validation lead** — soạn câu hỏi phỏng vấn/poll, đi hỏi người thật, tổng hợp tín hiệu xác nhận và phản bác (Phase 4.1) |
| 3   | Vũ Thành Khang | 2A202601866 | **Research lead** — tìm 2-3 tool/case/pattern đã có, kiểm link, đối chiếu xem họ giải bước nào trong workflow của nhóm (Phase 4.2) |
| 4   | Hoàng Trường Giang | 2A202601224 | **Problem Statement owner** — viết PS v0/v1, giữ cho metric có baseline + mục tiêu + cách đo, giữ boundary rõ phạm vi làm / không làm (Phase 5.3, 6.2) |
| 5   | Đào Ngọc Duy | 2A202601780 | **Devil's advocate + decision owner** — chủ trì so sánh No AI / Rule / Workflow / Agent, ép nhóm trả lời "vì sao không chọn mức đơn giản hơn", chốt Go / Not Yet / No-Go (Phase 6.1, 6.3) |

Vai trò Devil's advocate cố tình **không** giao cho Đạt, vì Đạt là người đề xuất candidate được chọn — để người đó tự phản biện bài của mình thì nhóm dễ bỏ qua điểm yếu.

Quyết định cuối Go / Not Yet / No-Go do **cả nhóm đồng thuận**, Duy là người chủ trì phần tranh luận.

**Vai trò xoay vòng — mọi người đều phải làm, không ai được ủy quyền:**

| Việc | Ai làm |
|---|---|
| Pitch 3 candidate của mình ở Phase 3.1 | Tất cả |
| Đặt câu hỏi challenge bài của người khác | Tất cả |
| Ghi nhật ký hội tụ (bảng 3.1-3.4) | Luân phiên, mỗi bước một người ghi |
| Viết reflection cá nhân | Tất cả, tự viết, không dùng AI viết thay |

Lý do tách bảng này: 12 điểm cá nhân cho "tham gia pitch + challenge" chấm từng người, không chấm nhóm. Ai im lặng ở Phase 3 thì mất điểm đó dù bản nộp nhóm tốt.

## Phân công theo phase

| Phase | Người chủ trì | Cả nhóm cùng làm |
|---|---|---|
| 3 — Hội tụ | Luân phiên ghi chép | Pitch, cluster, shortlist, chấm điểm, đồng thuận |
| 4.1 — Validation | Validation lead | Cùng nghĩ câu hỏi, chia nhau đi hỏi |
| 4.2 — Research | Research lead | Mỗi người tra 1 tool, cùng kiểm link |
| 4.3 — Ràng buộc NDA | Domain owner | Cùng đánh giá ảnh hưởng tới quyết định |
| 5.1-5.2 — Workflow | Domain owner | Cùng soi từng bước, hỏi lại chỗ chưa rõ |
| 5.3 — PS v0 | PS owner | Cùng phản biện từng field |
| 6.1 — So sánh R/W/A | Duy (devil's advocate) | Cùng tranh luận |
| 6.2 — PS v1 | Giang (PS owner) | Cùng chốt |
| 6.3 — Decision | Duy chủ trì | **Cả nhóm phải đồng thuận** |

## Candidate problem nhóm chọn

> **Chắt lọc tài liệu hãng (datasheet / reference manual / SDK) thành tài liệu nội bộ dùng được cho đội embedded.**
>
> Người đưa ra: Nguyễn Hoàng Đạt (Problem Card #1).
> Trạng thái: đây mới là **candidate problem**. Problem Statement chỉ được viết ở Phase 5 sau khi đã validate và research.

---

# Phase 3 — Nhật ký hội tụ

## 3.1 — Bảng trình bày top 3 của từng người

| # | Người đưa ra | Candidate problem | Người gặp vấn đề | Điểm nghẽn | Cảm nhận nhanh |
|---|---|---|---|---|---|
| 1 | Đạt | Chắt lọc tài liệu hãng thành docs nội bộ | Tech Lead embedded (viết) + ~5 dev (dùng) | Đọc/định vị nội dung trong RM ~3.300 trang, ~12h/dự án | Workflow rõ, baseline đo được |
| 2 | Đạt | Không có chuẩn chung driver/middleware/kiến trúc module | Dev embedded + Tech Lead khi review | Vòng lặp review-sửa 2-3 vòng vì chuẩn chưa thành văn bản | Nhiều khả năng là bài toán process/Rule, không cần AI |
| 3 | Đạt | Dev không tự tìm được câu trả lời trong kho tài liệu | Dev trong team + Tech Lead bị ngắt mạch | Dev tìm 10-15' không ra → hỏi lead → chờ | Impact rộng nhưng rủi ro cao vì output đi thẳng tới dev |
| 4 | Tuyến | Người mua vàng cá nhân phải gọi nhiều cửa hàng để hỏi và so giá | Chị B — phụ nữ 45-60 tuổi, tích trữ vàng, mua 2-4 lần/tháng | Gọi 3-5 cửa hàng rồi tự so sánh trong đầu, ~30' trong tổng 60-90'/lần mua | Pain đời thường dễ hiểu; nhưng giá vàng đã công khai trên web nên có thể chỉ cần Rule |
| 5 | Tuyến | Nhà đầu tư vàng phải tự check nhiều website mỗi sáng | Anh A — nam 28-40 tuổi, nhà đầu tư, theo dõi giá hằng ngày | Mở 4 website (10') + gọi 2-3 cửa hàng chốt giá (15') | Workflow rõ, lặp hằng ngày; metric lợi nhuận khó quy cho tốc độ |
| 6 | Tuyến | Nhân viên cửa hàng vàng không biết giá đối thủ nên không giữ được khách | Chị M — nhân viên bán hàng 25-35 tuổi tại cửa hàng vàng | Không có thông tin giá Doji/PNJ tại thời điểm khách hỏi | Có tác động doanh số rõ; cần kiểm xem "khách bỏ đi 30%" lấy từ đâu |
| 7 | Khang | Đọc tài liệu và báo cáo dài hằng ngày chiếm mất thời gian làm việc khác | Nhân viên văn phòng, BA, PM | Đọc toàn bộ tài liệu rồi tổng hợp, 60-90'/lần | Pain phổ biến nhưng actor còn rộng, cần thu hẹp về một vai trò cụ thể |
| 8 | Khang | Đọc báo cáo tài chính dài trước khi quyết định mua/bán cổ phiếu | Nhà đầu tư, chuyên viên phân tích | Đọc + phân tích chỉ số, 90-120'/báo cáo | Workflow rõ, có draft before/after. Cần thống nhất lại baseline (card ghi 120', metric ghi 10 giờ) |
| 9 | Khang | Giáo viên phải viết nhận xét riêng cho từng học sinh dựa trên điểm | Giáo viên chủ nhiệm | Viết nhận xét 3-5'/học sinh, ~4h/lớp | Bài toán sinh ngôn ngữ rõ nhất, nhưng đụng ranh giới đạo đức: nhận xét phải phản ánh quan sát thật của giáo viên |
| 10 | Giang | Trưởng nhóm phải inbox đôn đốc từng thành viên nhưng bài vẫn trễ sát giờ nộp | Trưởng nhóm bài tập môn học / trưởng ban CLB | Inbox nhắc từng người, 60-90'/tuần; và phải tự gánh sửa bài nộp trễ | Pain thật và ai cũng gặp. Nhưng nhắc nhanh hơn chưa chắc sửa được nguyên nhân gốc là động lực |
| 11 | Giang | Sinh viên đọc slide/tài liệu tiếng Anh 30-40 trang trước buổi học | Sinh viên đại học / chương trình liên kết | Vừa đọc vừa tra từ điển chuyên ngành rồi tự ghi chú, ~60' trong tổng 90' | Cùng pattern với #7, #8. Metric "nắm 100% thuật ngữ" chưa đo được |
| 12 | Giang | Link và quyết định cũ bị trôi trong chat nhóm Zalo/Discord | Thành viên nhóm bài tập / nhóm dự án | Cuộn lại hàng trăm tin nhắn để tìm, 10-15'/lần | Trùng pattern với #3. Người đề xuất tự đánh giá là Rule (bot pin/gán nhãn) — trung thực |
| 13 | Duy | BQL phải tra quy chế rồi soạn lại câu trả lời cho cùng loại thắc mắc của cư dân | Cư dân Vinhomes, BQL, Ban Quản Trị | Cư dân tự tìm 10-15' + BQL tra văn bản quy chế 10-15'/ticket, tổng 25-35'/ticket | Đối thủ mạnh nhất của #1: cũng thuộc cụm A, có 2 actor rõ, quy chế là nguồn kiểm chứng được |
| 14 | Duy | Sinh viên phải nhớ đúng cổng thông tin trong hệ sinh thái website phân tán | Sinh viên VinUni, Phòng Đào tạo | Nhớ/tìm đúng hệ thống rồi tìm đúng chức năng, 5-10'/lần tra cứu | Cả nhóm đều là sinh viên VinUni nên validate cực nhanh. Nhưng phần lớn là bài toán điều hướng — Rule/portal có thể đủ |
| 15 | Duy | Cư dân quên đóng phí hoặc sai cú pháp chuyển khoản, kế toán phải đối soát thủ công | Cư dân, BQL, kế toán | Kế toán kiểm tra giao dịch 5-10' + liên hệ xác minh 5-10'/trường hợp lỗi | Nhắc lịch và đối soát cú pháp là bài toán Rule/tích hợp ngân hàng, gần như không cần AI |

## 3.2 — Gom trùng / cluster

| Cluster | Candidates included | Pattern chung | Ghi chú |
|---|---|---|---|
| A — Biến nguồn thô thành nội dung **người khác** dùng được | #1, #9, #13 | Dữ liệu đã có đủ nhưng không ở dạng người nhận dùng được; cần người có chuyên môn diễn giải lại cho đúng đối tượng | Candidate được chọn nằm ở đây. Giá trị nằm ở phần diễn giải, không nằm ở phần lấy dữ liệu |
| B — Tìm / gom thông tin rời rạc để ra quyết định | #3, #4, #5, #6, #12, #14 | Thông tin nằm rải ở nhiều nguồn hoặc bị trôi, người dùng phải tự gom và tự so sánh | Cụm đông nhất. 3 candidate của Tuyến rơi vào đây, chỉ khác actor: người mua (#4), nhà đầu tư (#5), người bán (#6). #3 và #12 gần như trùng nhau |
| C — Thiếu chuẩn / quy trình thành văn bản | #2 | Chuẩn chỉ nằm trong đầu người có kinh nghiệm, chỉ lộ ra khi review | Lời giải nhiều khả năng là process/Rule, không cần AI |
| D — Đọc tài liệu dài để rút ra thông tin **cho chính mình** | #7, #8, #11 | Nguồn dài, phần thật sự cần rất ít, nhưng phải đọc hết mới biết phần nào cần | Khác cụm A ở chỗ output chỉ phục vụ người đọc, không bàn giao cho người khác |
| E — Việc bị rơi / sai sót trong quy trình định kỳ | #10, #15 | Việc đã có quy trình rõ nhưng vẫn trễ hoặc sai; người chủ trì phải đi đôn đốc và đối soát thủ công | Nguyên nhân gốc là **động lực và kỷ luật con người**, không phải thiếu thông tin. AI khó chạm tới gốc; nhắc lịch và đối soát cú pháp là việc của Rule |

**Ba quan sát khi cluster:**

1. Candidate #1 nằm ở **giao giữa cụm A và cụm D** — vừa phải đọc nguồn rất dài, vừa phải bàn giao kết quả cho người khác dùng.
2. **6/15 candidate (#1, #7, #8, #9, #11, #13) do 4 trong 5 thành viên độc lập nêu ra đều là biến thể của cùng một pain: "đọc nguồn dài rồi chắt lọc lại cho đúng người đọc".** Không ai bàn trước với nhau. Đây là bằng chứng pattern có thật, không phải quan sát riêng của một người.
3. Cụm A có một đặc điểm mà các cụm khác không có: **nguồn gốc kiểm chứng được**. Tài liệu hãng (#1), quy chế nội khu (#13), bảng điểm (#9) đều là văn bản có thẩm quyền để đối chiếu khi AI trả lời sai. Các cụm còn lại thiếu điểm neo này, nên khó đặt boundary và khó đo tính đúng đắn.

## 3.3 — Shortlist

| Candidate | Vì sao vào shortlist | Rủi ro / điều chưa rõ |
|---|---|---|
| #1 — Chắt lọc tài liệu hãng thành docs nội bộ | Workflow lặp lại rõ, có baseline thời gian, bottleneck ở một bước cụ thể, có non-AI alternative thật, human boundary tự nhiên | Đo "docs dễ hiểu" bằng gì? Tài liệu hãng có NDA — có được đưa lên dịch vụ AI ngoài không? Nhóm có tiếp cận được người làm embedded thật để validate không? |
| #5 — Nhà đầu tư tự check giá vàng nhiều website mỗi sáng | Workflow lặp hằng ngày, đo được thời gian, actor cụ thể, dễ validate vì nhiều người quen có thể hỏi được | Giá vàng đã công khai và có cấu trúc sẵn → nhiều khả năng Rule/scraping là đủ, không cần AI. Metric "lợi nhuận +20% nhờ tốc độ" khó chứng minh nhân quả |
| #6 — Nhân viên cửa hàng không biết giá đối thủ | Có tác động doanh số đo được; actor rõ; validate được bằng cách hỏi nhân viên cửa hàng thật | Con số "khách bỏ đi 30%" chưa có nguồn. Lấy giá đối thủ theo thời gian thực có thể vướng vấn đề pháp lý / điều khoản sử dụng của đối thủ |
| #13 — BQL tra quy chế rồi soạn lại câu trả lời cho cư dân | **Đối thủ trực tiếp của #1** — cùng cụm A, cùng pattern "diễn giải nguồn có thẩm quyền cho người khác". Có 2 actor rõ, quy chế là nguồn đối chiếu được, ticket là dấu hiệu thật đếm được | Nhóm có tiếp cận được dữ liệu ticket của BQL không? Quy chế nội khu là tài liệu nội bộ — có được phép xử lý không? Future workflow đề xuất "autopost với case chuẩn" là bỏ người ra khỏi vòng kiểm — rủi ro cao |

## 3.4 — Score và đồng thuận

Chấm 1-5. Điểm chỉ để ép nhóm nói rõ lý do.

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **#1 — Chắt lọc tài liệu hãng thành docs nội bộ** | 5 | 5 | 3 | 5 | 5 | 5 | 3 | **31** |
| #13 — BQL tra quy chế soạn trả lời cho cư dân | 5 | 4 | 3 | 4 | 3 | 4 | 3 | 26 |
| #5 — Nhà đầu tư check giá vàng nhiều nguồn | 4 | 4 | 3 | 3 | 4 | 3 | 3 | 24 |
| #6 — Nhân viên cửa hàng không biết giá đối thủ | 4 | 3 | 2 | 3 | 3 | 3 | 2 | 20 |

Hai điểm số thấp của candidate được chọn là cố ý giữ nguyên, không làm đẹp:

- **Pain có evidence = 3** — baseline hiện mới là ước lượng của một người, chưa có log thời gian hay số ticket. Đây là việc phải làm ở Phase 4.
- **Nhóm hiểu domain = 3** — chỉ Đạt nắm domain embedded, 4 người còn lại phải được giải thích lại. Rủi ro: nhóm dễ gật theo mà không phản biện được.

Hai con số này chính là danh sách việc của Phase 4, không phải lý do loại bài.

**Candidate nhóm chọn:**

```text
Chắt lọc tài liệu hãng (datasheet / reference manual / SDK) thành tài liệu
nội bộ dùng được cho đội embedded.
```

**Vì sao chọn:**

1. **Workflow vẽ được tới từng bước, có thời gian cho mỗi bước.** Đây là điều kiện cần để làm Phase 5 và để so sánh before/after có nghĩa. Nhiều candidate khác mới dừng ở mức mô tả pain.

2. **Bottleneck tách được thành hai loại khác nhau về bản chất.** Bottleneck thời gian là bước đọc và định vị nội dung trong Reference Manual (~12h) — việc tìm kiếm và trích xuất. Bottleneck chất lượng là bước viết phần "khi nào dùng / vì sao / đánh đổi" (~8h) — việc đòi hỏi kinh nghiệm dự án. Nhờ tách được hai loại này, nhóm chỉ ra được chính xác AI nên đứng ở đâu và người phải giữ lại phần nào. Không candidate nào khác làm được điều này rõ như vậy.

3. **Có nguồn gốc để đối chiếu khi AI sai.** Tài liệu hãng là văn bản có thẩm quyền, nên có thể ràng buộc mọi câu AI sinh ra phải kèm số trang và tên register kiểm được. Đây là điểm neo mà phần lớn candidate khác không có.

4. **Có phương án non-AI thật để so sánh.** Template tài liệu + checklist peripheral + thư viện tái sử dụng là giải pháp làm được ngay và giải được một phần bài toán. Nhóm không phải dựng phương án giả để loại.

5. **Hội tụ tự nhiên.** 6/15 candidate (#1, #7, #8, #9, #11, #13) do 4 trong 5 thành viên độc lập nêu ra đều là biến thể của "đọc nguồn dài rồi chắt lọc lại cho đúng người đọc". Không ai bàn trước với nhau. Chọn #1 vì đây là bản có workflow chi tiết nhất trong cụm, có cả người bàn giao lẫn người nhận, và có ràng buộc đúng/sai kiểm chứng được.

**Vì sao chọn #1 mà không chọn #13** (câu hỏi khó nhất, vì hai bài cùng cụm A):

| Tiêu chí | #1 — Tài liệu hãng | #13 — Quy chế nội khu |
|---|---|---|
| Tách bottleneck | Tách rõ thời gian vs chất lượng | Gộp chung thành "tra cứu + soạn trả lời" |
| Human boundary | Người verify và publish mọi bản | Đề xuất "autopost với case chuẩn" — bỏ người ra khỏi vòng kiểm với một phần câu hỏi |
| Hậu quả khi AI sai | Sai lan vào docs nội bộ, nhưng còn 2 lớp chặn: verify trích dẫn và review của senior | Trả lời sai về quy định thi công / thú cưng / tiện ích đi thẳng tới cư dân, gây tranh chấp ngay |
| Validate trong lab | Baseline có thể tự log lại theo từng bước | Cần ticket BQL và quy chế nội khu — nhóm không tiếp cận được |

Kết luận: #13 là candidate tốt và nhóm ghi nhận nó suýt được chọn. Nhóm loại nó vì **không validate được trong phạm vi lab**, không phải vì bài yếu.

**Vì sao không chọn các candidate còn lại:**

- **Cụm C — chuẩn driver/middleware (#2):** pain rõ và có bằng chứng qua comment trong PR, nhưng lời giải đúng là viết chuẩn thành văn bản + linter, tức process/Rule. Nhóm giữ lại làm **đối chứng** khi so sánh No AI / Rule / Workflow / Agent ở Phase 6, vì đây là ví dụ tốt cho việc "pain thật nhưng không cần AI".

- **Cụm B — tìm lại thông tin đã trôi (#3, #12) và điều hướng cổng thông tin (#14):** impact rộng nhưng output đi thẳng tới người dùng cuối, không qua người review. Riêng #14 thì một portal tổng hợp có menu rõ ràng đã giải được phần lớn.

- **Cụm B — giá vàng (#4, #5, #6):** pain có thật và dễ validate, nhưng dữ liệu giá vàng đã công khai và có cấu trúc sẵn. Bài toán chủ yếu là gom và so sánh số, mà Rule/scraping giải được phần lớn. Chọn cụm này thì phần "vì sao cần AI" rất mỏng.

- **Cụm D — đọc tài liệu dài cho chính mình (#7, #8, #11):** cùng pattern với #1 nhưng output chỉ phục vụ người đọc, không bàn giao cho ai. Vì vậy không có ràng buộc chất lượng từ bên ngoài, khó đặt metric và khó đặt boundary. Ngoài ra #8 còn mâu thuẫn baseline: card ghi 120 phút, metric ghi 10 giờ.

- **Cụm E — việc bị rơi trong quy trình định kỳ (#10, #15):** nguyên nhân gốc là động lực và kỷ luật con người, không phải thiếu thông tin. Nhắc nhanh hơn hoặc nhắc "đúng văn phong" không sửa được gốc. Riêng #15 thì nhắc lịch và kiểm cú pháp chuyển khoản là việc của Rule và tích hợp ngân hàng.

**Nếu có bất đồng, nhóm xử lý thế nào:**

Nhóm thống nhất trước ba nguyên tắc:

1. **Không vote ngay.** Ai phản đối phải chỉ rõ phản đối ở tiêu chí nào trong bảng score, không phản đối chung chung.
2. **Ưu tiên bài validate được trong lab.** Khi hai bài gần điểm nhau, chọn bài nhóm tự kiểm chứng được trong 30 phút của Phase 4. Đây chính là lý do #1 thắng #13.
3. **Quyết định có thể đảo ngược.** Nếu Phase 4 phản bác baseline hoặc phát hiện ràng buộc chặn (ví dụ NDA không cho xử lý tài liệu hãng), nhóm quay lại chọn #13. Đổi candidate vì có bằng chứng mới là điều đáng làm, không phải thất bại.

Bất đồng thực tế đã phát sinh: Duy bảo lưu ý kiến rằng #13 có impact rộng hơn vì ảnh hưởng tới hàng nghìn cư dân, trong khi #1 chỉ ảnh hưởng một team ~6 người. Nhóm ghi nhận và trả lời rằng lab chấm chất lượng lập luận chứ không chấm quy mô, và bài không validate được thì không đi tiếp được.

---

## Kết luận Phase 3

| Hạng mục | Kết quả |
|---|---|
| Số candidate ban đầu | 15 (5 người × 3 card) |
| Số cluster | 5 (A, B, C, D, E) |
| Shortlist | 4 (#1, #13, #5, #6) |
| **Candidate được chọn** | **#1 — Chắt lọc tài liệu hãng thành docs nội bộ (31/35)** |
| Candidate dự phòng | #13 — BQL tra quy chế soạn trả lời cho cư dân (26/35) |

Hai việc phải làm ở Phase 4, xuất phát trực tiếp từ hai điểm số thấp:

1. **Nâng "Pain có evidence" từ 3 lên** — Tuyến đi validate, tìm người làm embedded thật hoặc sinh viên từng làm đồ án vi điều khiển để xác nhận pain và baseline.
2. **Nâng "Nhóm hiểu domain" từ 3 lên** — Đạt giải thích lại workflow cho 4 người còn lại đủ kỹ để họ phản biện được, không chỉ gật theo.

Ngoài ra phải làm rõ ràng buộc NDA (mục 4.3) trước khi bàn giải pháp ở Phase 6.

---

# Phase 4 — Quick Validation + Research (30')

## 4.1 — Quick validation

**Người phụ trách:** Tuyến (Validation lead), có Đạt hỗ trợ phần bối cảnh kỹ thuật.

### Chiến lược: 3 tầng nguồn

Nhóm không có ai đang giữ vị trí Tech Lead embedded, nên chia nguồn theo độ mạnh. Tầng 1 mạnh nhất, tầng 3 chỉ bổ trợ.

| Tầng | Đối tượng | Cách tiếp cận | Độ mạnh |
|---|---|---|---|
| 1 | Người đang làm firmware / embedded | Anh chị khóa trên, người quen đi làm, hỏi qua Facebook/LinkedIn | Mạnh — pain trực tiếp |
| 2 | Sinh viên từng làm đồ án vi điều khiển | Hỏi ngay trong lớp | Khá — **cùng bản chất pain, khác quy mô** |
| 3 | Nguồn thứ cấp công khai | Bài viết, forum, báo cáo ngành | Yếu — chỉ chứng minh pattern chung, không chứng minh pain của nhóm |

Ghi chú về tầng 2: sinh viên làm đồ án STM32 cũng gặp đúng bottleneck bước 3 — mở reference manual hàng nghìn trang mà không biết đọc từ đâu. Khác biệt là quy mô và việc không phải bàn giao tài liệu cho người khác. Khi tổng hợp phải nói rõ giới hạn này.

### Bộ câu hỏi phỏng vấn (Option A — 2-3 người)

Hỏi mở, không mớm lời, **không nhắc chữ "AI"** để tránh dẫn dắt câu trả lời:

1. Lần gần nhất bạn phải làm việc với datasheet hoặc reference manual của một con chip mới là khi nào?
2. Lúc đó bạn bắt đầu từ đâu? Kể lại từng bước bạn làm.
3. Bước nào mất nhiều thời gian nhất? Ước lượng khoảng bao lâu?
4. Bạn có viết lại gì cho người khác dùng không, hay chỉ ghi chú cho riêng mình?
5. Đã bao giờ bạn hoặc đồng đội làm sai vì tài liệu ghi thiếu điều kiện áp dụng chưa? Kể một lần cụ thể.
6. Nếu có một thứ giúp bạn nhanh hơn, bạn muốn nó giúp ở bước nào?
7. Hiện bạn đang làm gì để đỡ vất vả hơn? (tìm ví dụ trên GitHub, hỏi người khác, dùng code mẫu...)

Vì sao hai câu này quan trọng nhất:

- **Câu 4** phân biệt cụm A với cụm D. Nếu đa số chỉ ghi cho mình thì bài của nhóm rơi về cụm D và phải xem lại lựa chọn.
- **Câu 7** để lộ non-AI alternative thật đang được dùng, thứ nhóm phải so sánh ở Phase 6.

### Micro-survey (Option B — 5-10 người)

1. Bạn đã từng phải đọc datasheet / reference manual trên 500 trang chưa? (Rồi / Chưa)
2. Lần đó bạn mất bao lâu để tìm được đúng phần mình cần? (< 1h / 1-4h / 4-8h / > 8h)
3. Bước nào khó chịu nhất? (Tìm đúng section / Hiểu nội dung / Đối chiếu nhiều tài liệu / Viết lại cho người khác)
4. Bạn đã bao giờ làm sai vì tài liệu thiếu điều kiện áp dụng chưa? (Rồi / Chưa)
5. Mức độ đáng giải quyết: 1-5

### Điều kiện phản bác — chốt TRƯỚC khi đi hỏi

Nhóm cam kết trước những kết quả nào sẽ buộc phải sửa bài. Làm bước này trước để tránh chỉ nghe điều mình muốn nghe.

| Nếu kết quả là... | Thì nhóm phải... |
|---|---|
| 2/3 người nói bước đọc RM chỉ mất 2-3h, không phải ~12h | Sửa baseline xuống; metric "32h → dưới 16h" mất hiệu lực, phải viết lại |
| Đa số nói họ **không** viết lại tài liệu cho người khác | Bài chuyển từ cụm A sang cụm D → cân nhắc đổi sang #13 |
| Đa số nói code mẫu / application note của hãng đã đủ dùng | Non-AI alternative mạnh hơn dự tính → nghiêng về Rule, quyết định cuối có thể là Not Yet |
| Không tìm được ai từng gặp pain này | Evidence quá yếu → đổi candidate sang #13 hoặc #14 |

### Nguồn thứ cấp Tuyến tìm được (tầng 3)

| # | Nguồn | Link | Nói về gì | Trạng thái kiểm | Dùng được tới đâu |
|---|---|---|---|---|---|
| S1 | Entelligence AI — "How AI Documentation Tools Cut Onboarding Time by 80%" (đăng trên dev.to) | https://dev.to/entelligenceai/how-ai-documentation-tools-cut-onboarding-time-by-80-15k5 | Tool AI sinh tài liệu giúp giảm thời gian onboarding | ✅ Đã mở kiểm | Là **bài của công ty bán tool**, đăng trên nền tảng nội dung mở. Con số 80% là claim marketing, **không được dùng làm số liệu trong bài** |
| S2 | daily.dev — Developer Onboarding: First 90 Days Playbook | https://recruiter.daily.dev/resources/developer-onboarding-first-90-days-playbook-engineering-teams/ | Quy trình onboarding developer trong 90 ngày đầu |✅ Đã mở kiểm | Nội dung về onboarding nói chung, không riêng tài liệu kỹ thuật. Dùng để đối chiếu bước "dev mới cần bao lâu mới tự làm được" |
| S3 | TimeCraft Advisory — How to Make Onboarding Faster with Better Documentation | https://www.timecraftadvisory.com/blog/how-to-make-onboarding-faster-with-better-documentation | Tài liệu tốt giúp onboarding nhanh hơn; quản lý tài liệu trong tổ chức | ✅ Đã mở kiểm | Là **blog tư vấn có mục đích bán dịch vụ**, nội dung về onboarding HR và quản lý file nói chung, **không phải tài liệu kỹ thuật**. Có trích nguồn cấp 1 đáng lần theo (xem dưới) |

**Đánh giá chung về 3 nguồn này — phải ghi rõ trong bài:**

Cả 3 đều là nguồn thứ cấp, mang tính marketing, và nói về **onboarding nói chung** chứ không phải về việc chắt lọc datasheet thành tài liệu nội bộ. Chúng chứng minh được rằng *"tài liệu kém làm chậm người mới"* là pattern có thật trong ngành, nhưng **không chứng minh được pain cụ thể của nhóm** và **không thay thế được phỏng vấn người thật ở tầng 1-2**.

Cách dùng đúng: đưa vào phần bối cảnh để cho thấy vấn đề không phải cá biệt, không dùng làm baseline hay để biện minh cho quyết định.

**Số liệu không được dùng trực tiếp:** con số "giảm 80% thời gian onboarding" (S1) là claim của bên bán tool. Nhóm không dùng con số này ở bất kỳ đâu trong bài.

**Nguồn cấp 1 đáng lần theo:** S3 có dẫn lại một số nghiên cứu gốc — IDC (thời gian tìm kiếm thông tin mỗi ngày), McKinsey Global Institute (tỉ lệ thời gian tuần làm việc dành cho tìm kiếm thông tin), M-Files (tỉ lệ nhân viên phải làm lại tài liệu đã có). Nếu muốn dùng số, phải truy về báo cáo gốc của IDC/McKinsey chứ **không trích lại qua blog tư vấn**. Đây là việc Khang làm ở mục 4.2 nếu còn thời gian.

### Bảng kết quả validation

| Nguồn | Số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
|---|---:|---|---|---|
| Interview người làm embedded (tầng 1) |  |  |  |  |
| Interview / poll sinh viên (tầng 2) |  |  |  |  |
| Nguồn thứ cấp (tầng 3) | 3 bài (S1, S2, S3) |  |  |  |

**Insight sau validation:**

```text
[Điền sau]
```

**Nhóm đã sửa gì sau validation:**

```text
[Điền sau]
```

## 4.2 — Research giải pháp đã có

**Người phụ trách:** Khang (Research lead).

Mục tiêu của bước này không phải liệt kê tool cho nhiều, mà trả lời một câu duy nhất: **trong 7 bước workflow của nhóm, bước nào đã có người giải rồi, và bước nào còn trống thật?**

### Bảng đối chiếu giải pháp với từng bước workflow

| # | Tool / pattern | Link | Giải bước nào trong 7 bước | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|---|
| R1 | **STM32CubeMX** (và công cụ cấu hình tương đương của NXP, TI) | https://www.st.com/en/development-tools/stm32cubemx.html | Bước 4 — sinh code khởi tạo, tự kiểm ràng buộc clock/pin | Do chính hãng làm nên chắc chắn đúng về mặt ràng buộc phần cứng | Không sinh tài liệu, không giải thích "vì sao chọn cấu hình này" | Bước cấu hình **đã có Rule giải rồi**. Nhóm không nên nhắm vào bước này |
| R2 | **Application Note của hãng** (tài liệu AN đi kèm mỗi dòng chip) | https://www.st.com/en/microcontrollers-microprocessors/stm32-32-bit-arm-cortex-mcus.html | Bước 5 một phần — hãng đã viết "khi nào dùng" cho các use case phổ biến | Miễn phí, có sẵn, đúng về kỹ thuật, do chính hãng viết | Chỉ phủ use case phổ biến; không biết bối cảnh sản phẩm cụ thể của công ty | **Phát hiện bất lợi cho giả định gốc của nhóm** — xem mục dưới |
| R3 | **Doxygen / Sphinx** (docs-as-code) | https://www.doxygen.nl/ · https://www.sphinx-doc.org/ | Bước 7, một phần bước 5 | Tài liệu luôn đồng bộ với code; giải được vấn đề lệch phiên bản | Chỉ sinh tài liệu **từ code đã có**, không chắt lọc được từ Reference Manual | Đây là **non-AI alternative mạnh**, phải so sánh nghiêm túc ở Phase 6 |
| R4 | **NotebookLM** hoặc RAG tự dựng trên PDF nội bộ | https://notebooklm.google.com/ | Bước 3 — trích xuất và định vị nội dung, kèm trích dẫn nguồn | Đúng bước bottleneck của nhóm; có trích dẫn để người verify | Không hiểu bối cảnh sản phẩm; **vướng NDA nếu là dịch vụ cloud** (xem 4.3) | Pattern đúng là "AI trích + người verify". Nhưng phải giải bài toán NDA trước |
| R5 | **Template + checklist peripheral trên Confluence** (giải pháp nội bộ, không cần tool mới) | — | Bước 2, 5, 7 | Làm được ngay, không tốn chi phí, không rủi ro bảo mật | Không giảm được bước 3 — vẫn phải có người đọc RM | Phải làm **trước hoặc song song** với bất kỳ phương án AI nào |

### Research đã làm thay đổi cách nhóm hiểu bài toán

Đây là phần quan trọng nhất của mục 4.2, không phải bảng ở trên.

**Giả định gốc trong Problem Card #1:** *"Tài liệu hãng không bao giờ có phần khi nào dùng / vì sao, vì hãng viết cho mọi khách hàng."*

**Research cho thấy giả định này quá mạnh.** Application Note (R2) chính là nỗ lực của hãng để trả lời đúng câu hỏi đó, và nó miễn phí, có sẵn, do chính hãng viết. Nghĩa là phần "vì sao" **không trống hoàn toàn** như nhóm nghĩ ban đầu.

**Nhóm thu hẹp lại giả định:** phần Application Note không phủ được là **bối cảnh sản phẩm cụ thể của công ty** — ràng buộc phần cứng riêng, yêu cầu về công suất/chi phí, quyết định kiến trúc đã có từ dự án trước. Đó mới là khoảng trống thật, và nó hẹp hơn nhiều so với "toàn bộ phần vì sao".

Việc tự phát hiện lỗ hổng trong giả định của chính mình là kết quả có giá trị nhất mà research mang lại cho nhóm ở phase này.

### Bản đồ khoảng trống sau research

| Bước | Đã có ai giải chưa? | Kết luận |
|---|---|---|
| 1 — Nhận tài liệu | Script đơn giản | Không phải bài toán |
| 2 — Lọc phạm vi | Template + checklist (R5) | Rule là đủ |
| **3 — Đọc / định vị trong RM** | **Chưa ai giải tốt** | **Khoảng trống thật** |
| 4 — Tra chéo errata/AN/SDK | CubeMX (R1) giải một phần | Phần còn lại hẹp |
| **5 — Viết "khi nào dùng / vì sao"** | AN (R2) phủ use case phổ biến | **Khoảng trống thu hẹp: chỉ còn phần bối cảnh sản phẩm cụ thể** |
| 6 — Review | Người làm | Không nên tự động hóa |
| 7 — Publish | Docs-as-code (R3) | Rule là đủ |

**Research takeaway:**

```text
Không nên xây agent tự chạy toàn bộ quy trình. Research cho thấy phần lớn
các bước đã có lời giải sẵn: bước cấu hình có công cụ hãng, bước publish và
đồng bộ phiên bản có docs-as-code, bước lọc phạm vi và format có template.

Khoảng trống thật chỉ còn hai chỗ:
1. Bước 3 — định vị nội dung liên quan trong Reference Manual theo checklist
   riêng của dự án. Đây là bottleneck thời gian và chưa có tool nào giải tốt.
2. Phần diễn giải theo bối cảnh sản phẩm cụ thể của công ty — hẹp hơn nhiều
   so với "toàn bộ phần vì sao" mà nhóm giả định ban đầu, vì Application Note
   của hãng đã phủ các use case phổ biến.

Hướng hợp lý là Workflow với phạm vi hẹp hơn dự tính ban đầu, và phải làm
template + checklist (R5) trước hoặc song song vì đó là phần chắc chắn có
hiệu quả mà không có rủi ro.
```

## 4.3 — Ràng buộc cần làm rõ trước khi bàn giải pháp

Mục này không có trong worksheet gốc. Nhóm thêm vào vì phát hiện có những ràng buộc nếu để đến Phase 6 mới xét thì phải làm lại toàn bộ quyết định.

| # | Ràng buộc | Vì sao quan trọng | Cách làm rõ | Tình trạng | Ảnh hưởng tới quyết định |
|---|---|---|---|---|---|
| C1 | **Tài liệu hãng kèm NDA** — được xử lý bằng công cụ AI nào? | Datasheet và reference manual thường có điều khoản hạn chế phân phối. Đưa lên dịch vụ AI cloud có thể là vi phạm hợp đồng với hãng, không chỉ là rủi ro kỹ thuật | Đọc điều khoản trên trang tải tài liệu của hãng; hỏi người làm thật xem công ty họ có chính sách gì về công cụ AI | Chưa làm rõ | Nếu cấm dịch vụ cloud thì chỉ còn phương án self-hosted, chi phí và công sức tăng mạnh → nghiêng hẳn về **Not Yet** |
| C2 | **Nhóm không có domain expert thật** | Chỉ Đạt nắm domain embedded. Nếu 4 người còn lại không hiểu đủ để phản biện thì bảng score 3.4 và mọi quyết định sau đó mất giá trị | Đạt giải thích lại workflow 7 bước; 4 người còn lại phải đặt được ít nhất 1 câu hỏi phản biện mỗi người | Chưa làm rõ | Nếu không đạt, nhóm phải hạ điểm "Nhóm hiểu domain" và cân nhắc đổi sang #13 hoặc #14 |
| C3 | **Baseline ~32 giờ chưa đo** | Toàn bộ metric của Problem Statement dựa trên con số này | Kết quả mục 4.1 | Chưa đo | Nếu lệch xa thì phải viết lại Success Metric ở PS v0 và v1 |
| C4 | **Ai là người vận hành và chịu trách nhiệm** nếu tài liệu do AI hỗ trợ tạo ra bị sai | Trong embedded, tài liệu sai dẫn tới cấu hình sai phần cứng. Cần rõ ai ký duyệt | Xác định trong Boundary của PS v1 | Chưa làm rõ | Không có người chịu trách nhiệm rõ ràng thì không được Go |

**Nguyên tắc nhóm thống nhất:** C1 là ràng buộc chặn. Nếu C1 không giải quyết được thì mọi thảo luận về Rule / Workflow / Agent ở Phase 6 đều là giả định, và quyết định cuối phải là **Not Yet** kèm việc "làm rõ chính sách bảo mật tài liệu hãng" là việc đầu tiên phải làm.

---

# Phase 5 — Workflow + Problem Statement (45')

## 5.1 — Current workflow bản nhóm

Bản dưới đây kế thừa từ Problem Card #1 cá nhân. Nhóm cần bổ sung actor / input / output / handoff cho từng bước và **sửa lại số liệu sau khi validate ở Phase 4**.

```text
CURRENT STATE — 7 bước, ~32 giờ công (số liệu chờ validate)

[1 Nhận bộ tài liệu hãng: 1h]
→ [2 Lọc peripheral/tính năng dự án dùng: 4h]
→ [3 Đọc + định vị nội dung trong RM ~3.300 trang: 12h]   <-- bottleneck thời gian
→ [4 Tra chéo errata + AN + SDK release note: 4h]
→ [5 Viết docs: mô tả + "khi nào dùng" + "vì sao": 8h]     <-- bottleneck chất lượng
→ [6 Review với senior: 2h]
→ [7 Publish Confluence + thông báo team: 1h]

Toàn bộ 7/7 bước là thủ công.
```

| Bước | Actor | Input | Output | Thời gian/tần suất | Handoff / ghi chú |
|---|---|---|---|---|---|
| 1 | Tech Lead | Bộ tài liệu từ hãng | Kho tài liệu dự án | 1h | |
| 2 | Tech Lead | Spec sản phẩm + tài liệu hãng | Danh sách peripheral cần dùng | 4h | |
| 3 | Tech Lead | Reference Manual ~3.300 trang | Các section liên quan | 12h | **Bottleneck thời gian** |
| 4 | Tech Lead | Errata + AN + SDK release note | Xác nhận cấu hình hợp lệ | 4h | |
| 5 | Tech Lead | Nội dung đã trích | Docs nội bộ có "khi nào dùng / vì sao" | 8h | **Bottleneck chất lượng** |
| 6 | Senior dev | Bản nháp docs | Docs đã review | 2h | Handoff Lead → Senior |
| 7 | Tech Lead | Docs đã review | Docs publish trên Confluence | 1h | Handoff Lead → cả team |

**Bottleneck chính:**

```text
[Nhóm chốt lại sau khi thảo luận. Lưu ý phân biệt 2 loại bottleneck ở trên —
đây là điểm quyết định AI nên can thiệp ở bước nào.]
```

## 5.2 — Future workflow bản nhóm

```text
[Nhóm vẽ lại. Draft kế thừa từ Card #1:]

FUTURE STATE — 7 bước, ~14 giờ công

[1 Nạp RM/datasheet/errata/SDK vào kho tài liệu dự án: 0.5h]  -- Rule/script
→ [2 AI trích + định vị theo checklist peripheral: 1h]         -- AI, bắt buộc kèm số trang
→ [3 Tech Lead verify trích dẫn trên PDF gốc: 3h]              <-- human boundary
→ [4 AI draft docs theo template nội bộ: 0.5h]                 -- AI
→ [5 Tech Lead viết "khi nào dùng / vì sao / đánh đổi": 6h]    <-- human boundary, GIỮ NGUYÊN
→ [6 Review với senior: 2h]
→ [7 Publish: 1h]

Boundary:
- AI không viết phần khuyến nghị áp dụng và đánh đổi kỹ thuật.
- Mọi claim kỹ thuật phải có số trang + tên register trong tài liệu gốc.
- AI không tự publish.

Fallback:
AI trích sai trang hoặc bịa tên register → bỏ toàn bộ output lượt đó, đọc RM
trực tiếp như quy trình cũ. Không sửa vá output sai.
```

**Before/after impact:**

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| Tổng thời gian | ~32h công/dự án | Dưới 16h | Metric chính |
| Số bước | 7 | 7 | Không giảm số bước, giảm effort trong bước |
| Số bước thủ công | 7/7 | 5/7 | Người vẫn verify, viết "vì sao", review, publish |
| Bottleneck chính | Đọc/định vị trong RM | Verify trích dẫn + viết "vì sao" | Bottleneck mới là điểm kiểm soát chất lượng |
| Risk mới | Không có | AI trích sai / bịa register → lỗi nhân bản ra toàn team | Bắt buộc verify trích dẫn |

## 5.3 — Problem Statement v0

| Field | Nội dung |
|---|---|
| **Actor** |  |
| **Workflow** |  |
| **Bottleneck** |  |
| **Impact** |  |
| **Success Metric** |  |
| **Boundary** |  |

---

# Phase 6 — Rule / Workflow / Agent + Decision (25')

## 6.0 — Vị trí trên ma trận

Bài toán của nhóm nằm ở ô nào?

```text

```

Vì sao?

```text

```

## 6.1 — So sánh Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI / process fix** | Template docs + checklist peripheral + thư viện tài liệu tái sử dụng | Đủ nếu phần lớn thời gian nằm ở format và cấu trúc | Không giảm được bước đọc/định vị trong RM |  |
| **Rule** | Script tự nạp tài liệu, index theo peripheral, cảnh báo lệch phiên bản SDK | Đủ cho bước gom và theo dõi phiên bản | Không hiểu được câu hỏi theo ngữ nghĩa |  |
| **Workflow** | Rule nạp tài liệu → AI trích xuất kèm trích dẫn → người verify → AI draft → người viết phần "vì sao" | Hợp nếu các bước tuyến tính và AI chỉ hỗ trợ vài bước ngôn ngữ | AI trích sai/bịa register; phụ thuộc chất lượng verify |  |
| **Agent** | Agent tự đọc tài liệu, tự quyết định đọc thêm gì, tự cập nhật docs khi hãng release bản mới | Chỉ cần nếu có nhiều nhánh quyết định và nhiều tool | Rủi ro cao, quyền truy cập rộng, khó truy vết lỗi |  |

**Mức chọn:**

```text
[Rule / Workflow / Agent]
```

**Vì sao chọn:**

```text

```

**Vì sao không chọn mức đơn giản hơn:**

```text

```

## 6.2 — Problem Statement v1

| Field | Nội dung |
|---|---|
| **Actor** |  |
| **Workflow** |  |
| **Bottleneck** |  |
| **Impact** |  |
| **Success Metric** |  |
| **Boundary** |  |
| **AI intervention point** |  |
| **Mức chọn** | Rule / Workflow / Agent |
| **Rủi ro & người thật kiểm tra** |  |

## 6.3 — Final decision

| Câu hỏi | Yes / Not Yet / No | Ghi chú |
|---|---|---|
| Actor và workflow đã rõ chưa? |  |  |
| Baseline và success metric đã đo được chưa? |  |  |
| Có data/input đủ dùng chưa? |  | Gắn với ràng buộc NDA ở mục 4.3 |
| Nếu AI sai, hậu quả có chấp nhận được không? |  | Sai register → cấu hình sai phần cứng |
| Có người review/owner vận hành không? |  |  |
| Có cách non-AI đơn giản hơn không? |  |  |

**Decision:**

```text
[Go / Not Yet / No-Go]
```

**Lý do:**

```text

```

**Nếu Go, pilot nhỏ nhất là:**

```text

```

**Nếu Not Yet, cần validate gì trước:**

```text

```

**Nếu No-Go, nên làm gì thay AI:**

```text

```

---

*Day 02 Lab — 02 Group Problem Statement*
