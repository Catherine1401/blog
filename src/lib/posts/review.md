---
title: "REVIEW"
date: "2025-05-26"
updated: "2025-05-26"
categories:
  - "process & thread"
coverImage: "/images/review.jpg"
coverWidth: 16
coverHeight: 9
excerpt: review
---
## Hệ thống phân tán, tập trung, phi tập trung khác nhau như thế nào, nêu ví dụ về mỗi loại,làm thế nào để xác định sự khác biệt chính?
---
#### Hệ thống tập trung (Centralized System)

Hệ thống tập trung là mô hình trong đó toàn bộ quyền điều khiển và xử lý dữ liệu đều nằm tại một nút trung tâm duy nhất. Các thiết bị khác trong hệ thống chỉ hoạt động như các máy khách (clients), phụ thuộc vào máy chủ (server).

Ví dụ điển hình là hệ thống máy chủ - máy khách như Facebook hoặc Google. Mọi dữ liệu và quyền kiểm soát đều thuộc về công ty quản lý.

Để xác định, nếu hệ thống chỉ có một điểm điều khiển chính và khi điểm đó gặp sự cố, toàn bộ hệ thống ngừng hoạt động, thì đó là hệ thống tập trung.

#### Hệ thống phân tán (Distributed System)

Hệ thống phân tán bao gồm nhiều nút cùng làm việc, phối hợp xử lý và chia sẻ dữ liệu. Dù có thể có một nút đóng vai trò điều phối, nhưng các nút còn lại có quyền và khả năng tương tự nhau.

Ví dụ: Hệ thống của Google Search hoặc Netflix sử dụng nhiều máy chủ trải dài trên toàn cầu để xử lý truy vấn hoặc phân phối nội dung. Một hệ cơ sở dữ liệu phân tán như MongoDB Cluster cũng thuộc loại này.

Cách nhận biết là hệ thống này hoạt động như một thể thống nhất nhưng phân phối trên nhiều thiết bị. Các thành phần phải được đồng bộ, phối hợp liên tục.

#### Hệ thống phi tập trung (Decentralized System)

Hệ thống phi tập trung không có nút trung tâm nào điều khiển toàn bộ hệ thống. Mỗi nút hoạt động độc lập, có thể ra quyết định và đóng góp vào hoạt động chung mà không cần sự điều khiển tập trung.

Ví dụ điển hình là mạng blockchain như Bitcoin hay Ethereum. Mỗi người dùng có thể trở thành một nút trong mạng, và toàn bộ hoạt động được bảo đảm thông qua các thuật toán đồng thuận như Proof of Work.

Nếu một hệ thống không có trung tâm rõ ràng, các nút không cần tin tưởng lẫn nhau nhưng vẫn phối hợp được nhờ thuật toán đồng thuận, đó là một hệ thống phi tập trung.

## Các đặc tính của hệ phân tán là gì? giải thích cho từng đặc điểm thật kỹ (tìm trong slides)
---
#### Tính trong suốt (Transparency)

Là khả năng che giấu sự phức tạp bên trong của hệ thống phân tán đối với người dùng và lập trình viên. Người dùng không cần biết tài nguyên nằm ở đâu, có bao nhiêu bản sao, hoặc có lỗi xảy ra trong hệ thống.

Ví dụ: Người dùng mở một tập tin mạng mà không cần biết nó nằm ở máy chủ nào.

Các dạng tính trong suốt:

- Trong suốt truy cập (Access transparency): Ẩn đi cách thức truy cập tài nguyên.
- Trong suốt vị trí (Location transparency): Ẩn đi nơi lưu trữ tài nguyên.
- Trong suốt đồng thời (Concurrency transparency): Cho phép nhiều người dùng truy cập tài nguyên cùng lúc mà không gây xung đột.
- Trong suốt sao chép (Replication transparency): Ẩn đi việc tài nguyên có nhiều bản sao.
- Trong suốt lỗi (Failure transparency): Hệ thống vẫn hoạt động khi có lỗi xảy ra.
- Trong suốt di chuyển (Migration transparency): Tài nguyên có thể di chuyển giữa các node mà người dùng không nhận thấy.

#### Tính mở (Openness)

Hệ thống được thiết kế theo chuẩn mở, cho phép các thành phần bên ngoài tương tác dễ dàng, có thể nâng cấp hoặc tích hợp mà không cần thay đổi toàn bộ hệ thống.

Ví dụ: Các dịch vụ bên ngoài có thể tích hợp qua REST API.

#### Tính mở rộng (Scalability)

Hệ thống vẫn duy trì hiệu năng khi quy mô tăng lên, như tăng số lượng người dùng, dữ liệu hoặc thiết bị. Có thể mở rộng theo chiều ngang (thêm máy) hoặc chiều dọc (nâng cấp máy).

Ví dụ: Khi có nhiều người truy cập, hệ thống tự động thêm server để xử lý.

#### Tính chịu lỗi (Fault Tolerance)

Hệ thống vẫn có thể hoạt động bình thường ngay cả khi một phần nào đó bị lỗi. Việc này yêu cầu cơ chế phát hiện, xử lý và phục hồi lỗi.

Ví dụ: Một node bị hỏng nhưng hệ thống vẫn cung cấp dịch vụ nhờ các node khác dự phòng.

#### Tính đồng thời (Concurrency)

Hệ thống cho phép nhiều người dùng hoặc tiến trình truy cập cùng lúc vào tài nguyên mà không làm sai lệch dữ liệu.

Ví dụ: Nhiều người có thể chỉnh sửa tài liệu chung mà không xảy ra xung đột.

#### Tính chia sẻ tài nguyên (Resource Sharing)

Các thành phần trong hệ thống có thể dùng chung tài nguyên như tập tin, cơ sở dữ liệu, dịch vụ mạng,...

Ví dụ: Nhiều máy tính truy cập chung một cơ sở dữ liệu từ xa.

#### Tính không đồng nhất (Heterogeneity)

Hệ thống bao gồm nhiều phần cứng, hệ điều hành và phần mềm khác nhau, nhưng vẫn phối hợp hoạt động trơn tru.

Ví dụ: Một hệ thống gồm thiết bị IoT, máy tính Windows và máy chủ Linux cùng làm việc với nhau.

#### Tính bảo mật (Security)

Hệ thống phải đảm bảo an toàn cho dữ liệu và tài nguyên: xác thực người dùng, phân quyền, mã hóa, và bảo vệ trước các mối đe dọa mạng.

Ví dụ: Chỉ người được cấp quyền mới truy cập được tài nguyên nội bộ.

## Mục đích của nút chủ trong một hệ phân tán là để làm gì? Điều gì sẽ xảy ra nếu nút chủ gặp sự cố?
---
Mục đích của nút chủ (master node) trong một hệ thống phân tán là đóng vai trò trung tâm trong việc quản lý, điều phối và giám sát hoạt động của toàn hệ thống. Nút chủ chịu trách nhiệm phân phối công việc cho các nút con, lưu giữ thông tin về cấu trúc và trạng thái của hệ thống, đồng bộ hóa dữ liệu, và thực hiện các quyết định quan trọng như quản lý tài nguyên, phát hiện lỗi hay tổ chức lại hệ thống khi cần thiết. Nhờ có nút chủ, hệ thống có thể vận hành trơn tru, phối hợp hiệu quả giữa nhiều thành phần phân tán.

Nếu nút chủ gặp sự cố, hậu quả phụ thuộc vào cách thiết kế hệ thống. Trong trường hợp hệ thống không có cơ chế dự phòng, toàn bộ hệ thống có thể bị gián đoạn, ngừng hoạt động hoặc không thể thực hiện được các tác vụ mới do mất đi trung tâm điều phối. Các nút con có thể trở nên rời rạc, không còn khả năng phối hợp hoặc xử lý công việc đúng cách. Trong những hệ thống được thiết kế tốt, có thể có cơ chế tự động phát hiện lỗi và thay thế nút chủ, ví dụ như bầu chọn nút chủ mới (leader election) bằng thuật toán Raft hoặc Paxos. Ngoài ra, một số hệ thống hiện đại còn hỗ trợ nhiều nút chủ hoặc cơ chế dự phòng nóng (hot standby) để đảm bảo tính sẵn sàng cao.

Ví dụ trong hệ thống Hadoop, NameNode đóng vai trò nút chủ. Nếu NameNode bị lỗi mà không có Standby NameNode, người dùng sẽ không thể truy cập dữ liệu dù dữ liệu vẫn còn được lưu trên các DataNode. Trong Kubernetes, control plane node là nút chủ điều phối các tài nguyên. Nếu node này gặp sự cố mà không có thiết lập High Availability, việc triển khai hoặc mở rộng dịch vụ sẽ bị ảnh hưởng.

## Trong một mạng không gian, tại sao các máy thường giao tiếp với nhau qua gossip protocol mà không gửi thông tin đến tất cả các máy khác hoặc gửi về một nút trung tâm
---
Trong một mạng không gian (distributed system), các máy thường giao tiếp với nhau thông qua gossip protocol (giao thức rỉ tai) thay vì gửi thông tin đến tất cả các máy khác (broadcast) hoặc gửi về một nút trung tâm (centralized node), là vì gossip protocol mang lại nhiều lợi ích quan trọng về hiệu năng, khả năng chịu lỗi và khả năng mở rộng.

Thứ nhất, gossip protocol giúp hệ thống mở rộng quy mô tốt hơn (high scalability). Trong các hệ thống lớn có hàng trăm hoặc hàng ngàn nút, việc mỗi nút gửi thông tin đến tất cả các nút còn lại (broadcast) sẽ gây ra bùng nổ lưu lượng mạng (network flood), làm giảm hiệu suất và tắc nghẽn. Gossip protocol chỉ yêu cầu mỗi nút chọn ngẫu nhiên một số ít nút để truyền tin, giúp giảm đáng kể lưu lượng truyền và tránh quá tải mạng.

Thứ hai, gossip protocol chịu lỗi tốt (fault tolerance). Do thông tin được lan truyền dần dần từ nút này sang nút khác, nên nếu một vài nút bị lỗi hoặc không khả dụng thì thông tin vẫn có thể tiếp tục lan rộng trong mạng. Điều này đảm bảo hệ thống vẫn hoạt động ổn định dù có một số phần tử bị hỏng hoặc mất kết nối.

Thứ ba, gossip protocol giúp phân tán gánh nặng (decentralization). Thay vì phụ thuộc vào một nút trung tâm để thu thập và phân phối thông tin (dễ trở thành điểm nghẽn hoặc điểm lỗi duy nhất), gossip protocol cho phép các nút cùng nhau chia sẻ trách nhiệm. Điều này nâng cao độ tin cậy của hệ thống và loại bỏ rủi ro từ một điểm trung tâm bị quá tải hoặc bị sập.

Thứ tư, gossip protocol truyền tin với độ trễ chấp nhận được (eventual consistency). Dù không phải tất cả các nút nhận thông tin cùng lúc, nhưng sau một khoảng thời gian ngắn, toàn bộ hệ thống sẽ dần đồng bộ thông tin. Đây là mô hình phù hợp với các hệ thống phân tán lớn, nơi yêu cầu cập nhật đồng nhất ngay lập tức là không khả thi hoặc quá tốn kém.

Ví dụ, trong các hệ thống như Cassandra hoặc DynamoDB, gossip protocol được sử dụng để các node chia sẻ thông tin trạng thái như node nào còn sống, node nào chết, hoặc thay đổi về dữ liệu, mà không cần gửi đến toàn mạng hay về một nút trung tâm.

## Các yếu tố cốt lõi của một hệ phân tán là gì
---
#### Tập hợp các nút độc lập (Independent Nodes)

Hệ phân tán bao gồm nhiều nút (nodes) là các máy tính riêng biệt, hoạt động độc lập, có bộ xử lý, bộ nhớ và kết nối mạng riêng. Mỗi nút có thể thực hiện nhiệm vụ riêng nhưng cũng phối hợp với các nút khác để hoàn thành công việc chung.

#### Mạng truyền thông (Communication Network)

Các nút kết nối với nhau thông qua một mạng truyền thông, thường là mạng máy tính (LAN, WAN hoặc Internet). Hệ thống cần giao thức mạng để các nút gửi và nhận thông điệp. Giao tiếp giữa các nút thường được thực hiện qua TCP/IP, HTTP, hoặc các giao thức như gRPC, MPI.

#### Cơ chế truyền thông giữa các tiến trình (Interprocess Communication – IPC)

Để các nút hợp tác được với nhau, chúng phải trao đổi thông tin thông qua các cơ chế truyền thông như message passing (truyền thông điệp), remote procedure call (gọi thủ tục từ xa – RPC) hoặc publish/subscribe. Đây là cách các tiến trình ở các máy khác nhau tương tác được.

#### Đồng bộ hóa và phối hợp (Synchronization and Coordination)

Do các nút hoạt động song song, cần có cơ chế đồng bộ hóa để tránh xung đột, như đồng bộ truy cập dữ liệu dùng chung, đồng bộ thời gian (clock synchronization), hoặc điều phối các hành động theo trình tự nhất định.

#### Chia sẻ tài nguyên (Resource Sharing)

Một hệ phân tán cho phép các nút chia sẻ tài nguyên như tập tin, cơ sở dữ liệu, máy in, dịch vụ, v.v. Các nút phải có cách truy cập tài nguyên từ xa mà vẫn đảm bảo hiệu năng và bảo mật.

#### Tính chịu lỗi (Fault Tolerance)

Vì một số nút có thể bị lỗi hoặc ngắt kết nối, hệ thống cần có khả năng phát hiện lỗi, khôi phục trạng thái, và đảm bảo tính liên tục trong hoạt động. Điều này giúp tăng độ tin cậy cho toàn hệ thống.

#### Tính nhất quán dữ liệu (Data Consistency)

Trong hệ phân tán, dữ liệu có thể được sao chép (replicated) giữa các nút. Cần có cơ chế đảm bảo dữ liệu giữa các nút là nhất quán, hoặc ít nhất là nhất quán dần (eventual consistency), để tránh xung đột và lỗi logic.

#### Bảo mật (Security)

Vì dữ liệu và tài nguyên được phân tán, hệ thống cần có cơ chế bảo mật như xác thực người dùng, mã hóa dữ liệu, phân quyền truy cập, để tránh rò rỉ thông tin hoặc truy cập trái phép.

#### Quản lý hệ thống (System Management)

Hệ thống cần có công cụ và giao diện để giám sát, cấu hình, cập nhật, và kiểm soát các thành phần phân tán, giúp người quản trị dễ dàng vận hành và khắc phục sự cố.

## Nêu những lí do sử dụng hệ phân tán
---
Đầu tiên, hệ phân tán giúp mở rộng quy mô (scalability) dễ dàng hơn so với hệ thống tập trung. Khi số lượng người dùng, dữ liệu hoặc thiết bị tăng lên, hệ phân tán có thể bổ sung thêm các nút mới mà không cần thay đổi toàn bộ kiến trúc.

Tiếp theo, hệ phân tán tăng khả năng chịu lỗi (fault tolerance) và độ tin cậy (reliability) của hệ thống. Nếu một hoặc vài nút bị lỗi hoặc ngắt kết nối, các nút còn lại vẫn có thể tiếp tục hoạt động, đảm bảo hệ thống không bị gián đoạn hoàn toàn.

Hệ phân tán cũng mang lại tính sẵn sàng cao (high availability), vì tài nguyên và dịch vụ được phân phối trên nhiều nút khác nhau. Người dùng có thể truy cập dịch vụ mọi lúc, ngay cả khi một số phần của hệ thống bị hỏng hoặc bảo trì.

Ngoài ra, hệ phân tán giúp chia sẻ tài nguyên (resource sharing) hiệu quả hơn, khi các máy tính và thiết bị trong mạng có thể dùng chung dữ liệu, máy in, cơ sở dữ liệu hoặc các dịch vụ mạng khác.

Một lý do quan trọng nữa là hệ phân tán cho phép gần người dùng hơn (proximity to users), giảm độ trễ và tăng tốc độ truy cập bằng cách đặt dữ liệu hoặc dịch vụ gần khu vực người dùng cuối.

Cuối cùng, sử dụng hệ phân tán giúp tăng tính linh hoạt (flexibility) trong phát triển và mở rộng hệ thống, khi các thành phần có thể được thêm, sửa đổi hoặc thay thế độc lập mà không ảnh hưởng đến toàn bộ hệ thống.

## Nêu định nghĩa hệ phân tán
---
Hệ phân tán là một tập hợp các máy tính độc lập được kết nối với nhau qua mạng và phối hợp hoạt động như một hệ thống duy nhất nhằm thực hiện các nhiệm vụ chung. Mỗi máy trong hệ phân tán có thể hoạt động riêng biệt, nhưng thông qua các cơ chế truyền thông và đồng bộ, toàn bộ các máy cùng phối hợp để chia sẻ tài nguyên, xử lý dữ liệu và cung cấp dịch vụ một cách liền mạch và hiệu quả.

Trong tiếng Anh, hệ phân tán được gọi là distributed system. Đây là một hệ thống trong đó các thành phần phần cứng và phần mềm nằm trên các máy tính khác nhau, nhưng hoạt động như một thể thống nhất để người dùng cảm nhận như đang sử dụng một hệ thống duy nhất.

## Chụp và để lên blog các hình của thuật toán Cristian, Berkeley, RBS, Lamport, Bully, Ring
---
![cristian](/static/images/cristian.png)

Thuật toán Cristian

![berkeley](/static/images/berkeley.png)

Thuật toán Berkeley

![lamport](/static/images/lamport.png)

Giải thuật Lamport

![bully](/static/images/bully.png)

Giải thuật Bully

![ring](/static/images/ring.png)

Giải thuật Ring

## Tiến trình nhẹ, tiến trình, luồng có những ưu điểm và nhược điểm gì, liệt kê. Khi một lời gọi hệ thống dừng thì đối với 3 loại như thế nào. Tiến trình nhẹ, tiến trình và luồng có mối quan hệ như thế nào với nhau và với chính nó?
---
#### Ưu điểm và nhược điểm của tiến trình, tiến trình nhẹ và luồng

Tiến trình (process) có ưu điểm là có không gian địa chỉ riêng biệt, giúp cách ly tốt giữa các tiến trình, tăng độ an toàn và ổn định cho hệ thống. Một tiến trình bị lỗi sẽ không ảnh hưởng đến tiến trình khác. Tuy nhiên, nhược điểm là tốn nhiều tài nguyên hơn, thời gian khởi tạo chậm, và việc giao tiếp giữa các tiến trình (IPC) phức tạp hơn so với luồng.

Tiến trình nhẹ (lightweight process – LWP) là khái niệm trung gian giữa tiến trình và luồng, thường xuất hiện trong một số hệ điều hành như Solaris. Ưu điểm của LWP là có khả năng quản lý như một thực thể độc lập nhưng vẫn chia sẻ tài nguyên chung giống luồng, giúp đạt được sự cân bằng giữa hiệu suất và an toàn. Nhược điểm là quản lý phức tạp và không phổ biến trong nhiều hệ điều hành hiện nay.

Luồng (thread) là đơn vị thực thi nhẹ hơn tiến trình. Ưu điểm của luồng là thời gian tạo và huỷ nhanh, chi phí tài nguyên thấp, cho phép chia sẻ dữ liệu và tài nguyên với các luồng khác trong cùng một tiến trình. Giao tiếp giữa các luồng diễn ra nhanh chóng và hiệu quả. Tuy nhiên, nhược điểm là mức độ cách ly thấp, một luồng gặp lỗi có thể ảnh hưởng đến toàn bộ tiến trình, đồng thời việc đồng bộ dữ liệu giữa các luồng cũng dễ dẫn đến lỗi nếu không cẩn thận.

#### Khi một lời gọi hệ thống bị chặn, điều gì xảy ra với tiến trình, tiến trình nhẹ và luồng

Khi một lời gọi hệ thống (system call) bị chặn, nếu tiến trình thực hiện lời gọi đó là một tiến trình độc lập thì toàn bộ tiến trình sẽ bị dừng, dẫn đến không xử lý được các tác vụ khác trong cùng tiến trình. Đối với tiến trình nhẹ, tùy theo cơ chế của hệ điều hành, chỉ tiến trình nhẹ đó bị chặn, các tiến trình nhẹ khác trong cùng tiến trình chính có thể tiếp tục thực thi bình thường. Còn đối với luồng, kết quả phụ thuộc vào mô hình quản lý luồng. Trong mô hình một-một (1:1) – tức mỗi luồng người dùng ánh xạ với một luồng nhân hệ điều hành – chỉ luồng bị chặn dừng lại, các luồng còn lại vẫn chạy. Tuy nhiên, trong mô hình nhiều-một (N:1), nếu một luồng bị chặn thì toàn bộ tiến trình có thể bị dừng vì hệ điều hành không thể chuyển lịch cho luồng khác.

#### Mối quan hệ giữa tiến trình, tiến trình nhẹ và luồng

Tiến trình là đơn vị thực thi độc lập lớn nhất, có không gian địa chỉ riêng và không chia sẻ tài nguyên với tiến trình khác. Bên trong một tiến trình, có thể tồn tại nhiều tiến trình nhẹ và nhiều luồng. Tiến trình nhẹ là cầu nối giữa luồng người dùng và hệ điều hành, đại diện cho một hoặc nhiều luồng trong tiến trình. Luồng là đơn vị nhỏ nhất trong hệ thống thực thi, chia sẻ cùng không gian bộ nhớ, tập tin và tài nguyên với các luồng khác trong cùng tiến trình. Như vậy, một tiến trình có thể chứa nhiều tiến trình nhẹ, mỗi tiến trình nhẹ ánh xạ tới một hoặc nhiều luồng. Các luồng trong cùng một tiến trình có thể thực thi song song và chia sẻ dữ liệu trực tiếp với nhau.

## Mô hình client server là gì, vai trò của máy chủ và máy khách là gì.
---
Mô hình client-server (khách – chủ) là một mô hình kiến trúc trong hệ thống phân tán, nơi mà một hoặc nhiều máy khách (client) gửi yêu cầu dịch vụ đến một máy chủ (server), và máy chủ phản hồi lại các yêu cầu đó. Mô hình này giúp phân tách rõ vai trò giữa bên cung cấp dịch vụ và bên sử dụng dịch vụ, đồng thời tăng hiệu quả tổ chức, mở rộng và bảo trì hệ thống.

Trong mô hình này, máy chủ (server) đóng vai trò là đơn vị trung tâm chịu trách nhiệm lưu trữ, xử lý dữ liệu và cung cấp dịch vụ cho các máy khách. Server thường chạy liên tục, có tài nguyên mạnh hơn và được thiết kế để phục vụ nhiều yêu cầu cùng lúc từ nhiều client khác nhau. Ví dụ, một web server sẽ tiếp nhận các yêu cầu HTTP từ trình duyệt của người dùng và trả về nội dung trang web tương ứng.

Ngược lại, máy khách (client) là bên gửi yêu cầu đến máy chủ để sử dụng dịch vụ hoặc truy xuất thông tin. Client thường là các thiết bị đầu cuối như máy tính cá nhân, điện thoại hoặc trình duyệt web. Máy khách không cần biết chi tiết cách server xử lý yêu cầu, mà chỉ cần gửi lệnh, nhận kết quả và hiển thị cho người dùng.

Tóm lại, mô hình client-server hoạt động dựa trên nguyên tắc: client yêu cầu – server đáp ứng, cho phép hệ thống phân chia chức năng rõ ràng, dễ mở rộng, dễ quản lý và phổ biến rộng rãi trong các ứng dụng như web, email, cơ sở dữ liệu, trò chơi trực tuyến, v.v.