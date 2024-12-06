## 2. Các kiểu dữ liệu trong PHP và các loại biến tương ứng 
- Trong PHP có các kiểu dữ liệu như kiểu INT, Kiểu Boolean, Kiểu Số Thực (float, double), Kiểu Chuỗi, Kiểu Mảng (array), Kiểu NULL, Kiểu Đối Tượng (object).
### 2.1 Kiểu dữ liệu INT
- Chữ `INT` là viết tắt của chữ `INTEGER`, là một kiểu dữ liệu dạng số và có thể ở viết ở nhiều cơ số khác nhau.
- Ví dụ :
```php
<?php
$thap_phan = 123; // Số thập phân
$so_am = -123; // Số âm
$bat_phan = 0123; // số bát phân
$thap_luc_phan = 0x1A; // và số thập lục phân
?>
```
- Kiểu số INT Chúng ta không dùng dấu nháy để bao quanh nó và kích thước của kiểu INT là 32bit. Trong PHP không hỗ trợ nhiều kiểu Unsigned Integer (Số nguyên dương) nên nếu bạn sử dụng vượt quá giới hạn của nó thì mặc nhiên trình biên dịch sẽ hiểu đây là kiểu Float (số thực), tuy nhiên không phải lúc nào điều này cũng đúng cho trường hợp số dương.
#### 2.1.1 Khai báo kiểu dữ liệu INT 
- Để khai báo một biến kiểu INT bạn sẽ gán giá trị cho nó là số nguyên (kể cả số âm).
- **Ví dụ** :
```php
<?php
$tuoi = 12; // biến $tuoi là kiểu INT có giá trị = 12
?>
```
#### 2.1.2 Ép dữ liệu sang kiểu INT
- Cú pháp : `(int)$ten_bien;`
- **Ví dụ** :
```php
<?php
$tuoi = '98'; // biến tuổi là một chuỗi có giá trị bằng '98'
$tuoi = (int)$tuoi; // lúc này biến $tuoi là một kiểu int có giá trị 98
?>
```
- Việc chuyển đổi này trong PHP đôi khi lại không cần thiết vì các kiểu dữ liệu trong php tự động chuyển các biến sang các kiểu thích hợp để thực hiện phép tính, tuy nhiên sau khi thực hiện tính toán thì biến đó sẽ tự chuyển lại kiểu dữ liệu ban đầu.
- **Ví dụ** :
```php
<?php
$a = '123';  // Biến $a là kiểu chuỗi có giá trị bằng '123'
$b = 123; // Biến $b là kiểu INT có giá trị bằng 123
$c = $a + $b; // Biến C là kết quả của phép toán $a + $b và sẽ có giá trị là 246 nên nó là kiểu INT
var_dump(is_int($c)); // hàm is_int($tenbien) dùng để kiểm tra một biến có phải là kiểu INT hay không
var_dump(is_int($a)); // kết quả là false vì biến $a là kiểu string
?>
```
- Trong ví dụ này các bạn thấy biến $a là chuỗi còn biến $b là số, khi ta cộng 2 biến lại thì các biến sẽ tự động chuyển sang kiểu số INT thích hợp để cộng, và kết quả là kiểu INT gán vào biến $c. Để kiểm tra bạn dùng dòng lệnh var_dump(is_int($c)); để xuất ra màn hình kết quả kiểm tra.
- **Ví dụ** :
```php
<?php
$a = 'a123'; // biến $a có giá trị là chuỗi 'a123'
$a = (int)$a; // chuyển $a sang kiểu INT
echo $a; // kết quả xuất ra màn hình là số 0
?>
```
- Chạy đoạn lệnh này các bạn sẽ thấy kết quả ra số 0. Tại sao? vì bạn thấy biến $a có ký tự đầu tiên không phải ở dạng số nên nó sẽ tự động cắt bỏ tất cả những ký tự đằng sau ký tự a nên chuỗi này rỗng, mà giá trị rỗng chuyển sang kiểu INT có giá trị bằng không.
- **Ví dụ** :
```php
<?php
$a = '123a'; // biến $a có giá trị là chuỗi '123a'
$a = (int)$a; // chuyển $a sang kiểu INT
echo $a; // kết quả xuất ra màn hình là số 123
?>
```
#### 2.1.3 Kiểm tra dữ liệu có phải kiểu INT
- Để kiểm tra một biến nào đó có phải kiểu INT không bạn dùng 2 hàm is_int($bien) hoặc is_integer($bien). kết quả trả về giá trị True nếu là kiểu INT và False nếu không phải kiểu INT.
### 2.2 Kiểu dữ liệu boolean 
- Đây là một kiểu dữ liệu đơn giản nhất trong các kiểu dữ liệu trong PHP, nó chỉ chứa 2 giá trị là đúng hoặc sai (TRUE hoặc FALSE). Để tạo biến kiểu boolean thì bạn gán giá trị cho nó là TRUE hoặc FALSE. Lưu ý TRUE, FALSE không phân biệt hoa thường, nghĩa là bạn gõ thế nào cũng được miễn là đúng.
```php
<?php
$is_admin = false; // biến $admin là kiểu boolean có gái trị là false
?>
```
#### 2.2.1 Ép dữ liệu sang kiểu boolean 
- Tương tự như kiểu INT bạn sử dụng (bool) hoặc (boolean) để ép kiểu sang kiểu bool. Như vậy trong PHP thì bool và boolean là 2 từ khóa có cùng một ý nghĩa.
- **Ví dụ** :
```php
<?php
$bool = 1; // biến $bool là kiểu int
$bool = (bool)$bool; // lúc này biến $bool sẽ có kiểu boolean
// Hoặc
$bool = (boolean)$bool; // lúc này biến $bool sẽ có kiểu boolean
?>
```
- Các ký tự **0**, ký tự trống và null đều được quy về giá trị **FALSE**, các ký tự còn lại quy về **TRUE**. Việc chuyển đổi này đôi khi cũng không cần thiết vì php tự xem xét giá trị và quy về **TRUE** hay **FALSE**.
- **Ví dụ** :
```php
<?php
$a = 123; // TRUE
$b = 0; // FALSE
$c = '0'; // FALSE
$d = 'a123b' // TRUE
$e = null; // FALSE
$f = ''; // FALSE
?>
```
#### 2.2.2 Kiểm tra một biến kiểu boolean 
- Để kiểm tra một biến có phải kiểu boolean bạn dùng hàm is_bool($bien); để kiểm tra, kết quả của hàm này trả về TRUE nếu là kiểu bool, ngược lại là false nếu không phải kiểu bool.
### 2.3 Kiểu số thực 
- Hiểu một cách nôm na kiểu số thực là những số có phần dư, còn kiểu INT là những số không dư phần nào, như số 1.234 là kiểu số thực, 1234 là kiểu số nguyên (INT). Kích cỡ của nó phụ thuộc xác định phụ thuộc vào từng platform nhưng giá trị lớn nhất xấp xỉ 1.8e308, các kiểu dữ liệu trong php của kiểu số thực gồm có kiểu float, double.
- **Ví dụ** :
```php
<?php
$a = 1.234; // Kiểu số thực
?>
```
#### 2.3.1 Ép sang kiểu dữ liệu số thực 
- Bạn dùng (float), (double) để chuyển kiểu dữ liệu sang số thực cho một biến
- **Ví dụ** :
```php
<?php
$a = 123; // biến $a kiểu int
$a = (float)$a; // Biến $a lúc này kiểu số thực (float)
$a = (double)$a; // Biến $a lúc này kiểu ố thực (double)
?>
```
#### 2.3.2 Kiểm tra một biến kiểu số thực 
- Để kiểm tra một biến phải kiểu số thực không bạn dùng hàm `is_float($bien)` để kiểm tra cho kiểu float, `is_double($bien)` để kiểm tra cho kiểu double. Kết quả 2 hàm này trả về TRUE nếu đúng, FALSE nếu sai.
### 2.4 Kiểu chuỗi 
- Các kiểu dữ liệu trong php thì kiểu chuỗi mình gồm kiểu `string` (chuỗi) và `char` (ký tự), mỗi ký tự là 1 byte và là một trong 256 ký tự khác nhau, để khai báo báo các bạn chỉ việc khai báo một biến và gán giá trị chuỗi cho nó, chuỗi phải được bao quanh bằng dấu nháy đơn `‘` hoặc dấu nháy kép `“`. Ép kiểu cũng như trên ta dùng (string) để chuyển sang kiểu chuỗi.
- **Ví dụ**:
```php
<?php
$a = 123; // khai báo biến $a kiểu int có giá trị 123
$a = (string)$a; //Chuyển biến $a thành kiểu chuỗi và có giá trị là '123'
?>
```
#### 2.4.1 Kiểm tra một biến kiểu string 
- Để kiểm tra một biến kiểu chuỗi (string) ta dùng hàm is_string($bien), kết quả hàm này trả về TRUE nếu đúng và FALSE nếu không đúng.
### 2.5 Kiểu mảng (array)
- Mảng là danh sách các phần tử có cùng kiểu dữ liệu và nó là một trong các kiểu dữ liệu trong php có độ phức tạp tính toán cao. Có 2 loại mảng là `mảng một chiều` hoặc `mảng nhiều chiều`. Riêng với PHP thì các phần tử của mảng có thể không cùng kiểu dữ liệu, và các phần tử của mảng được truy xuất thông qua các chỉ mục(vị trí) của nó nằm trong mảng.
#### 2.5.1 Khởi tạo và truy xuất các phần tử trong mảng 
- Để khai báo mảng ta dùng cú pháp sau:
```php
<?php
$ten_mang = array(); // khởi tạo một mảng gán vào biến $ten_mang
?>
```
- Giả sử tôi có 2 sinh viên là Nguyễn Văn A và Nguyễn Văn B, giờ tôi sẽ khởi tạo một mảng $sinhvien để lưu 2 sinh viên này lại.
- **Note** : Các bạn dùng hàm var_dump($mang); để in ra các phần tử của mạng để test trong quá trình học nhé. Hàm này có thể sử dụng được tất cả các kiểu dữ liệu trong php.
- **Cách 1** :
```php
<?php
$sinhvien = array('Nguyễn Văn A', 'Nguyễn Văn B');
print_r($sinhvien);
?>
```
- **Cách 2**:
```php
<?php
$sinhvien = array(
0 => 'Nguyễn Văn A',
1 => 'Nguyễn Văn B'
);
print_r($sinhvien);
?>
```
- **Cách 3**:
```php
<?php
$sinhvien = array();
$sinhvien[0] = 'Nguyễn Văn A';
$sinhvien[1] = 'Nguyễn Văn B';
print_r($sinhvien);
?>
```
- **Cách 4**:
```php
<?php
$sinhvien = array();
$sinhvien[] = 'Nguyễn văn A';
$sinhvien[] = 'Nguyễn Văn B';
print_r($sinhvien);
?>
```
#### 2.5.2 Mảng chỉ có mục 
- Là mảng có các phần tử được định danh một chỉ mục (kiểu số) và bắt đầu bằng số 0 và phần tử cuối cùng có chỉ mục là `(n-1)`, trong đó n là tổng số phần tử của mảng. Điều này có nghĩa nếu mảng của bạn có 10 phần từ thì lần lượt các vị trí phần tử trong mảng là: `[0] – [1] – [2] – [3] – [4] – [5] – [6] – [7] – [8] – [9]`
- **Quay lại 4 cách giải của ví dụ trên** :
 - **Với cách 1**: Bạn khởi tạo một mảng và gán trực tiếp 2 phần từ vào, vì mảng bắt đầu từ 0 nên nó tự hiểu phần tử đầu tiên có chỉ mục =0, và phần tử thứ 2 = 1.
  -  **Với cách 2**: Bạn khởi taọ một mảng và gán trực tiếp 2 phần tử vào, nhưng lúc gán bạn có ghi rõ các chỉ mục cho từng phần tử.
  -  **Với cách 3**: Ban khởi tạo một mảng rỗng. sau đó bạn dùng 2 lệnh để gán 2 phần tử vào, mỗi lệnh gán bạn có chỉ rõ chỉ mục.
  -  **Với cách 4**: Bạn khởi tạo một mảng rỗng, sau đó bạn dùng 2 lệnh gán 2 phần tử vào nhưng bạn lại không chỉ rõ chỉ mục, lúc này PHP sẽ kiểm tra thấy mảng đang rỗng nên phần tử đầu tiên nó sẽ mặc định gán chỉ mục = 0, và phần tử tiếp theo sẽ bằng phần tử trước nó + 1 tức là sẽ = 1.
- Để truy xuất các phần tử của mảng chỉ mục ta dùng cú pháp sau:
- `$tenmang[$index]`; trong đó `$index` là chỉ mục bạn muốn lấy.
#### 2.5.3 Mảng kết hợp 
- Là Mảng có các phần tử được định danh bằng một cái tên và đương nhiên vị trí các phần tử sẽ không có thứ tự.
- **Ví dụ 15** :
```php
<?php
$sinhvien = array(
'sinhvien_a' => 'Nguyễn Văn A',
'sinhvien_b' => 'Nguyễn Văn B'
);
print_r($sinhvien);
?>
```
```php
<?php
$sinhvien = array();
$sinhvien['sinhvien_a'] = 'Nguyễn Văn A';
$sinhvien['sinhvien_b'] = 'Nguyễn Văn B';
print_r($sinhvien);
?>
```
- **Xét ví dụ sau** :
```php
<?php
$sinhvien = array();
$sinhvien['sinhvien_a'] = 'Nguyễn Văn A';
$sinhvien['sinhvien_b'] = 'Nguyễn Văn B';
print_r($sinhvien);
?>
```
- Việc truy xuất các phần tử trong mảng kết hợp cũng tương tự như mảng chỉ mục ta dùng cú pháp sau: `$tenmang[$name]`, trong đó `$name` là tên của phần tử bạn muốn lấy ra.
- **Ví dụ** :
```php
<?php
$sinhvien = array();
$sinhvien['sinhvien_a'] = 'Nguyễn Văn A';
$sinhvien['sinhvien_b'] = 'Nguyễn Văn B';
echo $sinhvien['sinhvien_a']; // xuất ra màn hình sinh viên Nguyễn Văn A
echo $sinhvien['sinhvien_b']; // xuất ra màn hình sinh viên Nguyễn Văn B
?>
```
#### 2.5.4 Mảng một chiều 
- Tất cả những ví dụ ở trên gọi là mảng 1 chiều (gồm mảng 1 chiều chi mục, mảng một chiều kết hợp)

<img width="677" alt="Ảnh màn hình 2024-12-06 lúc 10 18 10" src="https://github.com/user-attachments/assets/2efd222f-2049-4778-a899-a0492313107c">

#### 2.5.5 Mảng nhiều chiều 
- Là mảng có nhiều chỉ mục cho từng phần tử, ví dụ mảng 2 chiều thì mỗi phần tử có 2 chỉ muc, 3 chiều thì mỗi phần tử có 3 chỉ mục, …
- Mảng nhiều chiều thực chất cũng chỉ là mảng 1 chiều nhưng được thể hiện dưới dạng nhiều chiều.
- Xem hình minh họa mảng 2 chiều sau được biểu hiện bằng số dòng và số cột (nghĩa là 2 chiều giống trong hình học không gian 2 chiều), mỗi phần tử sẽ được định vị trí ở điểm giao nhau của chỉ số cột và dòng hiện tại.

<img width="628" alt="Ảnh màn hình 2024-12-06 lúc 10 19 39" src="https://github.com/user-attachments/assets/ec99b35f-ca8b-47b4-9f7d-4a7b863ca627">

- Ví dụ về mảng 2 chiều :
```php
<?php
$a = array();
$a[0][1] = 123;
$a[0][2] = 321;
?>
```
- Ví dụ xuất phần tử mảng 2 chiều :
```php
<?php
$a = array();
$a[0][1] = 123;
$a[0][2] = 321;
echo $a[0][1]; // in ra giá trị 123
echo $a[0][2]; // in ra giá trị 321
?>
```
#### 2.5.6 Kiểm tra một biến kiểu mảng 
- Để kiểm tra một biến có phải kiểu mảng (array) không ta dùng hàm `is_array($bien)`, hàm này trả về TRUE nếu đúng và FALSE nếu không đúng.
### 2.6 Kiểu giá trị NULL
- Đây là kiểu đặc biệt trong PHP và cũng như các ngôn ngữ lập trình khác, nó mang giá trị rỗng.
- Lúc bạn khởi tạo một biến và bạn gán = NULL thì sẽ hệ thông sẽ không tốn bộ nhớ để lưu trữ, nên việc sử dụng nó rất có lợi.
- Kiểu NULL khi ép kiểu sang kiểu INT thì bằng 0, khi ép kiểu sang kiểu chuỗi thì = rỗng, và khi ép sang kiểu boolean thì mang giá trị FALSE.
- **Ví dụ**:
```php
<?php 
$a = null; // Khởi tạo biến $a và gán giá trị null
$b = (int)$a; // Biến $b có giá trị là ( 0 )
$c = (string)$a; // Biến $c có giá trị rỗng ( '' )
$d = (bool)$a; // Biến $d có giá trị FALSE
?>
```
#### 2.6.1 Kiểm tra một biến có giá trị null
- Để kiểm tra một biến có giá trị null hay không ta dùng hàm `is_null($bien)`. Biến này trả về TRUE nếu đúng và FALSE nếu không đúng.
### 2.7 Kiểu Object(đối tượng )
