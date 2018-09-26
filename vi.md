[Source](https://en.m.wikipedia.org/wiki/Design_by_contract "Permalink to Design by contract - Wikipedia")

# Thiết kế theo hợp đồng (Hợp đồng thiết kế) - Wikipedia

! [] [1]

Kế hoạch thiết kế theo hợp đồng

Thiết kế theo hợp đồng (DbC), còn được gọi là lập trình dạng hợp đồng, lập trình theo hợp đồng và lập trình được thiết kế theo hướng hợp đồng, là một cách tiếp cận việc thiết kế phần mềm. Nó quy định rằng các nhà thiết kế phần mềm nên xác định các đặc tả một cách chính xác, và được đối chiếu với các thành phần phần mềm, mở rộng định nghĩa thông thường của các kiểu dữ liệu trừu tượng với điều kiện tiên quyết, điều kiện phụ và bất biến. Những thông số kỹ thuật này được gọi là "hợp đồng", phù hợp với một khái niệm ẩn dụ cùng các điều kiện và nghĩa vụ của nghiệp vụ đối với hợp đồng đó.

Cách tiếp cận DbC giả sử tất cả các thành phần máy khách gọi một hoạt động trên một thành phần máy chủ sẽ đáp ứng các điều kiện tiên quyết được xác định theo yêu cầu cho hoạt động đó. Trường hợp giả định này được coi là quá rủi ro (như trong máy chủ đa kênh hoặc máy tính phân tán), phương pháp "thiết kế hướng phòng thủ" theo hướng ngược lại được thực hiện, nghĩa là kiểm tra thành phần máy chủ (trước hoặc trong khi xử lý yêu cầu của khách hàng) luôn hoạt động, và trả lời với một thông báo lỗi phù hợp nếu không.

## Nội dung

### Lịch sử

Thuật ngữ được đặt ra bởi Bertrand Meyer, có liên quan đến thiết kế của ông về ngôn ngữ lập trình Eiffel và được mô tả lần đầu trong các bài báo khác nhau bắt đầu từ năm 1986 [2] [3] và hai ấn bản liên tiếp (1988, 1997) Object-Oriented Software Construction của ông ấy. Eiffel Software đã đăng ký nhãn hiệu cho Thiết kế theo hợp đồng vào tháng 12 năm 2003 và được cấp vào tháng 12 năm 2004. [4] [5] Chủ sở hữu hiện tại của nhãn hiệu này là Eiffel Software. [6] [7]

Thiết kế theo hợp đồng có nguồn gốc của nó trong việc xác minh chính thức, đặc điểm kỹ thuật chính thức và logic của Hoare. Những đóng góp ban đầu bao gồm:

* Một ẩn dụ rõ ràng để hướng dẫn về quá trình thiết kế
* Các ứng dụng được dùng để kế thừa, đặc biệt là để định nghĩa lại và ràng buộc có tính cơ động cao
* Ứng dụng trong việc xử lý ngoại lệ
* Kết nối với tài liệu của phần mềm một cách tự động

### Miêu tả

Ý tưởng cốt lõi của DbC là một phép ẩn dụ về cách các yếu tố của một hệ thống phần mềm cộng tác với nhau trên cơ sở các nghĩa vụ và lợi ích lẫn nhau. Ẩn dụ xuất phát từ cuộc sống kinh doanh, nơi "khách hàng" và "nhà cung cấp" đồng ý về "hợp đồng" xác định, ví dụ:

* Nhà cung cấp (có nghĩa vụ) phải cung cấp một sản phẩm nhất định và có quyền mong đợi rằng khách hàng đã thanh toán chi phí (lợi ích) cho mình.
* Khách hàng (có nghĩa vụ) phải trả phí và được quyền nhận sản phẩm (lợi ích).
* Cả hai bên phải đáp ứng các nghĩa vụ nhất định, chẳng hạn như luật và quy định, áp dụng cho tất cả các contract.

Tương tự, nếu một thường trình từ một lớp trong lập trình hướng đối tượng cung cấp một chức năng nhất định, nó có thể:

* Mong đợi một điều kiện nhất định được đảm bảo khi nhập vào bởi bất kỳ mô-đun khách hàng nào gọi nó: điều kiện tiên quyết của thường lệ - nghĩa vụ cho khách hàng và lợi ích cho nhà cung cấp (bản thân thường trình), vì nó giải phóng nó khỏi phải xử lý các trường hợp bên ngoài của điều kiện tiên quyết.
* Đảm bảo một tài sản nhất định về xuất cảnh: postcondition của thói quen - một nghĩa vụ cho nhà cung cấp, và rõ ràng là một lợi ích (lợi ích chính của việc gọi các thói quen) cho khách hàng.
* Duy trì một tài sản nhất định, giả định về nhập cảnh và đảm bảo về lối ra: lớp bất biến.

Hợp đồng này tương đương về mặt ngữ nghĩa với việc hình thức hóa các nghĩa vụ thành ba nguyên tắc của Hoare. Điều này có thể được tóm tắt bằng "ba câu hỏi" mà nhà thiết kế phải nhiều lần trả lời trong hợp đồng:

* Hợp đồng kỳ vọng là gì?
* Bảo đảm hợp đồng là gì?
* Hợp đồng duy trì?

Nhiều ngôn ngữ lập trình có cơ sở để đưa ra các xác nhận như thế này. Tuy nhiên, DbC coi các hợp đồng này là rất quan trọng đối với tính chính xác của phần mềm mà chúng phải là một phần của quá trình thiết kế. Trong thực tế, DbC chủ trương viết các xác nhận đầu tiên. Các hợp đồng có thể được viết bằng các chú thích mã, được thi hành bởi một bộ kiểm thử, hoặc cả hai, ngay cả khi không có sự hỗ trợ ngôn ngữ đặc biệt cho các hợp đồng.

Khái niệm về hợp đồng kéo dài xuống mức phương thức / thủ tục; hợp đồng cho mỗi phương pháp thường sẽ chứa các thông tin sau: [cần dẫn nguồn]

* Các giá trị hoặc loại đầu vào được chấp nhận và không được chấp nhận và ý nghĩa của chúng
* Trả về giá trị hoặc loại và ý nghĩa của chúng
* Lỗi và các giá trị điều kiện ngoại lệ hoặc loại có thể xảy ra và ý nghĩa của chúng
* Tác dụng phụ
* Điều kiện tiên quyết
* Postconditions
* Bất biến
* (hiếm khi hơn) Đảm bảo hiệu suất, ví dụ: cho thời gian hoặc không gian được sử dụng

Các lớp con trong một hệ thống phân cấp thừa kế được phép làm suy yếu các điều kiện tiên quyết (nhưng không tăng cường chúng) và tăng cường các điều kiện và bất biến (nhưng không làm suy yếu chúng). Những quy tắc này gần đúng về phân loại hành vi.

Tất cả các mối quan hệ lớp là giữa các lớp khách hàng và các lớp nhà cung cấp. Một lớp khách hàng có nghĩa vụ thực hiện các cuộc gọi đến các tính năng của nhà cung cấp, nơi trạng thái kết quả của nhà cung cấp không bị vi phạm bởi cuộc gọi của khách hàng. Sau đó, nhà cung cấp có nghĩa vụ cung cấp trạng thái trả lại và dữ liệu không vi phạm các yêu cầu của tiểu bang của khách hàng. Ví dụ, bộ đệm dữ liệu của nhà cung cấp có thể yêu cầu dữ liệu đó có trong bộ đệm khi một tính năng xóa được gọi. Sau đó, nhà cung cấp đảm bảo cho khách hàng rằng khi một tính năng xóa kết thúc công việc của nó, mục dữ liệu sẽ, thực sự, sẽ bị xóa khỏi bộ đệm. Các hợp đồng thiết kế khác là các khái niệm về "bất biến lớp". Lớp bảo đảm bất biến (đối với lớp địa phương) rằng trạng thái của lớp sẽ được duy trì trong các dung sai được chỉ định ở cuối mỗi thực thi tính năng.

Khi sử dụng hợp đồng, nhà cung cấp không nên cố gắng xác minh rằng các điều kiện hợp đồng được thỏa mãn; ý tưởng chung là mã nên "thất bại", với xác minh hợp đồng là mạng lưới an toàn. Thuộc tính "không cứng" của DbC đơn giản hoá việc gỡ rối hành vi hợp đồng, vì hành vi dự định của mỗi thường trình được xác định rõ ràng. Điều này phân biệt nó rõ ràng từ một thực hành liên quan được gọi là lập trình phòng thủ, nơi mà các nhà cung cấp chịu trách nhiệm cho việc tìm ra phải làm gì khi một điều kiện tiên quyết bị phá vỡ. Thường xuyên hơn không, nhà cung cấp ném một ngoại lệ để thông báo cho khách hàng rằng điều kiện tiên quyết đã bị phá vỡ, và trong cả hai trường hợp - DbC và lập trình phòng thủ — khách hàng phải tìm ra cách để đáp ứng điều đó. DbC giúp công việc của nhà cung cấp dễ dàng hơn.

Thiết kế theo hợp đồng cũng xác định tiêu chí cho tính chính xác cho một module phần mềm:

* Nếu lớp bất biến và điều kiện tiên quyết là đúng trước khi một nhà cung cấp được gọi bởi một khách hàng, sau đó là bất biến và postcondition sẽ là đúng sau khi dịch vụ đã được hoàn thành.
* Khi thực hiện cuộc gọi đến nhà cung cấp, mô-đun phần mềm không được vi phạm các điều kiện tiên quyết của nhà cung cấp.

Thiết kế theo hợp đồng cũng có thể tạo điều kiện tái sử dụng mã, vì hợp đồng cho từng đoạn mã được ghi chép đầy đủ. Các hợp đồng cho một mô-đun có thể được coi là một dạng tài liệu phần mềm cho hành vi của mô-đun đó.
### Ý nghĩa hiệu suất

Các điều kiện hợp đồng sẽ không bao giờ bị vi phạm trong khi thực hiện chương trình không có lỗi. Các hợp đồng do đó thường chỉ được kiểm tra trong chế độ gỡ lỗi trong quá trình phát triển phần mềm. Sau khi phát hành, kiểm tra hợp đồng bị vô hiệu hóa để tối đa hóa hiệu suất.

Trong nhiều ngôn ngữ lập trình, các hợp đồng được thực hiện với khẳng định. Asserts được mặc định biên dịch trong chế độ phát hành trong C / C ++, và tương tự như ngừng hoạt động trong C # [8] và Java. Điều này có hiệu quả loại bỏ các chi phí thời gian chạy của hợp đồng phát hành.

### Mối quan hệ với kiểm thử phần mềm

Thiết kế theo hợp đồng không thay thế các chiến lược thử nghiệm thường xuyên, chẳng hạn như thử nghiệm đơn vị, thử nghiệm tích hợp và kiểm tra hệ thống. Thay vào đó, nó bổ sung cho thử nghiệm bên ngoài với các phép kiểm thử nội bộ có thể được kích hoạt cho cả các thử nghiệm riêng biệt và trong mã sản xuất trong giai đoạn thử nghiệm. Lợi thế của tự kiểm tra nội bộ là chúng có thể phát hiện lỗi trước khi chúng tự biểu hiện dưới dạng kết quả không hợp lệ được khách hàng quan sát. Điều này dẫn đến phát hiện lỗi sớm hơn và cụ thể hơn.

Việc sử dụng các xác nhận có thể được coi là một hình thức kiểm tra oracle, một cách để kiểm tra thiết kế bằng cách thực hiện hợp đồng.

### Hỗ trợ ngôn ngữ
 ... *Khoong cos gif ddeer dichj car*
