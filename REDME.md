
---
## Quy tắc Biểu Thức Chính Quy 


~Regular Expression bạn cần biết~


*Bạn đang học lập trình web? Bạn 
đang cần sử dụng biểu thức chính 
quy để validation dữ liệu nhưng 
chưa biết bắt đầu từ đâu? Yên tâm 
chuỗi bài bên dưới này tôi chia sẻ 
cho bạn từng bước. Biểu thức chính 
quy là phần hay nhưng khá trừu 
tượng, tôi đã mất khá nhiều thời 
gian để hiểu về nó và tôi hi vong 
rằng những nuội dung. bên dưới sẽ 
giúp ích cho bạn.*
#### CÁC DẠNG

- - -
### Bài 1: Biểu thức chính quy là gì?
Biểu thức chính quy (regular expression, viết tắt là regexp, regex hay
regxp) là một chuỗi miêu tả một bộ các chuỗi khác, theo những quy
tắc cú pháp nhất định. Biểu thức chính quy thường được dùng trong
các trình biên tập văn bản và các tiện ích tìm kiếm và xử lý văn bản
dựa trên các mẫu được quy định  .
Trong các ngôn ngữ lập trình cũng dược sử dụng biểu thức chính quy
một cách rộng rãi để chuẩn hóa dữ liệu đầu vào hoặc tìm kiếm theo
một định dạng mẫu cho trước  .
Phần mà chúng ta cần học ở đây là đi sâu vào cách viết các chuổi
mẫu biểu thức chính quy để thực hiện các yêu cầu trong thực tế  . Một
phần ứng dụng của biểu thức chính quy là Validation Form hoặc làm
việc với Htaccess trong lập trình website
Ví dụ biểu thứ chính quy đơn giản
`/abc/`
Chuổi ký tự trên là chuổi mẫu, và chúng ta dùng nó để kiểm tra các
mẫu khác có chưa các ký tự abc hay không
Chúng ta đi xem xét các chuổi sau:
`abc def`
Chuổi này hợp lệ với chuổi mẫu vì chứa chuỗi abc
`abdefgh123`
Chuổi này thì không đúng với chuỗi mẫu vì không chứa chuỗi abc
___
### Bài 2: Biểu diễn miền giá trị mẫu trong biểu
thức chính quy
Ở bài trước chúng ta đã hiểu qua biểu thức chính quy là gì và thông
qua một số ví dụ đơn giản cũng đã hiểu sơ qua về ý nghĩa hoạt động
của nó  .
Tuy nhiên trên thực tế tập dữ liệu mẫu nó vô cùng đa dạng và phức
tạp  .
Ví dụ yêu cầu của chúng ta cần một mẫu kiểm tra một trường nhập
vào là các chữ số nằm trong tập hợp {1,2,..9} chúng ta không thể sử
dụng cách thông thường là liệu kê tất cả ra và so sánh được  .
Hôm nay thông qua một số cú pháp trong biểu thức chính quy thì
công việc chúng ta sẽ nhẹ nhàng hơn rất nhiều
Dấu ngoặc vuông […] trong biểu thức chính quy
Khi sử dụng dấu ngoặc vuông này biểu thức chính quy biểu thị
chuỗi mẫu cho phép chuổi so sánh chưa 1 ký tự bất trì trong các ký
tự nằm ở biên trong.
Ví dụ sau biểu diễn chuỗi mẫu chứa các ký tự abc
`/[abc]/`
Khi đấy các chuỗi : a, ad, abc có định dạng trùng với chuỗi mẫu vì nó
tồn tại ít nhất 1 ký tự có chứa 1 trong 3 ký tự trong tập hợp các ký tự
 `{a,b,c}`
Rõ ràng hơn, với chuổi mẫu như trên biểu diễn cho một ký tự bất kỳ
của chuổi có nằm trong tập hợp các ký tự trong nằm trong dấu
ngoặc []
Tiếp theo, một chuỗi có ký tự chứa một trong các chữ số 1,2,3 được
biểu diễn dưới dạng biểu thức chính quy như sau  .
`/[123]/`
Với lập luận như trên ta có các chuổi sau đúng theo chuỗi mẫu mà
chúng ta biểu diễn: `1abc, 345cd`
Và các chuỗi sau không đúng định dạng: abc456, cd357
Rồi, chắc đến đây các bạn cũng đã hiểu qua phần nào về cách làm
việc của biểu thức chính quy rồi  . Chúng ta đi tiếp qua luật tiếp theo  .
Dấu gạch ngang (-) trong ngoặc vuông ([…]) ở biểu
thức chính quy
Ở phần trước khi chúng biểu diễn tập hợp các ký tự liên tục hay
không chúng ta cũng liên kê ra, tuy nhiên làm như thế nó rất mất thời
gian  .
Với dấu gạch ngang sẽ cho phép chúng ta tiết kiệm thời gian khi nó
tự động tạo cho chúng ta một dãy các ký tự liên tục (Gồm các chữ
cái và chữ số)
Ví dụ sau biểu thị chuỗi mẫu yêu cầu chứa một trong các ký tự từ 0-9
`/[0-9]/`
Cách biểu diễn như trên nó tương đương với
`/[0123456789]/`
Nó đã tiết kiệm thời gian của chúng ta khi tự động tạo ra một dãy chử
số liên tục khi chúng ta chỉ cần khai báo ký tự bắt đầu và ký tự kết
thúc
Biểu diễn các chữ cái từ A đến Z ta viết như sau:
`/[A-Z]/`
Biễu diễn các chử cái từ a đến z nhỏ như sau:
`/[a-z]/`
Nâng cao hơn, chúng ta biểu diễn tập hợp ký tự mẫu bao gồm
– Các ký tự chữ số từ 0-9
– Các ký tự chữ cái thường a – z
– Các ký tự chữ cái hoa A – Z
Ta biểu diễn thành chuỗi sau
/[A-Za-z0-9]/
Ðấy, khá dễ hiểu đúng không nào? Tuy nhiên cũng có một số trường
hợp tập ký tự mẫu của mình muốn loại bỏ đi một số ký tự hoặc một
dãy ký tự nào đó chúng ta làm thế nào? Các bạn tiếp tục theo dõi
phần sau  .
Dấu mũ (^) trong biểu thức chính quy
Dấu mũ (^) để loại bỏ đi một số hoặc một dãy ký tự của tập hợp ký tự
mẫu khi nằm trong ngoặc đơn
Ví dụ tập ký tự mẫu của chung ta là bất kỳ loại trừ các ký tự {a,b}
`/[^ab]/`
Hoặc tập ký tự mẫu hoại trừ các số 0 đến 3
`/[^0-3]/`
Ðấy là cách chúng ta loại trừ đi tập hợp các ký tự hoặc dãy ký tự,
chúng ta chỉ cần cho dấu ^ vào trước tập hoặc dãy ký tự muốn loại bỏ
Ở bài này chúng ta vừa đi qua các tạo tập hợp, dãy và loại bỏ trong
ký tự mẫu  . Nó cũng không có gì khó khăn lắm đúng không nào?
Phần sau chúng ta bước qua phần hấp dẫn hơn chính là biễu diễn
tính lặp trong biểu thức chính quy  .
---
### Bài 3: Tính lặp của tập ký tự mẫu trong biểu
thức chính quy
Ở bài trước chúng ta mới tạo ra tập ký tự mẫu nằm trong […] và chuổi
so sánh chỉ cần có ký tự trùng với một trong các ký tự mẫu của biểu
thức chính quy là đươc  . Tuy nhiên trong thực tế ta muốn đi so sánh
chuổi có số ký tự nhất định nào đó với điều kiện mỗi ký tự thuộc vào
tập ký tự mẫu thì thế nào  .
Các cách sau đây cho chúng có thể lặp ký tự theo mong muốn
– Sử dụng ký tự *
– Sử dụng ký tự +
– Sử dụng dấu ngoặc nhọn {}
Ðể hiểu rõ hơn chúng ta đi qua từng phần một
Sử dụng ký tự *
Cách sử dụng    . Thêm ký tự * trước ký tự hoặc tập hợp có 0 hoặc
nhiều lần lặp lại
Ví dụ chuỗi mẫu sau là chuổi có hoặc không chứa ký tự a
`/a*/`
Với mấu trên các chuỗi sau trùng với biểu thức mẫu: cd, abc, aac
Sử dụng ký tự +
Với ký tự dấu cộng quy định ký tự hoặc tập ký tự phía trước nó được
lặp lại 1 hoặc nhiều lần
Ví dụ biểu thức chính quy sau yêu cầu chúng ta nhập vào chuổi có ít
nhất một ký tự a
`/a+/`
Ví dụ một số chuổi sau phù hợp với biểu thức trên: ab, aab
Sử dụng ký tự ngoặc kép {}
Với cú pháp này quy định việc gặp lại của một kỷ tự hoặc một tập ký
tự mẫu
1  . {n} : Trùng khớp khi ký tự hoặc dãi ký tự đằng trước có chính xác n
phần tử  .
Ví dụ biểu thức sau có tập các trường hợp trùng khớp là các chử số
có 4 chử số trong đó mỗi chữ số thuộc tập từ 1 đến 9
`/^[0-9]{4}$/`
2. {n, m} : Trùng khớp khi ký tự hoặc dãy ký tự đằng trước có n đến
m ký tự
Ví dụ sau biễu diễn biểu thức chính quy của Username với luật sau
– Các ký tự bao gồm các chử cái hoa, thường, dấu chấm, dấu gạch
dưới
– Có 6 đến 32 ký tự
Ta có biểu thức chính quy sau
`/^[A-Za-z0-9_\.]{6,32}$/`
3  . {n,} : Trùng khớp khi ký tự hoặc tập ký tự đằng trước có tổng số ký
tự từ n trở lên
Ví dụ biểu thức chính quy sau biểu diễn các số có lớn hơn 5 chử số
/^[0-9]{5,}$/
Ở bài này chúng ta đã nắm được tính lặp của biểu thức mẫu, tuy rằng
hơi khó hiểu nhưng bạn cố gắng làm lại và hình dung thì sẽ nắm được
tất cả thôi  .
Dựa vào từng yêu cầu của bài toán để có được các biểu diễn thích
hợp
---
### Bài 4: Ðịnh vị chuổi ký tự mẫu trong biểu thức
chính quy
Như đã giới thiệu ở phần đầu, biểu thức chính quy là một chuổi dùng
mô tả một bộ các chuổi khác  . Tất nhiên có nhiều trường hợp chúng
ta cần thêm một điều kiện nữa chính là việc mô tả chuổi kèm theo cả
vị trí  .
Một ví dụ nhỏ sau để chúng ta có thể hình dung qua: Tôi muốn tìm
tất cả các chuổi có bắt đầu bằng chuổi Win  .
Với điều kiện này này ta có các chuổi sau thỏa mản: Windown
, Winner
Còn các chuổi sau thì không thỏa mãn điều kiện: The Windown, He
is Winner
Vậy chúng ta cùng đi nghiên cứu các cách quy định vị trí của biểu
thức chính quy
Ðinh vị chuỗi bắt đầu với ký tự ^
Như ví dụ bên trên chúng ta đã quy định chuỗi bắt đầu là Win và nó
được mô tả như sau
`/^Win/`
Ðịnh vị chuỗi kết thúc với $
Trong thực thế chúng ta muốn chuổi so sánh phải có ký tự kết thúc
với biểu thức mẫu  . Trong biểu thức chính quy có ký tự $ cho phép
chúng ta quy định việc đó  .
Ví dụ để mô tả các chuổi có kết thúc là các chữ cái in thường
 `[a-z]`
gồm 3 ký tự
`/[a-z]{3}/`
Ðịnh vị chuỗi bắt đầu và kết thúc `^…$`
Trong đa số trường hợp áp dụng vào lập trình thì chúng ta sử dụng
biểu thức chính quy để mô tả các chuổi có định dạng cho trước và
tất nhiên là chuổi đấy phải khớp 100% với biểu thức mô tả mẫu nên
chúng ta thường sử dụng căp ký tự `^…$`
Ví dụ sau đây để mô tả Usernanme có các ký tự từ A đến Z, a đến z,
0-9, gạch dưới, dấu chấm, có 6 đến 32 ký tự
`/^[A-Za-z0-9_\.]{6,32}$/`
---
### Bài 5: Nhóm và lựa chọn một trong những
trong biểu thức chính quy
Nhóm hay còn gọi là kết nối các phần của biểu thức mẫu là một phần
không thể thiếu trong biểu thức chính quy, có giúp chúng ta quản lý
chuổi mô tả một cách rành mạch hơn thông qua việt nhóm từng
phần của chuổi mô tả  .
Nhóm biểu thức mô tả với `(…)`
Sử dụng cặp ký tự ngặc nhọn giúp chúng ta có thể nhóm các phần
của biểu thức mẫu tùy ý
Ví dụ biểu thức chính quy sau đây mô tả đường linh thân thiện
website
====https://unitop.vn/course/html-css-21-ngay.html
Phần đầu chính là domain nên ở chúng ta cần mô tả cho chuỗi sau
course/html-css-21-ngay.html
Cấu trúc link
– Link bắt đầu từ chuổi ‘khoa-hoc’
– Tiếp theo dấu `‘/’`
– Tiếp theo là chuỗi các ký tự mô tả của đường link: Bao gồm các ký tự
`[A-Za-z0-9]`
– Tiếp theo dấu `‘-‘`
– Tiếp theo là ID: Bao gồm các ký tự [0-9]
– Tiếp theo là chuổi `‘.html’`
Vậy biểu thức mô tả chính quy như sau
`^khoa-hoc/([a-zA-Z0-9_-]+)-([0-9]+).html$`
Vậy với việc sử dụng dấu ngoặc `()` ta đã tách biểu thức chính quy
thành các nhóm con  . Phần nào ra phần đó theo đúng tính chất của
đường link website như được demo ở trên.
Sử dụng | trong biễu diễn biểu thức chính quy
Kết hợp với cặp dấu ngoặc nhọn `()` việc sử dụng ký tự | cho ta lựa
hoặc phần này hoặc phần khác của tập danh sách các phần từ liệu
kê
Ví dụ
`/gr(a|e)y/`
Với biểu thức mô tả trên dùng để mô tả một trong hai
chuổi gray hoặc grey
Chuỗi mô tả của chúng ta được cấu thành từ chuỗi ‘gr’ tiếp theo nối
với (1 trong hai ký tự a hoặc e ) và cuối cùng nối với ký tự `‘y’`
Ngoài việc lựa chọn một trong tập các ký tự dấu | còn co phép chúng
ta lựa chọn một trong những nhóm con
`((4\.[0-3])|(2\.[0-3]))`
Với chuổi biểu thức trên mô tả các
chuổi 4.1, 4.1, 4.2, 4.3 hoặc 2.0, 2.1, 2.2, 2.3
Kết luận
Phần kiến thức này rất hay đúng không các bạn  . Với hai quy tắc này
chúng ta có thể tạo nên các biểu thức mô ta phức tạp mà nhìn nó rất
rõ ràng dễ quản lý
---
### Bài 6: Các ký tự viết tắt trong biểu thức chính
quy
Dưới đây là danh sách các quy tắt viết tắt của biểu thức chính quy
mà phải nắm để nâng cao tốc độ làm việc  . Mỗi quy tắc có phần ký tự
và mô tả kèm ví dụ của quy tắt đó
Cách viết Mô tả
> `/d` Ðại diện cho bất kỳ ký tự `[0-9]`
> `/D` Ðại diện cho các ký tự không nằm trong `[0-9]`
> `/s` Ðại diện bất kỳ ký tự trắng
> `/S` Tập không chứa bất kỳ ký tự trắng
> `/w` Ðại diện cho bất kỳ các ký tự 
> `[A-Z], [a-z], [0-9]`
> `/W` Ðại diện bất kỳ các ký tự không thuộc dãy ký tự
>  `[A-Z], [a-z], [0-9]`
---
### Bài 7: Kiểm tra địa chỉ Email trong PHP bằng
biểu thức chính quy
Như đã giới thiệu ở trên, sau đây là cách chúng ta kiểm tra xem
chuỗi người dùng đúng đinh dạng email không?
> Bước 1
> Xây dựng biểu thức chính quy của Email
> Email chúng ta có đặc điểm sau:
> – Chứa các ký tự từ A đến Z, a đến z
> – Các ký tự số
> – Ký tự gạch dưới
> – Ký tự @
> – Các ký tự trước @ có 6-32 ký tự
> – Chuổi ký ký tự sau @ chia thành hai phần của domain mỗi phần có
> 2-12 ký tự
> Ta có chuổi biểu thức chính quy theo yêu cầu trên
> `^[A-Za-z0-9_.]{6,32}@([a-zA-Z0-9]{2,12})(.[a-zA-Z]{2,12})+$`
> Bước 2
> Kiểm tra bằng hàm preg_match()
> <?php
> $partten = "/^[A-Za-z0-9_.]{6,32}@([a-zA-Z0-9]{2,12})(.[a-zA-Z]
> {2,12})+$/";
> $subject = "phancuong.qt@gmail.com";
> if(!preg_match($partten ,$subject, $matchs))
> echo "Mail bạn vừa nhập không đúng định dạng ";
> ?>
Kết luận
==🟡Với chuổi chúng ta vừa phân tích là định dạng email phổ biến được phân tích và xây dựng lên từ biểu thức chính quy, bạn có thể sử dụng nó vào việc Validation FROM để chuẩn hóa dữ liệu trong dự án của mình.==
---
### Bài 8: Kiểm tra định dạng Username trong
PHP bằng biểu thức chính quy
Tên đăng nhập trong website cũng rất quan trọng, để yêu cầu người
dùng đăng ký tài khoản trên website với một định dạng mẫu cho
trước tránh trường hợp bị lổ hỗng bị hacker tấn tông  .
Xây dựng biểu thức chính quy cho (Tên đăng nhập)Username
Bước 1: Xây dựng biểu thức chính quy cho Username
Cấu trúc của Username
Chứa các ký tự A đến Z, a đến z, 0-9 dấu   . và dấu gạch dưới
Ðộ dài 6 đến 32 ký tự
Ta có biểu thức sau
/^[A-Za-z0-9_.]{6,32}$/
Bước 2: Kiểm tra chuỗi cho trước với biểu thức chính quy bằng
php
Chúng ta sử dụng hàm preg_match() để kiểm tra
<?php
$partten = "/^[A-Za-z0-9_\.]{6,32}$/";
$subject = "hocweb123_hello";
if(!preg_match($partten ,$subject, $matchs))
echo "Username bạn vừa nhập không đúng định dạng ";
?>
Kết luận
Thế là ta đã có được cách kiểm tra Username trong PHP với biểu
thức chính quy ngon lành rồi :)  . Các bạn cố gắng đọc và nắm dần
từng bước làm việc nhé  .
Ở phần tiếp theo chúng ta qua tạo chuổi mô tả cho mật khẩu trong
biểu thức chính quy
---
### Bài 9: Kiểm tra định dạng Mật khẩu trong PHP
bằng biểu thức chính quy
Mỗi chúng ta chắc ai cũng đã từng trải nghiệm việc đăng ký tài
khoản qua các hệ thống khác nhau như
> Google
> Facebook
> Yahoo
> Twitter
> Skype
> Zalo
> -… 
     và rất nhiều hệ thống khác Những hệ thống trên là những hệ thống lớn việc bảo mật hệ thống là vấn đề luôn được nghiên cứu kỷ , nếu bảo mật không tốt thì thông tin khách hàng bị lộ kéo theo hàng hoạt rắc rối về thông tin riêng tư, tài chính…bao nhiêu việc đau đầu kiện tụng đều có thể xãy ra. Trong hệ thống website thương mai điện tử ở Việt nam cũng vậy cũng rất cần phải được bảo mật tốt để hoạt động mua bán được diễn ra suôn sẻ Có một điểm chung tất cả các hệ thống này đều xây dựng riêng cho mình những quy tắc đặt mật khẩu mà họ cho là bảo mật nhất có thể Ví dụ mật khẩu bao gồm Cả ký tự chử cái hoa, thường, chử số, ký tự đặc biệt, dấu chấm Bắt đầu với ký tự in hoa Có từ 6 đến 32 ký tự Vậy sau đây chúng ta cùng nhau nghiên cứu việc sử dụng biểu thức chính quy như thế nào
> Bước 1: Xây dựng biểu thức chính quy cho mật khẩu
> Như một số yêu cầu về mật khẩu ở trên ta có biểu thức chính quy sau
> `^([A-Z]){1}([\w_.!@#$%^&*()]+){5,31}$`
> Trong đó chuổi biểu thức chính quy chia thành 2 nhóm
> * Nhóm 1: Biễu diễn ký tự đầu tiên viết hoa
> `([A-Z]){1}`
> Ở nhóm này ta thấy tập ký tự mô tả của ta từ A-Z đây chính là các chử cái in hoa và theo yêu cầu của đầu đề thì nhóm này có 1 phần tử
> * Nhóm 2: Biểu diễn các ký tự tiếp theo là các chử cái, chử số và ký tự đặc biệt
> `([\w_-.!@#$%^&*()]+){5,31}`
> Ở nhóm này ta sử dụng viết tắt trong biểu thức chính quy \w biểu diễn tập các chử cái và chữ số
> Ngoài ra, để biểu diễn các ký tự đặc biệt ta cần thêm dấu \ vào trước dãy ký tự đặc biệt
> `!@#$%^&*()`
> Và như phân tích ở trên thì phần còn lại của chuổi mô tả mật khẩu còn 5-31 ký tự
> Bước 2: Kiểm tra định dạng mât khẩu bằng preg_match trong
> `php`
> `&lt;?php`
> `$partten = "/^([A-Z]){1}([\w_\.!@#$%^&amp;*()]+){5,31}$/";`
> `$subject = "Cuongsb$";`
> `if(!preg_match($partten ,$subject, $matchs))`
> `echo "Mật khẩu bạn vừa nhập không đúng định dạng";?>`

==🟡Kết luận: Vừa rồi chúng ta đã áp dụng biểu thức chính quy để xây dựng chuỗi mô tả cho Mật khẩu. Phần này rất cần thiết và bạn có thể thay đổi nó theo yêu cầu hệ thống của mình để làm cho hệ thống đạt điểm bảo mật thông tin cho thành viên tốt hơn. P\/s: Nội dung này được hướng dẫn sử dụng vào thực tế tại Php Master – Xây dựng website bán hàng tại unitop.vn . Tôi nghĩ bạn nên xem để hoàn thiện kỹ năng tạo website của mình  .Có bất kỳ câu hỏi nào, bạn để lại ở comment, tôi sẽ dành thời gian hỗ trợ bạn!==

---
---
                                    ==`#thank for waching`==
 ---