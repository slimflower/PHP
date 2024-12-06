# Lý Thuyết
## 1. Khai báo biến trong PHP
- Để khai báo biến trong PHP ta sử dụng ký từ `$` kèm tên biến ở phía sau, còn khai báo hằng thì không có ký tự `$`.
### 1.1 Biến trong PHP là gì ?
- Trong PHP, biến là `một định danh` dùng để `lưu trữ vị trí của dữ liệu trong ô nhớ máy tính`. Dữ liệu nằm trong ô nhớ, mỗi khi bạn gọi đến biến thì máy tính sẽ trỏ đến ô nhớ đó.
- Chúng ta có hai loại biến, thứ nhất là `biến thông thường`, và thứ hai là `biến hằng số`. Nếu xét về phạm vi thì có biến toàn cục và biến cục bộ.
- Biến có thể lưu trữ `các kiểu dữ liệu trong PHP` khác nhau.Có thể là một chuỗi, một ký tự, một con số, hoặc thậm chí là các kiểu dữ liệu phức tạp hơn như đối tượng và mảng. Chúng ta sẽ tìm hiểu kỹ hơn trong chuyên đề PHP căn bản này.
### 1.2 Cách khai báo biến trong PHP
- Cú pháp của biến bắt đầu bằng dấu đô la `$` và tiếp theo là các chữ, số, dấu gạch dưới. Ký tự đầu tiên của tên biến phải là chữ hoặc là dấu gạch dưới, không được là số.
 ```php
<?php
$sinhvien = ''; //đúng
$_sinh_vien = ''; //đúng
$sinh_vien90 = ''; //đúng
$90sinhvien = ''; //sai
?>
```
- **Lưu ý**:PHP là một ngôn ngữ có phân biệt chữ hoa chữ thường. Ví dụ: `$sinhvien` khác `$SinhVien`
#### 1.2.1 Truyền biến trong PHP
- Để truyền biến, hay gán giá trị cho biến ta dùng toán tử phép gán `=`.
- Ví dụ: Gián giá trị `"Hello World"` vào biến `$hello`.
```php
$hello = 'Hello Word';
```
#### 1.2.2 Lấy giá trị của biến 
- Thay vì xuất trực tiếp chuỗi thì ta xuất giá trị của biến ra màn hình.
- Ví dụ: In ra giá trị của biến `$sinhvien`.
```php
<?php
$sinhvien = 'Nguyen Van A';
echo $sinhvien; // Xuất ra màn hình
?>
```
### 1.3 Đặt tên biến trong PHP
- Tên biến trong PHP không phải đặt sao cũng được, mà ban phải tuân thủ những quy tắc dưới đây.
#### 1.3.1 Quy tắc đặt tên biến 
- Tên không được chứa kí tự đặc biệt, ngoài ký tự đô la ở đầu biến và ký tự gạch dưới.
- Tên biến không được chứa ký tự khoảng trắng, không đặt có dấu.
- Tên biến có thể sử dụng chữ in hoa hoặc in thường đều được, và lưu ý là nó phân biệt đấy nha.
- Ký tư đầu tiên của tên biến phải là chữ cái, hoặc là dấu gạch dưới.
#### 1.3.2 Cách đặt tên biến hiệu quả 
- Mặc dù bạn có thể đặt tên biến bất kì, nhưng nếu một người có kinh nghiệm thì sẽ đặt theo những lưu ý dưới đây:
    - Đặt tên biến phải có ý nghĩa, không sử dụng kết hợp in hoa và in thường lộn xộn, mà phải đặt theo quy tắc riêng mà bạn tự đặt ra.
    - Không nên lạm dụng số để đặt quá nhiều.
    - Đặt tên biến có thể dài, nhưng đọc là hiểu ý nghĩa liền.
### 1.4 Ghi chú cho biến trong PHP
- Trong dòng lệnh code php đôi khi ta muốn thêm những lời giải thích ý nghĩa của dòng lệnh đó để sau này nhìn vào dễ hiểu hơn. Nhưng với trình biên dịch thì nó sẽ chạy tất cả các đoạn code nằm bên trong thẻ mở `<?php và thẻ đóng ?>`, nếu chúng ta gõ lung tung thì trình biên dịch sẽ báo sai vì không đúng với cú pháp PHP. Vì thế trước khi tìm hiểu biến và hằng số trong php chúng ta tìm hiểu cú pháp ghi chú trước.
- PHP hỗ trợ cho chúng ta hai cách để ghi chú đó là:
    - Ghi chú cho 1 dòng: // noi dung can ghi chu
    - Ghi chú cho nhiều dòng: /*noi dung can ghi chu*
```php
<?php
echo 'Chào Mừng Các Bạn Đến Với freetuts.net'; // dòng ghi chú
/*Hoặc dòng ghi chú*/
?>
```
### 1.5 Các loại biến trong PHP
- Trong PHP có một số loại biến như: Biến thông thường, biến toàn cục, biến cục bộ, biến hằng số, biến tĩnh ... những loại này chúng ta sẽ tìm hiểu dần trong chuyên đề PHP cơ bản này.
- Nếu xét theo tính chất thì chúng ta có biến toàn cục và biến cụ bộ. Biến tĩnh cũng là một loại biến cục bộ, bởi nó chỉ dùng trong chính đối tượng của lớp đó. Biến hằng là một biến toàn cục, bởi phạm vi sử dụng nó là toàn bộ chương trình.
#### 1.5.1 Khai báo biến toàn cục
- Là loại biến nằm bên ngoài toàn của toàn bộ chương trình, loại biến này ở đâu bạn cũng có thể sử dụng được, kể cả bên trong hàm.
```php
$bientoancuc = 'freetuts.net';
 
function test_freetuts(){
    global $bientoancuc; // gọi đến biến toàn cục
    echo $bientoancuc;
}
 
test_freetuts();
```
#### 1.5.2 Khai báo biến cục bộ
- Biến cục bộ thì đơn giản, bạn khai báo ở đâu thì chỉ sử dụng được ở đó mà thôi. Nếu bạn khai báo trong hàm thì sử dụng chỉ trong hàm, khai báo trong đối tượng thì chỉ sử dụng trong đối tượng đó mà thôi.
```php
function test_freetuts(){
    $domain = "freetuts.net";
}
 
// sai vì biến domain là cục bộ, chỉ sử dụng trong hàm test_freetuts
echo $domain;
```
#### 1.5.3 Khai báo biến hằng số
- **Hằng cũng là một biến*** nhưng bạn không thể thay đổi giá trị của nó, và cách khai báo biến và hằng số cũng khác nhau.
- Cú Pháp: `define(‘ten_hang’, ‘gia_tri’)`;
- **Trong đó:**
    - `define`: hàm tạo biến hằng
    - `ten_hang`: là tên biến hằng
    - `gia_tri`: giá trị của hằng
```php
<?php
/* Tạo một hằng số có tên là SDT và gán giá trị cho nó là 0909090909*/
define('SDT', '0909090909');
echo SDT; // xuất ra màn hình giá trị của hằng.
?>
```
### 1.6 Các ví dụ về sử dụng biến trong PHP
- **Sử dụng biến trong vòng lặp**: Chương trình tính tổn các số từ 0 đến 99 nên ta phải sử dùng vòng lặp.
```php
$tong = 0;
for ($i = 0; $i < 100; $i++)
{
    $tong += $i;
}
echo $tong;
```
- **Khai báo biến tạm trong PHP**: Biến tạm là một loại biến dùng để lưu trữ dữ liệu tạm thời trong quá trình tính toán.
```php
// Hoán đổi giá trị giữa biến $a và $b
function swap(&$a, &$b){
    $tmp = $a; // khai báo biến tạm để chứa a
    $a = $b;
    $b = $tmp;
}
```
- **Khai báo biến cờ trong PHP**: Biến cờ trong PHP đóng vai trò như một cờ hiệu, giúp chương trình kiểm tra điều kiện dễ dàng hơn.
```php
// Hoán đổi giá trị giữa biến $a và $b
function check($a){
    $flag = false; // ban đầu giả sử nó không nằm trong dãy số 1 - 7 - 11
    if ($a == 1){
        $flag = true;
    }
    if ($a == 7){
        $flag = true;
    }
    if ($a == 11){
        $flag = true;
    }
    return $flag;
}
```
