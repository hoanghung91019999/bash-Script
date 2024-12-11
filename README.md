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
# Thực thi điều kiện (Ra quyết định)\
- In shell:
  + 0 là giá false.
  + 1 or non-zero là giá trị true.
- Lệnh "test" được sử dụng để kiểm tra các loại tệp và so sánh các giá trị. Test được sử dụng trong thực thi có điều kiện. Nó được sử dụng cho:
   + So sánh thuộc tính tệp
   + Thực hiện so sánh chuỗi.
   + So sánh số học cơ bản.
- ví dụ :
```
test -f /etc/resolv.conf && echo "File /etc/resolv.conf found." || echo "File /etc/resolv.conf not found."
- f : option tìm file
```
- nếu lệnh test tìm thấy file trả về File /etc/resolv.conf found
- nếu lệnh test không tìm thấy file trả về File /etc/resolv.conf not found
- **if cấu trúc thực thi mã dựa trên điều kiện**
- cấu trúc :
```
if condition
then
     command1 
     command2
     ...
     commandN 
fi
- condition là điều kiện thực thi
```
- hoặc
```
if test var == value
then
     command1 
     command2
     ...
     commandN 
fi
```
- hoặc
```
if test -f /file/exists
then
     command1 
     command2
     ...
     commandN 
fi
```
- hoặc
```
 if [ condition ]
then
      command1
      command2
      ....
      ..
fi
```
- ví dụ
```
read -p "Enter a password" pass
if test "$pass" == "jerry"
then
     echo "Password verified."
fi

#!/bin/bash
read -p "Enter # 5 : " number
if test $number == 5 
then
    echo "Thanks for entering # 5"
fi
if test $number != 5 
then
    echo "I told you to enter # 5. Please try again."
fi
```
- if..else..fi cho phép đưa ra lựa chọn dựa trên sự thành công hay thất bại của lệnh.
- cấu trúc :
```
 if command
           then
                       command executed successfully
                       execute all commands up to else statement
                       or to fi if there is no else statement

           else
                       command failed so
                       execute all commands up to fi
           fi
```
```
 if test var -eq val
           then
                       command executed successfully
                       execute all commands up to else statement
                       or to fi if there is no else statement

           else
                       if command failed then
                       execute all commands up to fi
           fi
```
```
 if [ condition ]
           then
                       if given condition true
                       execute all commands up to else statement
                       or to fi if there is no else statement

           else
                       if given condition false 
                       execute all commands up to fi
           fi
```
- ví dụ
```
##!/bin/bash
read -p "Enter a password" pass
if test "$pass" = "jerry"
then
     echo "Password verified."
else
     echo "Access denied."	
fi
```
```
#!/bin/bash
# Purpose: Detecting Hardware Errors
# Author: Vivek Gite <vivek@nixcraft.com>
# Note : The script must run as a cron-job.
# Last updated on : 28-Aug-2007
# -----------------------------------------------

# Store path to commands
LOGGER=/usr/bin/logger
FILE=/var/log/mcelog

# Store email settings
AEMAIL="vivek@nixcraft.net.in"
ASUB="H/W Error - $(hostname)"
AMESS="Warning - Hardware errors found on $(hostname) @ $(date). See log file for the details /var/log/mcelog."
OK_MESS="OK: NO Hardware Error Found."
WARN_MESS="ERROR: Hardware Error Found."


# Check if $FILE exists or not
if test ! -f "$FILE" 
then   
	echo "Error - $FILE not found or mcelog is not configured for 64 bit Linux systems."
	exit 1
fi

# okay search for errors in file
error_log=$(grep -c -i "hardware error" $FILE)

# error found or not?
if [ $error_log -gt 0 ]
then    # yes error(s) found, let send an email
	echo "$AMESS" | email -s "$ASUB" $AEMAIL
else    # naa, everything looks okay
	echo "$OK_MESS"
fi
```
- **if lồng nhau**
- cấu trúc :
```
	if condition
	then
		if condition
		then
			.....
			..
			do this
		else
			....
			..
			do this
		fi
	else
		...
		.....
		do this
	fi
```
- if..elif..else..fi cho phép tập lệnh có nhiều khả năng và điều kiện khác nhau
- ví dụ :
```
read -p "Enter a number : " n
if [ $n -gt 0 ]; then
  echo "$n is a positive."
elif [ $n -lt 0 ]
then
  echo "$n is a negative."
elif [ $n -eq 0 ]
then
  echo "$n is zero number."
else
  echo "Oops! $n is not a number."
fi
```
- **Trạng thái thoát của một lệnh**
- Mỗi lệnh Linux trả về một trạng thái khi nó kết thúc bình thường hoặc bất thường. Bạn có thể sử dụng giá trị của trạng thái thoát trong tập lệnh shell để hiển thị thông báo lỗi hoặc thực hiện một số hành động. Ví dụ, nếu lệnh tar không thành công, nó trả về một mã lệnh yêu cầu tập lệnh shell gửi email đến sysadmin.
- Bạn có thể sử dụng biến shell đặc biệt có tên là $? để lấy trạng thái thoát của lệnh đã thực thi trước đó. Để in biến $?, hãy sử dụng lệnh echo: echo $?
- nếu echo $? trả về 0 - lệnh đúng
- nếu echo $? trả về giá trị từ 1-255-lệnh sai
- ví dụ :
```
#!/bin/bash
# set var 
PASSWD_FILE=/etc/passwd

# get user name
read -p "Enter a user name : " username

# try to locate username in in /etc/passwd
grep "^$username" $PASSWD_FILE > /dev/null

# store exit status of grep
# if found grep will return 0 exit stauts
# if not found, grep will return a nonzero exit stauts
status=$?

if test $status -eq 0
then
	echo "User '$username' found in $PASSWD_FILE file."
else
	echo "User '$username' not found in $PASSWD_FILE file."
fi
```
- **Thực hiện có điều kiện**
- dựa vào trạng thái thoát có thể thực hiện các câu lệnh có điều kiện
- Logic AND && - Chỉ chạy lệnh thứ hai nếu lệnh đầu tiên thành công.
- Logic OR || - Chỉ chạy lệnh thứ hai nếu lệnh đầu tiên không thành công.
- ví dụ :
```
grep "^vivek" /etc/passwd && echo "Vivek found in /etc/passwd"
tìm vivek trong /etc/passwd nếu có ( lệnh thành công Logic AND && ) in ra 
grep "^vivek" /etc/passwd || echo "User vivek not found in /etc/passwd"
tìm vivek trong /etc/passwd nếu có in thì ko in ra nếu ko có ( lệnh ko thành công Logic OR || ) mới in ra
```
- logic not (!) là toán tử boolean
- Phủ định trạng thái của lệnh
- Trong Bash, các lệnh thường trả về:
    + 0: Thành công (true).
    + Khác 0: Thất bại (false).
    + ! sẽ đổi trạng thái:
    + Nếu lệnh trả về 0, ! sẽ làm cho nó thành false.
    + Nếu lệnh trả về khác 0, ! sẽ làm cho nó thành true.
- sử dụng lệnh test bằng ngoặc
```
[ condition ] && true-command || false-command
```
- các toàn từ so sánh xem [tại đây](https://bash.cyberciti.biz/guide/Numeric_comparison)
- so sánh chuỗi
```
STRING1 = STRING2 - là 
STRING1 != STRING2 -khác
```
- các option so sánh với tệp tin và thư mục xem [tại đây](https://bash.cyberciti.biz/guide/File_attributes_comparisons)

- **Cách sử dụng tham số vị trí**
- ham số vị trí (Positional Parameters) trong Bash là các tham số hoặc đối số được truyền cho một script hoặc hàm khi nó được gọi. Chúng được tham chiếu bằng các ký hiệu đặc biệt như $1, $2, $3,... tương ứng với thứ tự của đối số.
- $@ mở rộng thành "$1" "$2" "$3" ... "$n"
- $* mở rộng thành "$1y$2y$3y...$n",
- ví dụ :
```
my_function() {
    echo "First argument: $1"
    echo "Second argument: $2"
}

my_function argA argB
$1: argA
$2: argB
```
- các tham số được thiết lập bởi shell :
- |Tham số|	Ý nghĩa|
  |:-------|---------------------------------:|
  |$0|	Tên của script hoặc chương trình đang chạy (bao gồm đường dẫn nếu có).|
  |$1, $2, ...|	Các tham số truyền cho script hoặc hàm, bắt đầu từ tham số thứ nhất.|
  |$#|	Số lượng tham số được truyền.|
  |$*|Chuỗi chứa tất cả các tham số, được ngăn cách bởi dấu cách.|
  |"$@"|	Tương tự $*, nhưng giữ nguyên dấu ngoặc kép của từng tham số nếu chúng có.|
  |$?|Mã trạng thái thoát (exit code) của lệnh hoặc script trước đó.|
  |$$|PID (Process ID) của script hoặc shell đang chạy.|
  |$!|	PID của tiến trình cuối cùng được chạy trong nền.|

- **sử dụng exit command**
- sử dụng exit command để phát hiện lỗi và chỉ định script thành công
- ví dụ
```
#!/bin/bash

LOG_FILE="/var/log/script_errors.log"

echo "Bắt đầu kiểm tra file..."

if [ ! -f "/path/to/file" ]; then
    echo "$(date) - Lỗi: File không tồn tại!" >> "$LOG_FILE"
    exit 1
fi

echo "Kiểm tra thư mục..."

if [ ! -d "/path/to/directory" ]; then
    echo "$(date) - Lỗi: Thư mục không tồn tại!" >> "$LOG_FILE"
    exit 2
fi

echo "Mọi thứ đều ổn!"
exit 0
```
- đặt các exit với mã khác 0 để nếu có sảy ra lỗi trong script sẽ biết lỗi ở đâu, nếu có lỗi ở đâu script sẽ dừng và trả về mã lỗi exit đã set ( exit 1-255)
- và đặt exit 0 ở cuối script để thông báo script thành công mà không có lỗi

**câu lệnh case**
- Câu lệnh case trong Bash là một công cụ mạnh mẽ để thực hiện so sánh và xử lý các trường hợp khác nhau một cách hiệu quả, đặc biệt khi bạn muốn kiểm tra một biến hoặc giá trị với nhiều khả năng khác nhau. Câu lệnh này hoạt động tương tự như một chuỗi các câu lệnh if lồng nhau nhưng dễ đọc và bảo trì hơn.\
- cấu trúc :
```
case <biến hoặc biểu thức> in
    <mẫu 1>)
        # Thực hiện hành động nếu khớp với mẫu 1
        ;;
    <mẫu 2>)
        # Thực hiện hành động nếu khớp với mẫu 2
        ;;
    <mẫu 3>)
        # Thực hiện hành động nếu khớp với mẫu 3
        ;;
    *)
        # Thực hiện hành động nếu không có mẫu nào khớp (tùy chọn)
        ;;
esac
```
  + <biến hoặc biểu thức>: Biến hoặc biểu thức bạn muốn so sánh.
  + <mẫu n>: Các mẫu (pattern) mà bạn muốn so sánh với giá trị của biến hoặc biểu thức.
  + ;;: Dùng để kết thúc mỗi khối mã lệnh của mỗi trường hợp.
  + *: Là ký tự đại diện cho tất cả các trường hợp không khớp với mẫu nào, tương tự như "else" trong câu lệnh if.
- ví dụ :
```
#!/bin/bash

echo "Nhập một số từ 1 đến 3:"
read num

case $num in
  1)
    echo "Bạn đã chọn số 1"
    ;;
  2)
    echo "Bạn đã chọn số 2"
    ;;
  3)
    echo "Bạn đã chọn số 3"
    ;;
  *)
    echo "Lựa chọn không hợp lệ"
    ;;
esac
```
