---
title: "Tự động tạo liên kết cho tiêu đề trong mdsvex"
date: "2023-10-26"
updated: "2023-10-26"
categories:
  - "sveltekit"
  - "markdown"
coverImage: "/images/first.jpg"
coverWidth: 16
coverHeight: 9
excerpt: Trong bài viết này, mình sẽ chia sẻ cách mdsvex tự động tạo liên kết cho các heading — cực kỳ tiện lợi khi viết blog hay tài liệu!
---

Trong quá trình xây dựng blog với **SvelteKit + mdsvex**, mình phát hiện một tính năng khá thú vị:  
> mdsvex tự động thêm liên kết vào các tiêu đề (heading) — rất tiện nếu bạn muốn người đọc dễ dàng chia sẻ hoặc dẫn link tới từng phần cụ thể.

Dưới đây là một vài ví dụ thực tế:

## Đây là tiêu đề cấp 2 (H2)

`Lorem ipsum dolor sit amet` — một đoạn văn bản mô phỏng.

### Đây là tiêu đề cấp 3 (H3)

Tiếp tục với nội dung mẫu.

#### Tiêu đề cấp 4 (H4) — không có gì bất ngờ

Chỉ để minh họa khả năng tự động gắn link.

##### Vâng, đây là H5

Và nó cũng có link luôn nhé.

###### Cuối cùng là H6 — sâu nhất trong hệ thống tiêu đề

Nếu bạn cần chia nhỏ nội dung chi tiết, H6 cũng hoạt động tốt.

---

👉 **Lưu ý nhỏ**:  
Tính năng auto-link này hoạt động "ngầm" và không cần cấu hình phức tạp nếu bạn dùng đúng cấu trúc với `mdsvex` và `rehype-slug` kèm `rehype-autolink-headings`.

Hy vọng chia sẻ nhỏ này giúp bạn tiết kiệm thời gian khi viết tài liệu bằng Markdown với mdsvex!

