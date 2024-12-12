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
# chapter 5 : vòng lặp Bash loops
- Bash loops (vòng lặp trong Bash) cho phép bạn thực hiện một chuỗi lệnh nhiều lần. Có ba loại vòng lặp chính trong Bash: for, while, và until. Mỗi loại vòng lặp có cách sử dụng và mục đích khác nhau, giúp bạn linh hoạt trong việc xử lý các tác vụ lập trình.

###  Vòng lặp for
- Vòng lặp for trong Bash được sử dụng để lặp qua một tập hợp giá trị hoặc một phạm vi. Bạn có thể sử dụng for để lặp qua các phần tử trong một danh sách hoặc lặp qua một phạm vi số.
- lặp giá trị sau đó truyền vào biến rùi in ra biến
- ví dụ :
```
#!/bin/bash
n=$1
# make sure command line arguments are passed to the script
if [ $# -eq 0 ]
then
	echo "A shell script to print multiplication table."
	echo "Usage : $0 number"
	exit 1
fi

# Use for loop
for i in {1..10} 
do
	echo "$n * $i = $(( $i * $n))"
done
```
- output
```
chạy script : ./multiplication.sh 13

13 * 1 = 13
13 * 2 = 26
13 * 3 = 39
13 * 4 = 52
13 * 5 = 65
13 * 6 = 78
13 * 7 = 91
13 * 8 = 104
13 * 9 = 117
13 * 10 = 130
```
- for trong for
```
#!/bin/bash
# A shell script to print each number five times.
for (( i = 1; i <= 5; i++ ))      ### Outer for loop ###
do

    for (( j = 1 ; j <= 5; j++ )) ### Inner for loop ###
    do
          echo -n "$i "
    done

  echo "" #### print the new line ###
done
```
- giải thích :
  	+ giá trị i = 1 lặp cho tới khi  i nhở hơn hoặc bằng 5 lớn hơn 5 kết thúc
  	+ mỗi lần i lặp vòng lặp for bên trong kích hoạt và lặp giá trị j tương tự giá trị i nhưng ko echo ra j mà echo ra i
  	+ j lặp 5 lần in ra i 5 lân
  	+ mỗi lần i lặp sẽ kích hoạt j lặp khi j lặp hết mới tiếp tục lặp j
- **While**
- Vòng lặp while thực thi các lệnh trong khối do khi điều kiện là đúng (true). Vòng lặp này kiểm tra điều kiện trước khi thực thi các lệnh bên trong.
- ví dụ :
```
#!/bin/bash
count=1
while [ $count -le 5 ]
do
  echo "Số là: $count"
  ((count++))  # Tăng giá trị biến count
done
```
- **Vòng lặp until**
- Vòng lặp until là ngược lại với vòng lặp while. Vòng lặp until sẽ tiếp tục thực thi các lệnh trong khối do cho đến khi điều kiện trở thành đúng (true). Vòng lặp này kiểm tra điều kiện sau mỗi lần lặp.
- ví dụ :
```
#!/bin/bash
count=1
until [ $count -gt 5 ]
do
  echo "Số là: $count"
  ((count++))  # Tăng giá trị biến count
done
```
- **Sử dụng break và continue trong vòng lặp**
- break: Dùng để thoát khỏi vòng lặp hiện tại ngay lập tức.
- continue: Dùng để bỏ qua phần còn lại của vòng lặp và tiếp tục với lần lặp tiếp theo.
- ví dụ :
```
#!/bin/bash
for i in {1..10}
do
  if [ $i -eq 5 ]
  then
    echo "Đã gặp số 5, thoát khỏi vòng lặp"
    break
  fi
  echo "Số là: $i"
done
```
- **vòng lặp select**
- Trong Bash, vòng lặp select là một công cụ rất hữu ích để tạo các menu cho người dùng lựa chọn từ một danh sách các tùy chọn. Nó cho phép người dùng chọn một giá trị từ một tập hợp các tùy chọn đã cho, sau đó thực hiện hành động tương ứng với sự lựa chọn đó.
- cấu trúc :
```
select var in list
do
    command(s)
done
```
-  ví dụ
```
#!/bin/bash

PS3="Please select an option: "   # Tùy chỉnh thông báo hướng dẫn cho người dùng.

select option in "Option 1" "Option 2" "Option 3" "Exit"
do
    case $option in
        "Option 1")
            echo "You selected Option 1"
            ;;
        "Option 2")
            echo "You selected Option 2"
            ;;
        "Option 3")
            echo "You selected Option 3"
            ;;
        "Exit")
            echo "Exiting the script"
            break  # Dừng vòng lặp
            ;;
        *)
            echo "Invalid option, please select again."
            ;;
    esac
done
```
# chapter 6 Shell Redirection
- Shell Redirection là một tính năng mạnh mẽ trong các shell của hệ điều hành Unix/Linux. Nó cho phép bạn kiểm soát cách dữ liệu được gửi vào hoặc ra khỏi chương trình, file, hoặc thiết bị. Shell redirection đặc biệt hữu ích khi bạn muốn lưu đầu ra, xử lý dữ liệu, hoặc tương tác với file mà không cần giao tiếp trực tiếp qua giao diện.
   + 0 - Đầu vào - Bàn phím (stdin)
   + 1 - Đầu ra - Màn hình (stdout)
   + 2 - Lỗi - Màn hình (stderr)
- Ba số trên là số POSIX chuẩn và còn được gọi là mô tả tệp (FD). Mỗi lệnh Linux ít nhất mở các luồng trên để giao tiếp với người dùng hoặc các chương trình hệ thống khác.
- **input**
-  cấu trúc :
```
 command < filename
```
- Còn được gọi là stdin.
- Đầu vào chuẩn mặc định là bàn phím.
- < là ký hiệu chuyển hướng đầu vào và cú pháp là
![image](https://github.com/user-attachments/assets/6e34857b-ad46-4372-9773-be5564c74af4)

- **output**
- Ghi dữ liệu đầu ra của một chương trình vào file thay vì hiển thị trên màn hình (stdout).
- cấu trúc
```
command > output.file.name
- ghi đè
echo "Hello Again" >> output.txt
- ghi thêm vào cuối dòng
```
- **error**
- Chuyển đầu ra lỗi (stderr) vào một file hoặc thiết bị.
- cấu trúc :
```
command 2> errors.txt
command 2>> errors.txt
```

- **tạo file trống**
- cấu trúc :
```
> filename
```
- **/dev/null loại bỏ đầu ra không mong muốn**
- /dev/null là một thiết bị đặc biệt trong hệ điều hành Unix/Linux. Nó hoạt động như một "hố đen", nơi mọi dữ liệu gửi vào đều bị loại bỏ mà không để lại dấu vết. Điều này rất hữu ích khi bạn muốn loại bỏ đầu ra không mong muốn từ các lệnh hoặc chương trình.
- cấu trúc :
```
command > /dev/null
```
- Loại bỏ lỗi chuẩn (Standard Error - stderr)
```
command 2> /dev/null
```
- Loại bỏ cả đầu ra chuẩn và lỗi chuẩn
```
command > /dev/null 2>&1
hoặc
command &> /dev/null
```
- **here document**
- Here Document (Heredoc) là một phương pháp trong shell scripting của Unix/Linux để truyền nhiều dòng văn bản làm đầu vào cho một lệnh hoặc chương trình. Đây là cách thay thế hiệu quả cho việc nhập liệu trực tiếp hoặc sử dụng file tạm.
- chủ yếu dùng EOF
- cấu trúc :
```
command <<EOF
nội_dung
EOF
```
- ví dụ
```
cat <<EOF > config.conf
[server]
address=127.0.0.1
port=8080
EOF
```
 **Here Strings**
- Here Strings là một tính năng trong shell (ví dụ: Bash) dùng để cung cấp một chuỗi văn bản ngắn gọn làm đầu vào cho một lệnh. Đây là một cách thay thế ngắn gọn hơn so với Here Document khi bạn chỉ cần truyền một dòng văn bản.
- cấu trúc :
```
command <<< "chuỗi_văn_bản"
 vd : cat <<< "Hello, World!"
 - đọc dữ liệu đầu vào và in ra màn hình
```
- **Bạn có thể gán mô tả tệp cho tệp đầu ra bằng cú pháp sau:**
```
exec fd> output.txt
where, fd >= 3
```
- ví dụ
```
#!/bin/bash
# Let us assign the file descriptor to file for output
# fd # 3 is output file 
exec 3> /tmp/output.txt 

# Executes echo commands and  # Send output to 
# the file descriptor (fd) # 3 i.e. write output to /tmp/output.txt
echo "This is a test" >&3

# Write date command output to fd # 3
date >&3

# Close fd # 3
exec 3<&-
```
- **Bash hỗ trợ cú pháp sau để mở tệp để đọc và ghi vào mô tả tệp:**
- cấu trúc
```
exec fd<>fileName
```
- giải thích
   + exec fd< filename : mở file ở chế độ đọc
   + exec fd> filename : mở file ở chế độ ghi
   + exec fd<>fileName : mở file ở chế độ đọc và ghi
- ví dụ
```
#!/bin/bash
FILENAME="/tmp/out.txt"
# Opening file descriptors # 3 for reading and writing
# i.e. /tmp/out.txt
exec 3<>$FILENAME

# Write to file
echo "Today is $(date)" >&3
echo "Fear is the path to the dark side. Fear leads to anger. " >&3
echo "Anger leads to hate. Hate leads to suffering." >&3
echo "--- Yoda" >&3

# close fd # 3
exec 3>&-
```
- **read -u**
- Sử dụng read -u cho phép bạn đọc dữ liệu từ một file descriptor (FD) tùy chỉnh thay vì từ stdin. Điều này rất hữu ích khi bạn cần đọc từ các file hoặc các luồng dữ liệu khác ngoài bàn phím hoặc đầu vào mặc định.
- cấu trúc :
```
read -u fd var1 var2 ... varN
```
- ví dụ
```
#!/bin/bash
# mở file gán fd là 3 và ở chế độ đọc
exec 3< /etc/resolv.conf

# mở file gán fd là 4 và ở chế độ ghi
exec 4> /tmp/output.txt
 
# lấy dữ liệu từ file 3 và gán lần lượt vào biến a b
read -u 3 a b

# Display data on screen
echo "Data read from fd # 3:"
echo $a $b

# Write the same data to fd # 4 i.e. our output file
echo "Writing data read from fd #3 to fd#4 ... "
echo  "Field #1 - $a " >&4
echo  "Field #2 - $b " >&4

# Close fd # 3 and # 4
exec 3<&-
exec 4<&-
```

# chappter 7 Pipes and Filters
- Trong lập trình shell, pipes và filters là hai khái niệm cơ bản giúp kết nối các lệnh với nhau, cho phép bạn xử lý dữ liệu theo chuỗi mà không cần phải lưu trữ dữ liệu tạm thời vào file. Đây là cách tiếp cận liên kết lệnh (command chaining) mạnh mẽ trong môi trường shell.
- **Pipes**
- Pipes trong shell được sử dụng để chuyển dữ liệu từ lệnh này sang lệnh khác. Dữ liệu được chuyển qua pipe giữa các lệnh dưới dạng dòng (stream) mà không cần phải lưu vào tệp.
- cú pháp ::
```
command1 | command2
- command1: Lệnh đầu tiên, xuất ra dữ liệu (stdout).
- command2: Lệnh thứ hai, nhận dữ liệu từ stdin của lệnh đầu tiên.
```
- **Filters**
- Filters là các lệnh hoặc chương trình trong shell mà có chức năng xử lý, chuyển đổi hoặc lọc dữ liệu đầu vào và xuất ra kết quả đã được xử lý. Filters thường làm việc với dữ liệu từ stdin và gửi kết quả ra stdout. Các lệnh phổ biến dùng làm filters bao gồm grep, awk, sed, sort, cut, v.v.
- các lệnh phổ biến dùng làm Filters
  + grep: Tìm kiếm chuỗi trong dữ liệu.
  + awk: Xử lý và phân tích dữ liệu văn bản theo cột.
  + sed: Thực hiện thay thế hoặc chỉnh sửa văn bản.
  + sort: Sắp xếp dữ liệu.
  + cut: Cắt bỏ hoặc lựa chọn cột từ dữ liệu.

- **Sử dụng Pipes với Multiple Commands**
- Bạn có thể kết hợp nhiều lệnh với nhau qua các pipe để tạo thành một chuỗi xử lý dữ liệu phức tạp hơn.
- ví dụ :
```
cat file.txt | grep "pattern" | sort | uniq
```
- Pipe cho stderr (2>&1): Dùng để kết hợp đầu ra lỗi (stderr) với đầu ra chuẩn (stdout).
	+ Ví dụ: command 2>&1 | another_command
```
ls /nonexistent_directory 2>&1 | grep "No such file or directory"
2>&1: Chuyển hướng stderr (thông báo lỗi) sang stdout, để thông báo lỗi này có thể được đưa vào pipe
| grep "No such file or directory": Dùng grep để lọc và chỉ in ra thông báo lỗi chứa chuỗi "No such file or directory"
```
- Pipe với process substitution (<(command) hoặc >(command)): Cho phép truyền dữ liệu từ một lệnh như một tệp tạm thời vào lệnh khác.
  	+ <(command): Cho phép bạn chuyển đầu ra của một lệnh thành một "tệp" ảo mà các lệnh khác có thể đọc.
	+ >(command): Cho phép bạn chuyển đầu ra của một lệnh vào một "tệp" ảo mà các lệnh khác có thể ghi vào.
	+ Ví dụ: diff <(command1) <(command2)
```
diff <(echo "apple") <(echo "orange")
<(echo "apple"): Tạo một tệp ảo chứa đầu ra của lệnh echo "apple".
<(echo "orange"): Tạo một tệp ảo chứa đầu ra của lệnh echo "orange".
diff: So sánh hai tệp ảo này và in ra sự khác biệt.
```
- ví dụ trong thực tế :
```

Tìm kiếm các dòng lỗi trong file log
cat /var/log/syslog | grep "error" | sort | uniq
```


