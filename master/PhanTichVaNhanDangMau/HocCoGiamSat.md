Đề cương ôn tập
***
# 1. Phát biểu bài toán nhận dạng mẫu có giám sát và cho biết cách tìm hàm hồi quy nhờ xác định tham số. Nếu tập có 100 mẫu và có thể nhận 5 nhãn thì có thể có bao nhiêu giả thuyết?

## Phát biểu bài toán nhận dạng mẫu có giám sát
- Học có giám sát (supervised learning) dùng để chỉ các bài toán học mà trong dữ liệu/kinh nghiệm hay quá trình học có các thông tin định hướng để cải thiện độ đo thực hiện.
- Hai bài toán học có giám sát thường gặp nhất là **phân lớp** và **hồi quy hàm số** dựa trên một tập mẫu đã biết nhãn.
- Cho một tập mẫu quan sát được $D=\{x^k, y^k\}, k \in \{1, ..., N\}$, trong đó $D_x = \{x^k\}$ là tập con của tập đối tượng X còn $D_y=\{y^k\}$ là nhãn trong tập Y của các đối tượng tương ứng. Ta cần tìm nhãn cho các đối tượng x mới trong X.

## Cách tìm hàm hồi quy nhờ xác định tham số
Phương pháp thông dụng giải bài toán hồi quy là tìm hàm hồi quy g có biểu diễn tham số như sau:
$$g(x) = \varphi(x, c_1, ..., c_M)$$

Việc xác định các hệ số $c_k$ được thực hiện nhờ tìm cực tiểu tổng bình phương sai số (sum of squared errors - SSE):
$$E(c) = \sum_{k=1}^{N} [\varphi(x^k)-y^k]^2$$

Với bài toán nội suy thì cực tiểu của E tìm được sẽ bằng 0. Trường hợp tổng quát, véc-tơ c có thể tìm bằng thuật toán gradient hoặc biến thể của nó. Một biến thể đơn giản nhất được mô tả như sau:
1. Khởi tạo $c=c^0\in^M$ tùy ý
2. Thực hiện lặp:
   - 2.1. Tính $E'(c^0) = \left[\frac{\partial E}{\partial c_1}, ..., \frac{\partial E}{\partial c_m}\right]^T$;
   - 2.2. $\alpha_1=\alpha$ // $\alpha\in(0,1]$ cho trước
   - 2.3. $c^1=c^0-\alpha_1E'(c^0)$;
   - 2.4. Nếu $E(c^1)<E(c^0)$ thì $c^0 \leftarrow c^1$ và quay lại 2.1;
   - 2.5. Ngược lại: $\alpha_1 \leftarrow \frac{\alpha_1}{2}$ và trở lại 2.3

Thuật toán dừng khi $||E'(c^1)||$ đủ bé, trong đó $||u||=\sqrt{\sum_{i=1}^{M} u_i^2}$ là chuẩn Euclide của véc-tơ u trong $R^M$.

Trong trường hợp tuyến tính, ta giải hệ phương trình đạo hàm bằng 0 để tìm ra cực trị của hàm.

## Nếu tập có 100 mẫu và có thể nhận 5 nhãn thì có thể có bao nhiêu giả thuyết?
Có $5^{100}$ giả thuyết
***

# 2. Giới thiệu các phương pháp tìm hàm hồi quy mà anh/ chị biết.
Các phương pháp tìm hàm hồi quy:
- Giải hệ phương trình trong trường hợp tuyến tính
- Phương pháp tối ưu (gradient)
***

# 3. Trình bày phương pháp trực tiếp hàm hồi quy và áp dụng cho hàm hồi quy dạng tuyến tính.
Trong trường hợp tuyến tính, ta giải hệ phương trình đạo hàm bằng 0 để tìm ra cực trị của hàm.
***
# 4. Trình bày khái niệm cây quyết định và thuật toán ID3. So sánh các thuật toán ID3 và C4.5
## Lược đồ chung xây dựng cây quyết định
Xây dựng lược đồ cây quyết định thực hiện đệ quy giống nhau như sau:
1. Mở một nút gốc, nếu dữ liệu thuần nhất hoặc hết thuộc tính thì gán nhãn chung hoặc nhãn đa số và nút và làm nút lá
2. Chọn thuộc tính tốt nhất gán cho nút và phát triển các nhãn theo giá trị thuộc tính này cùng với xác định các tập con dữ liệu tương ứng với giá trị được xét
3. Trở lại bước 1 cho đến khi mọi nút lá được xác định

## Thuật toán ID3
ID3(Tập mẫu, tập nhãn, tập thuộc tính)
0. Khởi tạo: D, tập nhãn, tập thuộc tính;
1. Tạo nút gốc cho cây;
2. Gán nhãn cho nút nếu dữ liệu thuần nhất hoặc tập thuộc tính là rỗng
   1. Nếu mọi mẫu đều dương tính/âm tính thì nhãn nút gốc là +/-
   2. Nếu tập các thuộc tính là rỗng, trả về cây 1 nút gốc có nhãn là giá trị phổ biến của thuộc tính đích trong tập các mẫu
   3. Các trường hợp khác sang bước 3
3. Gồm các bước:
   1. Xác định thuộc tính phân loại tập mẫu tốt nhất trong tập thuộc tính
   2. A $\leftarrow$ thuộc tính phân lớp tốt nhất
   3. Với mỗi giá trị có thể $v_i$ của thuộc tính A, thực hiện:
      1. THêm 1 nhánh mới dưới nút gốc với mỗi điều kiện $A=v_i$
      2. Xác định $Example_{v_i}=\{x \in \text{tập mẫu}: x \text{ có giá trị vì ở thuộc tính } A\}$
      3. Nếu $Example_{v_i}$ là rỗng thì thêm dưới nhánh 1 nút lá có nhãn là nhãn phổ biến nhất của các mẫu trong tập mẫu
      4. Ngược lại, trở lại bước 1 với khơi tạo: 
      $$D = \text{Examples}, \text{tập nhãn}, \text{tập thuộc tính} - \{A\}$$

## So sánh thuật toán ID3 và thuật toán C4.5
Thuật toán C4.5 được đề xuất để khắc phục các nhược điểm có trong ID3
1. Ngoài áp dụng tiêu chuẩn *Thu hoạch thông tin cực đại*, C4.5 còn đề xuất sử dụng tiêu chuẩn *Tỷ lệ thu hoạch thông tin cực đại (Gainratio)* để dùng cho các trường hợp mà tiêu chuẩn trước áp dụng không tốt
2. Áp dụng các kỹ thuật chặn sớm để tránh overfit
3. Đề xuất giải pháp xử lý trường hợp mẫu có thuộc tính thiếu giá trị
4. Đề xuất phương pháp áp dụng cho thuộc tính nhận giá trị liên tục
***

# 5. Trình bày thuật toán C4.5 xây dựng cây quyết định, cách xử lý thuộc tính có giá trị liên tục và
mẫu có giá trị thuộc tính bị mất so với CRAT thế nào?