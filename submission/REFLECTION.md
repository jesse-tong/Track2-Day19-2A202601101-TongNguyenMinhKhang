# Reflection — Lab 19

**Tên:** Tống Nguyễn Minh Khang
**Cohort:** 3
**Path đã chạy:** docker

---

## Câu hỏi (≤ 200 chữ)

> Trên golden set 50 queries, mode nào thắng ở loại query nào (`exact` /
> `paraphrase` / `mixed`), và tại sao? Khi nào bạn **không** dùng hybrid
> (i.e. khi nào pure BM25 hoặc pure vector là lựa chọn đúng)?

_Answer here._
Trên golden set 50 queries, keyword search mode (trong code sử dụng BM25) thắng ở loại query exact, do chúng có thể tìm các từ khoá chính xác, từ riêng, ID, số hoặc thời gian (không mang nhiều semantic meaning), hoặc query cần constraint chính xác và cần match chính xác các thuật ngữ, đặc biệt là danh từ riêng khi semantic search có thể nhầm các từ này với từ đồng nghĩa. Semantic search mode (ví dụ embedding similarity search dùng Qdrant) thì sẽ thắng ở loại query paraphrase do các document có thể có nhiều cách diễn đạt và paraphrase khác nhau nên keyword search sẽ khó match do overlap thấp. Hybrid search sẽ thắng đối với query mixed do các dạng query này có cần constraint hoặc nhiều từ ít semantic meaning, nhưng có cả semantic intent.
---

## Điều ngạc nhiên nhất khi làm lab này

_(Optional, 1–2 câu)_
Điều ngạc nhiên nhất khi làm lab này là mình nghĩ rằng mô hình Embedding sẽ luôn tốt hơn thuật toán từ khóa BM25 ra đời từ thập niên 90, tuy nhiên trong thực tế là với các câu hỏi chứa thuật ngữ kỹ thuật chính xác (exact match) hoặc đặc thù, BM25 thường cho kết quả chính xác hơn Vector Search. Vector search dễ bị "bẫy" ngữ nghĩa khi các khái niệm gần nhau bị trộn lẫn.
---

## Bonus challenge

- [ ] Đã làm bonus (xem `bonus/`)
- [ ] Pair work với: _<tên đồng đội nếu có>_
