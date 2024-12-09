# Chapter 1 - Linux OS
- Linux là một tập hợp các chương trình và tiện ích được gắn kết với nhau bằng bash shell.
- Shell quản lý các tệp và dữ liệu.
- Shell quản lý mạng, bộ nhớ và các tài nguyên khác.
  ![image](https://github.com/user-attachments/assets/f6823d3f-5ee6-44a7-aae9-8b735d1dcd1d)
### shell
- shell là một chương trình máy tính của một hệ điều hành. Shell chấp nhận các lệnh mà con người có thể đọc được và dịch chúng thành thứ mà kernal có thể đọc và xử lý.
- Shell không phải là một phần của nhân hệ thống, nhưng sử dụng kernel để thực thi chương trình, tạo tệp, v.v.
- Một số shell có sẵn cho Linux bao gồm:
   + BASH (Bourne-Again SHell) - Shell phổ biến nhất trong Linux. Đây là mã nguồn mở.
   + CSH (C SHell) - Cú pháp và cách sử dụng của C shell rất giống với ngôn ngữ lập trình C.
   + KSH (Korn SHell) - Được David Korn tại AT & T Bell Labs tạo ra. Korn Shell cũng là cơ sở cho các thông số kỹ thuật tiêu chuẩn của POSIX Shell.
   + TCSH - Đây là phiên bản nâng cao nhưng hoàn toàn tương thích của Berkeley UNIX C shell (CSH).
- một số tổ hợp phím trong shell
   + CTRL + L: Xóa màn hình.
   + CTRL + W: Xóa từ bắt đầu từ con trỏ.
   + CTRL + U: Xóa dòng tức là Xóa tất cả các từ khỏi dòng lệnh.
   + Các phím mũi tên Lên và Xuống: Gọi lại lệnh (xem lịch sử lệnh).
   + Tab: Tự động hoàn thành tệp, thư mục, tên lệnh và nhiều hơn nữa.
   + CTRL + R: Tìm kiếm qua các lệnh đã sử dụng trước đó (xem lịch sử lệnh)
   + CTRL + C: Hủy các lệnh đang chạy.
   + CTRL + T: Hoán đổi hai ký tự cuối cùng trước con trỏ.
   + ESC + T: Hoán đổi hai từ cuối cùng trước con trỏ.
   + CTRL + H: Xóa chữ cái bắt đầu từ con trỏ.
### shell script
- lưu chữ một chuỗi lệnh vào tệp văn bản và yêu cầu shell thực thi tệp văn bản thay vì nhập lệnh, thì đó được gọi là shell program hoặc shell script
- **shell script bao gồm:**
   + Shell keywords such as if..else, do..while.
   + Shell commands such as pwd, test, echo, continue, type.
   + Linux binary commands such as w, who, free etc..
   + Text processing - công cụ và lệnh được sử dụng để thao tác, chỉnh sửa, phân tích, và xử lý dữ liệu văn bản trong hệ thống Linux hoặc Unix
   + Functions -  là các khối mã (code block) được đặt tên và có thể tái sử dụng nhiều lần trong cùng một script. Chúng giúp tổ chức code tốt hơn và tránh lặp lại các đoạn mã.
   + Control flow - các câu lệnh như if..then..else hoặc vòng lặp shell để thực hiện các hành động lặp lại.
- tạo sao nên sử dụng shell scripting
    + Shell script có thể lấy dữ liệu đầu vào từ người dùng hoặc tệp và xuất chúng ra màn hình.
    + Bất cứ khi nào bạn thấy mình thực hiện cùng một tác vụ nhiều lần, bạn nên sử dụng shell scripting, tức là tự động hóa tác vụ lặp đi lặp lại.
    + Tạo các công cụ/tiện ích mạnh mẽ của riêng bạn.
    + Tự động hóa lệnh nhập hoặc lệnh.
    + Tùy chỉnh các tác vụ quản trị.
    + Tạo các ứng dụng đơn giản.
    + Vì các tập lệnh được kiểm tra kỹ lưỡng nên khả năng xảy ra lỗi sẽ giảm khi cấu hình dịch vụ hoặc tác vụ quản trị hệ thống như thêm người dùng mới.
- Các ví dụ thực tế về việc sử dụng shell script xem [tại đây](https://bash.cyberciti.biz/guide/Why_shell_scripting)

# Chapter2 : Getting Started With Shell Programming
- bash là shell. Viết tắt của Bourne-Again SHell
- Dấu nhắc lệnh :
    + $ : người dùng thường
    + #: người dùng root
### bash shell có 2 loại
- Internal commands (builtins) : lệnh có sẵn trong shell bao gồm
    + Lệnh điều khiển shell : cd , pwd,export...
    + lệnh kiểm soát luồng điều khiển : if, else, elif, while,for
    + Lệnh quản lý biến
    + Lệnh quản lý tệp và thư mục : umask,pushd
    + Lệnh xử lý job và tiến trình : kill,...
    + Lệnh debugging và thông tin
- External commands: Lệnh bên ngoài - các tệp nhị phân riêng biệt được lưu trữ trong các thư mục /sbin, /usr/sbin, /usr/bin, /bin hoặc /usr/local/bin.
-  _có những lệnh sẽ có ở cả 2 loại nhưng hệ thống sẽ ưu tiên dùng trong builtins, khi cần các tùy chọn nâng cao sẽ sử dụng đến external_

### shell login
- khi bạn đăng nhập vào hệ thống các tệp shell script bắt đầu thực thi để thiết lập môi trường và cấu hình cho người dùng
- |Tệp cấu hình|Mô tả|
  |:-------|:------------------------------------:|
  |/etc/profile|	Được thực thi cho tất cả người dùng khi đăng nhập vào hệ thống.|
  |~/.bash_profile|	Cấu hình cho shell khi người dùng đăng nhập.|
  |~/.profile|	Dùng cho các shell login nếu không có ~/.bash_profile.|
  |/etc/bash.bashrc|	Cấu hình cho tất cả người dùng khi mở shell non-login (ví dụ: terminal).|
  |~/.bashrc|	Cấu hình cho shell non-login (dùng khi mở terminal).|
- Login shell (khi đăng nhập vào hệ thống):
  + /etc/profile, ~/.bash_profile, ~/.profile sẽ được thực thi.
- Non-login shell (khi mở terminal trong môi trường đồ họa):
  + ~/.bashrc sẽ được thực thi.
### shell script Hello, World! Tutorial
- tạo tệp sh
```
vi hello.sh
```
```
#!/bin/bash
echo "Hello, World!" 
echo "Knowledge is power."
```
- chưa có quyền thực thi
- cấp quyền thực thi
```
chmod +x hello.sh
./hello.sh
```
- output :
```
Hello, World!
Knowledge is power.
```
- hầu hết các file sh đều bắt đầu bằng : #!/bin/bash or #!/usr/bin/env bash
- Cú pháp #! : được sử dụng trong các tập lệnh để chỉ ra trình thông dịch để thực thi trong hệ điều hành UNIX/Linux
- theo sau là đường dẫn đầy đủ đến trình thông dịch như /bin/bash hoặc /usr/bin/env bash
- Nó được gọi là shebang hoặc dòng "bang".
- chú thích được đặt sau dấu #
- dùng lệnh chmod để thay đổi quyền thực thi cho file script
   + chmod +x script.sh
   + chmod 0755 script.sh
   + chmod 0700 script.sh
- mọi script được thực thi bằng cú pháp sau :
```
chmod +x script.sh
./script.sh
```

# Chapter 3 The Shell Variables and Environment
- biến (variables) là các đối tượng chứa giá trị mà bạn có thể sử dụng trong các lệnh
- Biến trong shell giúp lưu trữ và thao tác với dữ liệu như chuỗi, số, tên tệp, v.v.
- sử dụng echo để hiện thị giá trị biến :
```
echo "$PATH"
echo "$PS1"
echo "${HOME}"
echo "${HOME}work"
```
- Bạn phải sử dụng $ theo sau là tên biến để in nội dung của biến.

### Gán giá trị cho các biến shell
- cú pháp
```
varName=someValue
```
- gọi biến
```
echo "$varName"
```
ví dụ : 
```
input="/home/sales/data.txt"
echo "Input file $input"
```
```
BACKUP="/nas05"
echo "Backing up files to $BACKUP/$USERNAME"
```
```
echo "MySHELL=>${SHELL}Code<="
```
- ví dụ về **_biến mặc định_** tham số truyền vào :
- cú pháp : ${var:=defaultValue}
```
die(){
  local error=${1:=Undefined error} hoặc local error=${1:-Undefined error}
  echo "$0: $LINENO $error" 
}
die "File not found"
die
```
- :-: Chỉ sử dụng giá trị mặc định nếu tham số không được cung cấp hoặc trống.
- :=: Gán giá trị mặc định cho biến nếu tham số không được cung cấp hoặc trống, và biến sẽ có giá trị đó trong suốt phần còn lại của quá trình thực thi.
- trong ví dụ trên có biến error và truyền tham số thứ nhất

- **quy tắc đặt tên biến**
- Tên biến phải bắt đầu bằng chữ cái (a-z, A-Z) hoặc dấu gạch dưới (_), không thể bắt đầu bằng số.
- Tên biến có thể chứa chữ cái, số và dấu gạch dưới.
- Tên biến không được chứa dấu cách.
- Tránh sử dụng các từ khóa đặc biệt và tên biến hệ thống.
- Tên biến phân biệt chữ hoa và chữ thường.
- Các tên biến có thể dài nhưng nên ngắn gọn và dễ hiểu.
- Không sử dụng ký tự đặc biệt như dấu chấm, dấu gạch ngang trong tên biến.

- **unset**
- Sử dụng lệnh unset để xóa các biến trong khi thực thi chương trình. Nó có thể xóa cả hàm và biến shell.
- ví dụ :
```
vech=Bus
echo "$vech"
unset vech
echo "$vech"
```
- unset funtion
- ví dụ :
```
function hello(){ echo "Hello $USER. Today is $(date)."; }
unset -f hello
```

**cho phép người dùng nhập dữ liệu đầu vào**
- cấu trúc :
```
read -p "Prompt" variable1 variable2 variableN
```
- ví dụ :
```
read -r -p "Are you sure (Y/n)? " answer
echo "You typed: $answer"
```
- **các phép tính số học**
- cấu trúc : $((expression))
    + $(( n1+n2 ))
    + $(( n1/n2 ))
    + $(( n1-n2 ))
- ví dụ : add.sh
```
#!/bin/bash
x=5
y=10
ans=$(( x + y ))
echo "$x + $y = $ans"
```
```
chmod +x add.sh
./add.sh
```
- nhập đầu vào
```
#!/bin/bash
read -p "Enter two numbers : " x y
ans=$(( x + y ))
echo "$x + $y = $ans"
```
**Tạo một biến số nguyên**
- cấu trúc :
```
declare -i y=10
echo "$y"
```
ví dụ : 
```
#!/bin/bash
# set x,y and z to an integer data type
declare -i x=10
declare -i y=10
declare -i z=0
z=$(( x + y ))
echo "$x + $y = $z"
```
**Tạo biến hằng số**
-  lệnh readonly hoặc lệnh declare
-  cấu trúc :
```
readonly var
readonly varName=value
hoặc
declare -r var
declare -r varName=value
```
**Kiểm tra sự tồn tại của biến Bash**
- Nếu biến không được định nghĩa, bạn có thể dừng thực thi tập lệnh Bash bằng cú pháp đơn giản sau:
- cấu trúc :
```
${varName?Error varName is not defined}
${varName:?Error varName is not defined or is empty}
```
- ví dụ : 
```
#!/bin/bash
# varcheck.sh: Variable sanity check with :? 
path=${1:?Error command line argument not passed}

echo "Backup path is $path."
echo "I'm done if \$path is set."
```
- nếu ko nhập tham số đầu vào sẽ ko chạy lệnh echo

**tùy chỉnh biến môi trường**
- Tùy chỉnh môi trường Bash shell (customizing the Bash shell environment) liên quan đến việc sửa đổi các tệp cấu hình và thiết lập biến môi trường để điều chỉnh cách Bash hoạt động theo nhu cầu cá nhân. Điều này thường bao gồm:
  + Thiết lập biến môi trường
  + Tạo alias cho các lệnh
  + Định nghĩa các hàm shell
  + Thay đổi Prompt (PS1)
  + Tự động thực thi lệnh khi shell khởi động


