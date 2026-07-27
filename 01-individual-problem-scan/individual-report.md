# 01 — Individual Problem Scan

**Học viên:** Nguyễn Hoàng Đạt — 2A202601460

> **Ghi chú về bối cảnh và số liệu:** Bối cảnh Tech Lead embedded trong bài là bối cảnh tôi tự dựng, không phải vị trí tôi đang giữ. Toàn bộ số liệu là ước lượng dựa trên hiểu biết của tôi về quy trình phát triển embedded, chưa đo bằng log thời gian hay số liệu từ bug tracker. Dấu `~` đánh dấu những con số tôi kém chắc chắn nhất. Mọi con số cần được đo lại bằng số liệu thật trước khi dùng làm baseline cho Success Metric.

## Bối cảnh giả lập của tôi

Tôi là **Tech Lead của một đội embedded** trong một công ty lớn. Team gồm ~5 developer embedded (mix senior/junior), phát triển firmware cho sản phẩm của công ty.

Mỗi khi nhận một dự án mới, đầu vào của tôi là bộ tài liệu từ hãng chip/module: **datasheet, reference manual, errata sheet, application note, SDK/driver và API document**. Đầu ra là **tài liệu kỹ thuật nội bộ** để team dùng làm cơ sở phát triển. Tài liệu này phải thỏa mãn hai ràng buộc cùng lúc:

1. **Đúng** — không được lệch so với tài liệu hãng, vì sai một bit cấu hình register là hỏng phần cứng hoặc sinh bug rất khó truy.
2. **Dùng được** — thành viên trong team đọc là áp dụng được ngay vào sản phẩm, không phải đọc lại 3.000 trang tài liệu gốc.

Phần lớn thời gian và rủi ro của tôi nằm ở khoảng giữa hai ràng buộc này.

---

## Bảng scan — 8 problems

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Lặp lại | Mỗi dự án đổi dòng chip phải đọc lại Reference Manual ~3.300 trang từ đầu rồi viết lại tài liệu nội bộ cho ~9 peripheral (clock, GPIO, UART, SPI, I2C, ADC, DMA, timer, low-power) theo cùng một format | Tech Lead (tôi) | ~20 giờ công/dự án cho riêng hai bước này (đọc RM ~12h + viết docs ~8h), nằm trong tổng ~32h của cả workflow ở Card #1; lặp lại mỗi lần đổi chip (~2-3 dự án/năm) |
| 2 | Lặp lại | Dev hỏi lại cùng một loại câu hỏi qua Teams: pin mapping, thứ tự init clock, điều kiện dùng DMA. Câu hỏi lặp theo từng người mới thay vì lặp theo thời gian, nên viết FAQ chỉ giải quyết được một phần | Dev trong team, Tech Lead | ~5-8 câu/tuần trong 4 tuần đầu dự án, mỗi câu ngắt mạch tôi ~15-20 phút |
| 3 | Tốn thời gian | Chốt một cấu hình phải tra chéo 4 nguồn: RM (mô tả register) + errata (lỗi silicon) + application note (khuyến nghị) + SDK release note (API đã đổi chưa) | Tech Lead | ~30-60 phút cho một cấu hình khó; không tra đủ thì rủi ro dính lỗi errata |
| 4 | Tốn thời gian | Review PR mất nhiều vòng vì không có chuẩn chung về driver API, error handling, cấu trúc module — mỗi dev viết một kiểu | Tech Lead, dev | ~2-3 vòng review/PR driver, phần lớn comment là về convention chứ không phải logic; dev mới cần ~1-2 tuần mới bắt được convention |
| 5 | AI có thể tốt hơn | Tìm thông tin trong kho tài liệu chỉ bằng keyword: Confluence search và Ctrl+F trong PDF không hiểu câu hỏi theo ngữ nghĩa ("làm sao giữ SPI hoạt động khi vào stop mode") | Dev trong team | Dev tìm ~10-15 phút không ra thì bỏ cuộc và hỏi Tech Lead |
| 6 | AI có thể tốt hơn | Biến mô tả register-level trong RM thành hướng dẫn theo ngữ cảnh sản phẩm: "khi nào dùng", "vì sao chọn cấu hình này", "đánh đổi là gì" — đây là phần tài liệu hãng không bao giờ có vì hãng viết cho mọi khách hàng | Tech Lead, dev | Đây là phần tốn nhiều chất xám nhất và cũng là phần dev cần nhất |
| 7 | Pain từ người khác | Dev implement sai vì tài liệu nội bộ chỉ chép lại datasheet mà không nêu điều kiện áp dụng và ràng buộc — lỗi chỉ lộ ra ở integration test | Dev, QA, tiến độ dự án | ~2-3 bug/dự án thuộc loại "làm đúng theo docs nhưng vẫn sai"; debug loại này mất ~0.5-1 ngày/bug |
| 8 | Pain từ người khác | Hãng release SDK/driver/datasheet bản mới nhưng tài liệu nội bộ không theo kịp; dev làm theo bản cũ mà không biết là đã cũ | Dev, Tech Lead | Hãng update ~1-2 lần/quý, tài liệu nội bộ trễ vài tuần đến vài tháng; đã có case dev dùng API đã deprecated |

**Phân bố lăng kính:** Lặp lại 2 · Tốn thời gian 2 · AI có thể tốt hơn 2 · Pain từ người khác 2.

Quan sát sau khi scan: các problem trên không rời rạc mà nối thành một chuỗi. #1, #3, #6 là chi phí tôi trả để tạo ra tài liệu. #2, #5, #7, #8 là chi phí team trả khi tài liệu chưa đủ tốt hoặc đã cũ. #4 là vấn đề riêng về chuẩn kỹ thuật, không phải vấn đề tài liệu — nên tôi tách nó ra thành một candidate độc lập để so sánh.

---

## Top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | **Chắt lọc tài liệu hãng thành docs nội bộ dùng được** (gộp #1, #3, #6, #7) | Workflow lặp lại rõ ràng, có baseline thời gian ước lượng được, bottleneck nằm ở một bước cụ thể, có non-AI alternative thật (template + checklist), và có ranh giới người/máy tự nhiên | Đo "docs dễ hiểu" bằng gì cho khách quan? Baseline ~32h có đúng cho cả dự án tái sử dụng chip cũ không? Tài liệu hãng thường có NDA — có được đưa lên dịch vụ AI bên ngoài không? |
| 2 | **Không có chuẩn chung driver/middleware/kiến trúc module** (#4) | Pain có bằng chứng rất rõ qua comment trong PR; ảnh hưởng tới toàn team chứ không chỉ mình tôi | Đây nhiều khả năng là bài toán **process/Rule**, không phải bài toán AI. Chuẩn phải do người viết trước thì công cụ mới có gì để kiểm |
| 3 | **Dev không tự tìm được câu trả lời trong kho tài liệu** (#2, #5, #8) | Impact rộng nhất, giảm được cả thời gian dev lẫn thời gian tôi bị ngắt quãng | Rủi ro trả lời sai về register cao hơn hẳn Card 1 vì output đi thẳng vào tay dev, không qua tôi review. Cần data access vào cả PDF hãng lẫn Confluence nội bộ |

---

## Problem Card #1 — Chắt lọc tài liệu hãng thành docs nội bộ

```text
┌──────────────────────────────────────────────────────────────┐
│ PROBLEM CARD #1                                              │
│                                                              │
│ Problem : Mỗi dự án mới, Tech Lead mất ~32 giờ công    │
│ biến ~3.500 trang tài liệu hãng thành docs nội bộ, trong    │
│ đó riêng bước đọc và định vị đúng nội dung đã chiếm ~12h.   │
│                                                              │
│ Ai chịu ảnh hưởng? Tech Lead (người viết) + 5 dev (người    │
│ dùng docs để phát triển sản phẩm)                            │
│                                                              │
│ Workflow hiện tại:                                           │
│ 1. Nhận tài liệu hãng → 2. Lọc phạm vi → 3. Đọc RM →        │
│ 4. Tra chéo errata/AN/SDK → 5. Viết docs → 6. Review →      │
│ 7. Publish                                                   │
│                                                              │
│ Bước nghẽn nhất: Bước 3 — đọc/định vị trong RM (~12h)       │
│                                                              │
│ Đo thành công bằng gì? ~32h → dưới 16h công/dự án,          │
│ và số bug "làm đúng docs nhưng vẫn sai" không tăng          │
│                                                              │
│ Quick gut: ☑ Workflow                                        │
└──────────────────────────────────────────────────────────────┘
```

**Problem :**
Mỗi khi nhận dự án mới, Tech Lead mất khoảng 32 giờ công để biến ~3.500 trang tài liệu hãng thành tài liệu nội bộ dùng được cho team, trong đó bước đọc và định vị đúng nội dung trong Reference Manual chiếm nhiều thời gian nhất và không đòi hỏi phán đoán kỹ thuật cao.

**Actor:**
Tech Lead đội embedded, người duy nhất chịu trách nhiệm viết tài liệu kỹ thuật nội bộ cho dự án. Người dùng đầu ra là ~5 developer embedded trong team.

**Thời điểm / bối cảnh:**
Giai đoạn khởi động dự án, sau khi chốt dòng chip/module và trước khi team bắt đầu code. Đây là đường găng: team không thể bắt đầu phát triển driver trước khi có tài liệu nội bộ.

**Current workflow:**

```text
1. Nhận bộ tài liệu từ hãng (datasheet, RM, errata, AN, SDK, API doc)
2. Lọc ra danh sách peripheral và tính năng dự án thật sự dùng
3. Đọc từng section trong Reference Manual để định vị nội dung liên quan
4. Tra chéo errata + application note + SDK release note để xác nhận cấu hình hợp lệ
5. Viết tài liệu nội bộ: mô tả, "khi nào dùng", "vì sao chọn", cấu hình mẫu
6. Review với 1-2 senior trong team
7. Publish lên Confluence và thông báo cho team
```

**Bottleneck:**
**Bước 3 — đọc và định vị nội dung trong RM, ~12 giờ công.** Đây là bước tốn thời gian nhất nhưng phần lớn công việc là tìm kiếm và trích xuất, không phải phán đoán kỹ thuật.

Cần phân biệt rõ với **bước 5 (~8h)**: bước 5 tốn ít thời gian hơn nhưng là **bottleneck về chất lượng** — phần "khi nào dùng / vì sao / đánh đổi là gì" đòi hỏi kinh nghiệm dự án và hiểu bối cảnh sản phẩm. Tài liệu hãng không bao giờ có phần này vì hãng viết cho mọi khách hàng. Đây là chỗ tôi tạo ra giá trị thật và **không nên giao cho AI**.

Việc tách hai loại bottleneck này là điểm quan trọng nhất của card: nó chỉ ra AI nên can thiệp ở đâu và người phải giữ lại phần nào.

**Impact:**
~32 giờ công/dự án cho một mình Tech Lead, lặp lại mỗi dự án đổi chip (~2-3 dự án/năm). Trong lúc đó team bị chặn hoặc phải làm việc với tài liệu chưa hoàn chỉnh. Hệ quả kéo theo: ~2-3 bug/dự án thuộc loại "dev làm đúng theo docs nhưng vẫn sai" vì tài liệu thiếu điều kiện áp dụng, mỗi bug tốn ~0.5-1 ngày để truy.

**Success metric:**

| Chỉ số | Hiện trạng | Mục tiêu | Cách đo |
|---|---|---|---|
| Thời gian tạo docs nội bộ | ~32 giờ công/dự án | Dưới 16 giờ công/dự án | Tech Lead log thời gian theo từng bước trong 1 dự án |
| Bug loại "đúng docs nhưng vẫn sai" | ~2-3 bug/dự án | Không tăng (≤3) | Đếm ticket được gán nhãn `doc-gap` trong bug tracker |
| Câu hỏi lặp lại của dev về nội dung có trong docs | ~5-8 câu/tuần (4 tuần đầu) | Giảm còn ~3 câu/tuần | Đếm trong channel Teams của dự án |

Metric thời gian là metric chính. Hai metric còn lại là **guardrail**: nếu tài liệu làm nhanh hơn nhưng team hiểu sai nhiều hơn thì coi như thất bại.

**Non-AI alternative:**
Chuẩn hóa template tài liệu nội bộ + checklist peripheral cố định + thư viện tài liệu tái sử dụng giữa các dự án cùng họ chip. Cách này giảm được thời gian ở bước 2, 5 và 7, nhưng **không giảm được bước 3** — vẫn phải có người đọc RM để tìm đúng nội dung. Đây là phương án phải làm trước hoặc song song, không phải phương án loại trừ.

**AI hypothesis:**
AI trích xuất và định vị nội dung liên quan trong RM theo checklist peripheral, **kèm trích dẫn số trang và tên register cụ thể**, rồi tổng hợp thành bản nháp theo template nội bộ. Tech Lead verify trích dẫn và tự viết phần "khi nào dùng / vì sao" — phần này giữ nguyên cho người.

**Quick gut:**
Workflow.

### Draft current workflow

```text
CURRENT STATE — 7 bước, ~32 giờ công

[1 Nhận bộ tài liệu hãng: 1h]
→ [2 Lọc peripheral/tính năng dự án dùng: 4h]
→ [3 Đọc + định vị nội dung trong RM ~3.300 trang: 12h]   <-- bottleneck thời gian
→ [4 Tra chéo errata + AN + SDK release note: 4h]
→ [5 Viết docs: mô tả + "khi nào dùng" + "vì sao": 8h]     <-- bottleneck chất lượng
→ [6 Review với senior: 2h]
→ [7 Publish Confluence + thông báo team: 1h]

Toàn bộ 7/7 bước là thủ công.
```

### Draft future workflow

```text
FUTURE STATE — 7 bước, ~14 giờ công

[1 Nạp RM/datasheet/errata/SDK vào kho tài liệu dự án: 0.5h]  -- Rule/script
→ [2 AI trích + định vị theo checklist peripheral: 1h]         -- AI, bắt buộc kèm số trang
→ [3 Tech Lead verify trích dẫn trên PDF gốc: 3h]              <-- human boundary
→ [4 AI draft docs theo template nội bộ: 0.5h]                 -- AI
→ [5 Tech Lead viết "khi nào dùng / vì sao / đánh đổi": 6h]    <-- human boundary, GIỮ NGUYÊN
→ [6 Review với senior: 2h]
→ [7 Publish: 1h]

Boundary:
- AI không được viết phần khuyến nghị áp dụng và đánh đổi kỹ thuật.
- Mọi claim kỹ thuật phải có số trang + tên register trong tài liệu gốc.
  Không có trích dẫn kiểm được thì không đưa vào docs.
- AI không tự publish. Tech Lead là người duy nhất publish.

Fallback:
AI trích sai trang hoặc bịa tên register → bỏ toàn bộ output của lượt đó,
Tech Lead đọc RM trực tiếp như quy trình cũ. Không sửa vá output sai.

Bottleneck mới:
Bước 3 (verify trích dẫn) và bước 5 (viết phần "vì sao"). Đây là bottleneck
chấp nhận được vì đó chính là điểm kiểm soát tính đúng đắn của tài liệu.

Ràng buộc cần kiểm tra trước: tài liệu hãng thường kèm NDA.
Phải xác nhận được phép xử lý bằng công cụ AI nào (on-premise / self-hosted /
enterprise agreement) trước khi bàn tiếp về giải pháp.
```

---

## Problem Card #2 — Không có chuẩn chung driver / middleware / kiến trúc module

**Problem :**
Team không có chuẩn chung về driver API, error handling và cấu trúc module, nên mỗi dev tự thiết kế một kiểu và mỗi PR driver phải qua ~2-3 vòng review chỉ để thống nhất convention.

**Actor:**
5 dev embedded trong team (người viết code) và Tech Lead (người review).

**Thời điểm / bối cảnh:**
Suốt giai đoạn phát triển, mỗi khi có PR cho một driver hoặc module mới.

**Current workflow:**

```text
1. Dev nhận task viết driver cho một peripheral
2. Dev tự thiết kế API và cấu trúc module theo cách riêng
3. Dev implement + test cục bộ
4. Tạo PR
5. Tech Lead review, phần lớn comment về naming, init pattern, error handling
6. Dev sửa, đẩy lại
7. Lặp bước 5-6 khoảng 2-3 vòng rồi mới merge
```

**Bottleneck:**
Vòng lặp bước 5-6. Nguyên nhân gốc không nằm ở review mà nằm ở việc **chuẩn chưa tồn tại dưới dạng văn bản** — nó chỉ nằm trong đầu Tech Lead, và chỉ hiện ra khi review.

**Impact:**
Mỗi PR driver kéo dài thêm vài ngày do vòng lặp review. Code khó tái sử dụng giữa các dự án. Dev mới mất ~1-2 tuần mới bắt được convention. Tech Lead tốn thời gian lặp lại cùng một loại comment.

**Success metric:**

| Chỉ số | Hiện trạng | Mục tiêu | Cách đo |
|---|---|---|---|
| Số vòng review/PR driver | ~2-3 vòng | ~1 vòng | Đếm số lần request-change trên PR |
| Tỉ lệ comment về convention | Phần lớn comment | Dưới 20% | Gán nhãn comment `convention` vs `logic` |

**Non-AI alternative:**
Viết coding standard + driver API template + skeleton repo + checklist PR. Đây là giải pháp **đầy đủ** cho bài toán này, không cần AI. Có thể bổ sung linter/static analysis để tự động hóa việc kiểm — nhưng đó là Rule, không phải AI.

**AI hypothesis:**
Rất hạn chế. AI chỉ có thể hỗ trợ ở mức nhắc chuẩn khi review, và chỉ sau khi chuẩn đã được viết ra. AI **không thể** quyết định chuẩn nên là gì — đó là quyết định kiến trúc thuộc về Tech Lead.

**Quick gut:**
No AI / process fix (bổ sung Rule ở bước kiểm tra tự động).

### Draft current workflow

```text
CURRENT STATE

[1 Nhận task] → [2 Dev tự thiết kế API] → [3 Implement]
→ [4 PR] → [5 Review: comment convention]  <-- bottleneck
→ [6 Sửa] → lặp 5-6 (2-3 vòng) → [7 Merge]
```

### Draft future workflow

```text
FUTURE STATE — không dùng AI

[0 Viết coding standard + driver template + skeleton repo]  -- làm 1 lần
→ [1 Nhận task]
→ [2 Dev generate module từ skeleton]                       -- Rule
→ [3 Implement]
→ [4 PR + linter tự kiểm convention]                        -- Rule
→ [5 Review: chỉ tập trung vào logic]
→ [6 Merge]

Vòng lặp review về convention biến mất vì chuẩn được kiểm tự động
trước khi tới mắt người.
```

Card này tôi giữ lại làm **đối chứng cho nhóm**: một bài toán có pain rõ, evidence rõ, nhưng câu trả lời đúng lại là "không cần AI". Nó giúp nhóm tránh mặc định coi mọi problem đều là problem AI.

---

## Problem Card #3 — Dev không tự tìm được câu trả lời trong kho tài liệu

**Problem :**
Khi cần một thông tin kỹ thuật cụ thể, dev tìm ~10-15 phút trong Confluence và PDF hãng bằng keyword mà không ra, cuối cùng vẫn phải hỏi Tech Lead qua Teams và chờ.

**Actor:**
Dev embedded trong team (người bị chặn) và Tech Lead (người bị ngắt mạch công việc).

**Thời điểm / bối cảnh:**
Trong lúc code, đặc biệt là 4 tuần đầu dự án khi tài liệu nội bộ chưa phủ hết.

**Current workflow:**

```text
1. Dev gặp câu hỏi kỹ thuật khi đang code
2. Search Confluence bằng keyword
3. Không ra → Ctrl+F trong PDF datasheet/RM
4. Tìm được đoạn liên quan nhưng không chắc có áp dụng đúng cho dự án không
5. Hỏi Tech Lead trên Teams
6. Chờ Tech Lead rảnh
7. Tech Lead trả lời (kèm phải tự mở lại tài liệu để xác nhận)
```

**Bottleneck:**
Bước 5-7: dev bị chặn trong lúc chờ, và Tech Lead bị ngắt mạch ~15-20 phút mỗi lần. Câu hỏi lặp theo từng người mới chứ không lặp theo thời gian, nên viết thêm FAQ chỉ giải quyết được một phần.

**Impact:**
~5-8 câu/tuần trong 4 tuần đầu dự án. Tính cả thời gian dev tìm không ra, thời gian chờ, và thời gian Tech Lead bị ngắt quãng thì chi phí thật cao hơn nhiều so với thời lượng câu trả lời.

**Success metric:**

| Chỉ số | Hiện trạng | Mục tiêu | Cách đo |
|---|---|---|---|
| Câu hỏi phải escalate lên Tech Lead | ~5-8 câu/tuần | ~3 câu/tuần | Đếm trong channel Teams dự án |
| Thời gian dev tự tìm ra câu trả lời | ~10-15 phút rồi bỏ cuộc | Dưới 3 phút | Dev tự log trong 2 tuần pilot |
| Tỉ lệ câu trả lời có trích dẫn kiểm được | — | 100% | Kiểm thủ công trên mẫu 20 câu |

**Non-AI alternative:**
FAQ nội bộ + cải thiện cấu trúc và tag của Confluence + index tài liệu theo peripheral. Giảm được phần nào nhưng không giải quyết được việc **dev không biết dùng đúng từ khóa để tìm** — đây chính là chỗ tìm kiếm theo keyword thất bại.

**AI hypothesis:**
Hệ thống hỏi đáp trên kho tài liệu (nội bộ + tài liệu hãng) trả lời kèm trích dẫn nguồn và số trang, để dev tự kiểm chứng trước khi áp dụng.

**Quick gut:**
Workflow. Chưa cần Agent — không có bước nào cần AI tự lập kế hoạch hay tự gọi công cụ theo nhánh.

### Draft current workflow

```text
CURRENT STATE — ~20-35 phút cho một câu hỏi

[1 Dev gặp câu hỏi]
→ [2 Search Confluence: 3']
→ [3 Ctrl+F trong PDF: 7-12']
→ [4 Không chắc áp dụng đúng không]
→ [5 Hỏi Teams: 2']
→ [6 Chờ Tech Lead: 10-20']        <-- bottleneck (dev bị chặn)
→ [7 Tech Lead trả lời: 15-20']    <-- bottleneck (lead bị ngắt mạch)
```

### Draft future workflow

```text
FUTURE STATE — ~5 phút cho phần lớn câu hỏi

[1 Dev gặp câu hỏi]
→ [2 Hỏi hệ thống Q&A trên kho tài liệu: 1']    -- AI
→ [3 Nhận câu trả lời + trích dẫn trang: tức thì]
→ [4 Dev mở đúng trang được trích để tự kiểm: 3']  <-- human boundary
→ [5 Nếu vẫn không chắc → escalate lên Tech Lead]  -- đường thoát giữ nguyên

Boundary:
- Câu trả lời KHÔNG có trích dẫn trang thì không được tin.
- Không đưa code cấu hình trực tiếp cho peripheral ảnh hưởng phần cứng
  (clock tree, power, flash). Chỉ trỏ tới đúng section để dev tự đọc.
- Đường escalate lên Tech Lead luôn còn, không bị thay thế.

Fallback:
Hệ thống trả lời sai/không có nguồn → dev escalate như quy trình cũ.

Rủi ro lớn nhất:
Output đi thẳng vào tay dev, KHÔNG qua Tech Lead review như Card 1.
Trả lời sai về register có thể dẫn tới cấu hình sai phần cứng.
Đây là lý do Card 3 rủi ro cao hơn Card 1 dù nghe hấp dẫn hơn.
```

---

## Card tôi muốn pitch nhất

**Card #1 — Chắt lọc tài liệu hãng thành docs nội bộ.**

**Vì sao:**

- Workflow rõ nhất trong ba card, tôi là người trực tiếp làm nên vẽ được từng bước với thời gian tương đối sát.
- Có baseline thời gian đo được và có metric guardrail về chất lượng, không chỉ metric "nhanh hơn".
- Bottleneck tách được thành hai loại — bottleneck thời gian (đọc/định vị) và bottleneck chất lượng (viết phần "vì sao") — nên chỉ ra được chính xác AI nên đứng ở đâu và người phải giữ lại phần nào.
- Có non-AI alternative thật (template + checklist) và tôi giải thích được vì sao nó chưa đủ, thay vì gạt đi để lấy cớ dùng AI.
- Human boundary rất tự nhiên: Tech Lead vẫn là người verify và publish, nên rủi ro kiểm soát được — khác với Card 3 nơi output đi thẳng tới dev.
- So sánh được đủ bốn mức No AI / Rule / Workflow / Agent một cách có nghĩa.

**Câu hỏi tôi muốn nhóm challenge:**

1. **Ràng buộc bảo mật:** tài liệu hãng thường kèm NDA. Nếu công ty không cho đưa datasheet lên dịch vụ AI bên ngoài thì bài toán còn khả thi không, hay phải đổi hoàn toàn hướng giải?
2. **Baseline có đại diện không:** ~32 giờ là con số cho dự án đổi dòng chip mới. Dự án tái sử dụng chip cũ thì chi phí thấp hơn nhiều. Với ~2-3 dự án/năm, tổng impact có đủ lớn để đáng đầu tư không?
3. **Đo chất lượng thế nào:** "docs dễ hiểu, dev áp dụng được" đo bằng gì cho khách quan? Đếm bug `doc-gap` và đếm câu hỏi lặp lại đã đủ chưa, hay chỉ là proxy yếu?
4. **Rule đã đủ chưa:** nếu chỉ làm template + checklist + thư viện tài liệu tái sử dụng, tôi giảm được bao nhiêu phần trăm trong 32 giờ? Nếu con số đó đã đủ tốt thì có nên dừng ở Rule không?
5. **Rủi ro chuyển dịch:** nếu AI trích xuất sai mà tôi verify không kỹ, tài liệu nội bộ sai sẽ nhân bản lỗi ra toàn team. Verify 3 giờ có thật sự đủ, hay tôi đang lạc quan về bước này?

---

## Ghi chú dùng AI ở Phase 1-2

| Việc | Tôi tự làm | Dùng AI |
|---|---|---|
| Xác định bối cảnh, actor, 6 vấn đề gốc | Có, từ trải nghiệm thật | Không |
| Mở rộng scan lên 8 problems theo 4 lăng kính | Chốt lại từng dòng | Có, để gợi ý lăng kính còn thiếu |
| Ước lượng số liệu dấu hiệu thật | Có, từ trí nhớ dự án gần nhất | Không — số liệu không verify được thì không dùng |
| Tách bottleneck thời gian vs bottleneck chất lượng | Có | Không |
| Chọn top 3 và card muốn pitch | Có | Không |

Điểm tôi phải tự sửa lại: 6 vấn đề ban đầu tôi nêu đều nằm trong cùng một cụm (tài liệu), thiếu lăng kính "pain từ người khác" và thiếu hoàn toàn dấu hiệu thật bằng số. Sau khi scan lại, tôi tách được vấn đề chuẩn driver (#4) ra thành candidate độc lập — và nhận ra đó là bài toán **không cần AI**, giữ lại làm đối chứng cho nhóm.

Tôi cũng chủ động cắt danh sách scan từ 11 xuống 8 dòng: các dòng bị bỏ đều là biến thể của dòng khác (ví dụ "onboard dev mới" thực chất là hệ quả của #2 và #4). Giữ 8 problem cụ thể và không trùng lặp có giá trị hơn 11 problem trong đó vài dòng chỉ nói lại cùng một nguyên nhân gốc.

Việc cần làm trước Phase 4: xác nhận lại toàn bộ số liệu `~` bằng log thời gian thật và đếm ticket, thay vì để ước lượng theo trí nhớ.

---
