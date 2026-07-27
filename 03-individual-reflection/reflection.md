# 03 — Individual Reflection

**Học viên:** Nguyễn Hoàng Đạt — 2A202601460
**Vai trò trong nhóm:** Domain owner — người pitch candidate được nhóm chọn, chủ trì vẽ workflow before/after
---

## 1. Tôi đã tham gia vào phần nào?

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng |
|---|---|---|
| **Scan cá nhân** | Scan 8 problems từ bối cảnh Teach Lead đội embedded, trải đều 4 lăng kính. Ban đầu tôi nghĩ ra 6 vấn đề nhưng đều nằm trong một cụm là tài liệu | Tự cắt danh sách từ 11 xuống 8 vì các dòng thừa chỉ nói lại cùng một nguyên nhân gốc. 3 candidate của tôi vào bảng hội tụ nhóm |
| **Pitch Problem Card** | Pitch Card #1 — chắt lọc tài liệu hãng thành tài liệu nội bộ. Điểm tôi nhấn mạnh nhất là việc tách hai loại bottleneck: bước đọc/định vị (12h, tốn thời gian) và bước viết "vì sao" (8h, tốn chất xám) | Nhóm chọn candidate này, 31/35 điểm ở bảng score |
| **Challenge bài của bạn khác** | Với những Problem của các bạn khác: với Tuyến giá vàng phải tùy theo đại lý, input không đảm bảo, quá nhiều đại lý nhỏ,với Khang baseline và metric chwua khớp để thuyết phục, với Giang metric từ 40% về 0% gàn như là bất khả thi khó đo được, với Duy đấy là bài toán QR/Ngân Hàng chưa phải AI.| Các bạn cũng đã lắng nghe nhưng việc các bạn sửa heettt hay chưa thì chưa được xác nhận |
| **Gom trùng / cluster** | Tham gia gom 15 candidate thành 5 cụm A-E. Phát hiện candidate của tôi nằm ở giao giữa cụm A và cụm D | Giúp nhóm thấy 6/15 candidate do 4 trong 5 người độc lập nêu ra đều là biến thể của "đọc nguồn dài rồi chắt lọc lại" |
| **Chọn candidate problem** | Bài của tôi được chọn, nên tôi phải trả lời câu khó nhất: vì sao chọn #1 mà không chọn #13 (BQL tra quy chế) — hai bài cùng cụm A | Nhóm chốt lý do là #13 không validate được trong phạm vi lab, không phải vì bài yếu |
| **Validation / research** | Tuyến và Khang chủ trì. Tôi hỗ trợ phần bối cảnh kỹ thuật và soạn bộ câu hỏi phỏng vấn không nhắc chữ "AI" để tránh mớm lời | Phỏng vấn 1 người làm embedded xác nhận đúng hai giả định quan trọng nhất |
| **Workflow nhóm** | Chủ trì vẽ workflow 7 bước, bổ sung actor / input / output / thời gian / handoff cho từng bước | Chỉ ra được cả quy trình chỉ có 2 handoff, một người ôm bước 1-5 và 7 |
| **Problem Statement** | Giang chủ trì viết. Tôi cung cấp nội dung domain và rà lại phần Bottleneck, Boundary |Tôi có chỉnh sửa lại 1 chút, tuy nhiên phàn lớn Giang đã làm được |
| **Rule / Workflow / Agent** | Tính ra con số: nếu bỏ hoàn toàn phần AI thì quy trình vẫn về ~20h nhờ template, checklist và docs-as-code — tức 62% mức cải thiện đến từ phần không cần AI | Đây là căn cứ để nhóm chọn làm Rule trước, và để trả lời "vì sao không chọn mức đơn giản hơn" |
| **Decision** | Datasheet và reference manual của các hãng chip lớn thường đã public ra ngoài để người dùng tra cứu khi sử dụng| Nhóm chuyển từ Not Yet sang Go có điều kiện sau khi xác nhận C1 được phép |

---

## 2. Tôi đã dùng AI như thế nào?

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai / hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| **Scan** | Mở rộng 6 vấn đề tôi tự nghĩ ra thành danh sách đủ 4 lăng kính | Chỉ ra tôi thiếu hẳn lăng kính "pain từ người khác" và thiếu dấu hiệu thật bằng số | AI đưa ra 11 dòng, trong đó nhiều dòng chỉ là biến thể của nhau (ví dụ "onboard dev mới" thực chất là hệ quả của hai dòng khác) | Tôi cắt xuống 8 dòng. Danh sách dài mà trùng nguyên nhân gốc thì yếu hơn danh sách ngắn mà tách bạch |
| **Problem Card** | Soạn nháp 3 card theo template | Cấu trúc đầy đủ field, không sót mục nào | AI viết bối cảnh Tech Lead embedded như thể đó là công việc thật của tôi | Tôi đổi tiêu đề thành **"Bối cảnh giả lập"** và ghi rõ trong ghi chú đầu bài. Thà mất điểm "trải nghiệm thật" còn hơn để bài trông như khai man |
| **Workflow** | Chuyển mô tả thành sơ đồ before/after và bảng có actor/handoff | Nhanh, và giúp tôi thấy chỗ thiếu handoff | Bản draft cá nhân đặt AI ở 2 bước (trích xuất và draft tài liệu), rộng hơn mức cần thiết | Sau research, tôi thu lại còn **1 bước duy nhất** — AI chỉ ở bước 3 |
| **Research** | Tìm tool/pattern đã có và đối chiếu với 7 bước workflow | Tìm ra Application Note của hãng — thứ tôi đã bỏ qua khi viết card | AI ban đầu chấp nhận luôn giả định của tôi rằng "tài liệu hãng không bao giờ có phần khi nào dùng". Giả định đó **sai** | Tôi thu hẹp giả định: Application Note đã phủ use case phổ biến, khoảng trống thật chỉ còn **bối cảnh sản phẩm cụ thể của công ty** |
| **Problem Statement** | Soạn nháp PS v0/v1 và bảng Success Metric | Tách được metric chính và metric guardrail, thứ tôi không nghĩ tới | AI viết ghi chú số liệu chỉ phủ những số có dấu `~`, trong khi nhiều số ước lượng khác không có dấu đó | Tôi sửa lại câu ghi chú cho phủ **toàn bộ** số liệu. Ghi chú hẹp hơn thực tế còn nguy hiểm hơn không ghi chú |
| **Rule / Workflow / Agent** | Soạn bảng so sánh 4 mức | Bảng đầy đủ, có cột "giải được bao nhiêu" để so định lượng | AI diễn đạt kết quả validation là "bằng chứng **không đủ mạnh để sửa**" | Tôi đổi thành "bằng chứng **đủ mạnh để không sửa**". Hai câu này nghĩa khác hẳn nhau: một câu là thiếu thông tin, câu kia là đã được xác nhận |
| **Decision** | Soạn lập luận Go / Not Yet / No-Go | Lập luận chặt, có tiêu chí chuyển trạng thái rõ ràng | AI kết luận **Not Yet** dựa trên giả định rằng ràng buộc NDA chưa làm rõ — nhưng đó chỉ là giả định của AI, không phải sự thật | Nhóm đi tra thật và xác nhận **được phép dùng công cụ AI**. Kết luận đổi thành Go có điều kiện. Đây là lần AI sai rõ nhất trong cả buổi |

**Nhận xét chung về việc dùng AI:**
     Tôi không bảo AI bịa ra tình huống về Embbededd, tôi có kinh nghiệm làm việc ở mảng này nên tôi đã kiểm chứng được rồi nên đã đưa ra 1 bối cảnh hợp lý và nêu 1 số Problem mà tôi thấy được và nêu cho AI để AI nhận xét chỉnh sửa và chi tiết hóa góc nhìn của tôi xong tôi trình bày để mọi người có thể hiểu được 

---

## 3. Trả lời câu hỏi mở

**Tôi học được gì khi nghe top 3 problems của các bạn khác?**
    Mỗi người đều có 1 góc nhìn gác nhau với mỗi vấn đề gặp phải, cách tiếp cận Ai cũng khác nhau. tuy nhiên cách tiếp cận các bạn còn chưa bao quát được hết vấn đề

**Nhóm có lúc nào bị solution-first không?**
    Có. Cứ nghĩ sẽ phải thêm bot nhắc nhở hoặc AI Agent rồi mới quay lại xem ứng dụng vào vấn đề nào, tìm hiểu workflow

**Tôi có thay đổi ý kiến sau khi bị challenge không?**

    có 1 chút chỉnh sửa, khi được các bạn hỏi hay bị phản biển lúc thuyết trình thì tôi biết thêm được góc nhìn cửa mọi người các mọi người suy nghĩ về Problem này

**Tôi đóng góp gì thật sự vào artifact cuối?**

Fix lại workflow 7 bước before/after; việc tách hai loại bottleneck; con số 62% cải thiện đến từ phần không cần AI; làm cho bối cảnh domain để cả nhóm hiểu bài toán.
---

## 4. Bài học của tôi

- Problem tốt không phải problem nghe "AI" nhất, mà là problem có workflow vẽ được và metric đo được.
- Tách bottleneck ra thành nhiều loại quan trọng hơn là tìm ra một bottleneck. Nếu chỉ nói "viết tài liệu tốn thời gian" thì không biết đặt AI ở đâu; tách ra thành bottleneck thời gian và bottleneck chất lượng thì thấy ngay AI nên vào bước nào và người phải giữ bước nào.
- Rule không kém AI. Trong bài của nhóm tôi, Rule lấy được 62% mức cải thiện mà không có rủi ro nào, và nó còn là điều kiện cần để phần AI chạy được.
- Research không phải để tìm tool mà để biết mình đã sai ở đâu. Application Note làm giả định gốc của tôi yếu đi, và đó là kết quả có giá trị nhất của Phase 4.
- Một ràng buộc chưa kiểm chứng có thể lật ngược cả quyết định. Nhóm suýt chốt Not Yet chỉ vì cho rằng NDA sẽ chặn.

---

## 5. Tự kiểm cuối bài

- [ ] [12đ cá nhân] Cá nhân có 5+ problems và top 3 Problem Cards → **8 problems, 3 card đầy đủ**
- [ ] [12đ cá nhân] Tôi đã pitch rõ và challenge nhóm đúng trọng tâm → Tốt
- [ ] Nhóm có nhật ký hội tụ từ candidates về 1 bài → **15 candidate, 5 cụm, shortlist 4, score 7 tiêu chí**
- [ ] [15đ nhóm] Nhóm có workflow trước/sau → **7 bước, có actor/input/output/handoff**
- [ ] [20đ nhóm] Nhóm có Problem Statement v0/v1 với metric và boundary rõ → **có, metric ghi rõ chỗ nào chưa đo**
- [ ] [15đ nhóm] Nhóm có so sánh No AI / Rule / Workflow / Agent → **4 mức, có cột "giải được bao nhiêu"**
- [ ] [10đ nhóm] Nhóm có Go / Not Yet / No-Go và lý do rõ → **Go với pilot đo lường, có tiêu chí dừng**
- [ ] [10đ cá nhân] Reflection có vai trò trong nhóm, cách dùng AI, điều học được, nếu làm lại tôi sẽ viết chi tiết hơn đa dạng và chi tiết bài toán hơn
- [ ] [6đ cá nhân] Tôi tự giải thích được mạch problem → workflow → metric → boundary → độ phù hợp với AI

---

*Day 02 Lab — 03 Individual Reflection*
