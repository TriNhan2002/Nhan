**ping/hping3 ping đến domain vietnix.vn sau đó giải thích**

**ttl= là gì**

ttl=53

**time= là gì**

time=5.25

**ssh command**

**Dùng password**

ssh username@ip_address

**Dùng key**

ssh -i /path-to-ssh-key/ssh-key username@ip-server

**Dùng port custom**

+ /etc/ssh/sshd_config
+ Port port_custom
+ systemctl restart sshd
+ exit
+ ssh -p port_custom -l root ip_address



**scp command**

**scp 1 file**

scp file.txt user@host:/folder/folder1

**scp 1 folder**

scp -r folder2 user@host:/folder/folder1



**rsync command**

**rsync file**

rsync -zvh backup.tar /tmp/backups/

**rsync folder**

rsync -avzh /folder1 /folder2/

**rsync increamental**

rsync -av --progress /path/to/source /path/to/destination

**cat command**

**cat nội dung 1 file**

cat file.txt

**cat dòng thứ <n> trong file**

cat -n 5 file.txt

**cat nhiều dòng vào 1 file bằng EOF**

cat << EOF > file.txt



**echo command**

**Dùng echo để chèn thêm 1 dòng vào cuối file**

echo "Dòng cần thêm." >> file.txt

**Dùng echo để overwirte nội dung của file**

echo "Dòng cần thêm." > /folder/file.txt



**tail/head command**

tail -n 5 file.txt

tail -n 5 file.txt

**tail và tailf**

tail -n 5 file.txt

tail -f file.txt



**sed command**

**Dùng sed để find and replace một string trong file**

**traceroute/tracert command**

sed -i 's/traceroute/tracert/g' file.txt

**Sau khi traceroute xong giải thích chi tiết kết quả trả về**

traceroute to example.com (ip_address_của_file.txt), 30 hops max, 60 byte packets
 1  router.local (192.168.1.1)  0.123 ms  0.045 ms  0.034 ms
 2  isp-gateway (10.1.1.1)  10.234 ms  10.098 ms  10.045 ms
 3  172.16.0.1 (172.16.0.1)  15.678 ms  15.123 ms  15.234 ms
 4  93.184.216.34 (93.184.216.34)  25.678 ms  25.543 ms  25.678 ms

**netstat command**

netstat [options]

**hiển thị các socket đang listen**

netstat -tuln

**don't resolve hostname**

netstat -n

**don't resolve portname**

netstat -n

**display process name/PID**

$ ps -fp [pid] 

**only show tcp socket**

netstat -tn

**only show udp socket**

netstat -un



**sort command**

sort [OPTION]... [FILE]...

**sort theo thứ tự tăng dần**

sort -n file.txt

**sort theo thứ tự giảm dần**

sort -nr file.txt

**sort theo column**

sort -k số_cột -n file.txt



**uniq command**

uniq [options] [input_file] [output_file]

**lọc ra các dòng lặp lại trong một file**

sort file.txt | uniq -d

**lọc ra các dòng lặp lại trong file và đếm số lượng các dòng lặp lại**

sort file.txt | uniq -c -d

**wc command**

wc [options] file.txt

**Đếm số dòng trong file**

wc -l file.txt

**Đếm số kí tự trong file**

wc -c file.txt

**chmod, chown, chattr command**

+ chmod [options] file.txt
+ chown [options] user:group file.txt
+ chattr [options] file.txt

**Phân quyền bằng số, phân quyền bằng chữ**

**Đổi owner user/group**

chown [options] user:group file.txt



**Set Immutable Attribute**

chattr +i file.txt

**find command**

find [source] [options]

**find các file có đuôi .log**

find folder/folder1 -name "*.log"

**find các folder có tên abc**

find folder/folder1 -name "*.log"

**find các file có tên abc**

find folder/folder1 -name "abc"

**find các file có tên abc và thực hiện phần quyền read only cho file**

find folder/folder1 -name "abc" -exec chmod 444 {} \;



**cp command**

cp [options] nguồn_đích

**cp file**

cp file.txt file1.txt

**cp folder**

cp -R folder/folder1 folder2/folder3



**mv command**

mv [options] nguồn_đích

**mv file, folder**

mv file folder/folder1

mv folder/folder3 folder1/folder2



**cut command**

cut [options] file.txt

**cut kí tự thứ <n> trong string**

echo "string" | cut -c n

**cut từ kí tự thứ <n> trở về sau**

echo "string" | cut -c n-

**cut từ kí tự thứ <n> trở về trước**

echo "string" | cut -c 1-n-1



**dig command**

dig [options] [domain] [type]

**Dùng Dig command để kiểm tra resolv record A, MX, NS**

+ dig vietnix.vn A

+ dig vietnix.vn MX

+ dig vietnix.vn NS

**Dùng Dig command để kiểm tra resolv record A, MX, NS với custom DNS**

+ dig @8.8.8.8 vietnix.vn A
+ dig @8.8.8.8 vietnix.vn MX
+ dig @8.8.8.8 vietnix.vn NS



**tar/zip/unzip command**

- **Nén/Giải nén file tar.gz - Nén/Giải nén file .zip**

  Nén file tar.gz : tar -czvf archive.tar.gz [source]

  Giải nén file tar.gz: tar -xzvf archive.tar.gz

  Nén file .zip: zip -r archive.zip [source]

  Giải nén file .zip: unzip archive.zip

**mount/umount command**

- **Add thêm một ổ cứng sdb ~ 5gb**

  lsblk

  sudo fdisk /dev/sdb

  Nhập "n" để tạo một phân vùng mới.

  Chọn "p" cho phân vùng chính.

  Chọn số phân vùng (thường là "1").

  Nhập kích thước phân vùng (5gb).

  Nhập "w" để lưu và thoát.

- **Kiểm tra được có bao nhiêu ổ cứng trên máy chủ**

  lsblk

  sudo fdisk -l

  sudo blkid

  cat /proc/partitions

  df -h

- **Mount ổ cứng vào /mnt/test**

  lsblk

  sudo mkdir -p /mnt/test

  sudo mount /dev/sdb1 /mnt/test

  df -h

- **Umount /mnt/test**

  sudo umount /mnt/test

**Symbolic Links, Hard Links command**

**Định nghĩ Sym Link**

Symbolic link (liên kết tượng trưng, hay còn gọi là symlink và soft link) là một kiểu file đặc biệt, có nhiệm vụ trỏ đến một file hay thư mục khác.

**Định nghĩ Hard Link**

Có thể hiểu như một tên bổ sung cho file hiện có. Các liên kết này liên kết hai hay nhiều tên file với nhau trong cùng một inode. Người dùng có thể tạo một hay nhiều liên kết cứng cho một file duy nhất, tuy nhiên không thể tạo cho thư mục và file trên một filesystem hoặc phân vùng khác. Các liên kết cứng chủ yếu được dùng để lưu trữ nội dung file ở một vị trí cố định, thường để tránh việc nhân bản lượng dữ liệu quá lớn.

**Ví dụ về Sym Link và Hard Link**

**Sym Link**

+ ln -s file.txt symlink.txt

+ ls -l

+ echo "Symlink!" > file.txt

+ cat symlink.txt

  Kết quả sẽ là: Symlink!

**Hard Link**

+ echo "Hard Link 1" > file.txt

+ ln file.txt hardlink.txt

+ ls -l

+ echo "Hard Link 2" > file.txt

+ cat hardlink.txt

  Kết quả sẽ là: Hard Link 2

**ls command**

**Liệt kê danh sách file/thư mục**

ls

**Liệt kê danh sách file/thư mục và thuộc tính**

ls -l

**Show file ẩn**

ls -a

**ps command**

ps [options]

**show tiến trình**

ps aux

**kill tiến trình**

kill [options] PID

**top command**

**Kiểm tra tài nguyên cpu đang sử dụng của một vài process đang chạy**

+ top
+ htop
+ ps aux --sort=-%cpu | head -n 10

**Giải thích về Load average, us, sy, ni, id, wa, hi, si, st, zombie process, sleeping process**

+ **Load Average** là một chỉ số cho biết số lượng process đang chờ để được thực thi (đang hoạt động hoặc đang chờ tài nguyên CPU). Nó thường được hiển thị dưới dạng ba giá trị, tương ứng với 1, 5 và 15 phút qua. Giá trị này cho biết mức độ tải trên CPU, với giá trị cao cho thấy hệ thống có thể bị quá tải.
+ **us** là phần trăm thời gian CPU được sử dụng cho các process trong không gian người dùng (user space), tức là các ứng dụng thông thường không phải là phần mềm hệ thống.
+ **sy** là phần trăm thời gian CPU được sử dụng cho các process trong không gian hệ thống (kernel space), tức là các hoạt động của kernel và các driver.
+ **ni** là phần trăm thời gian CPU được sử dụng cho các process có mức độ ưu tiên "nice" (mức độ ưu tiên thấp hơn), tức là các process mà người dùng đã giảm ưu tiên.
+ **id** là phần trăm thời gian CPU không hoạt động, tức là thời gian CPU không bận rộn xử lý bất kỳ process nào.
+ **wa** là phần trăm thời gian CPU đang chờ cho các hoạt động I/O (Input/Output) hoàn thành. Nếu giá trị này cao, có thể cho thấy vấn đề với các thiết bị lưu trữ hoặc mạng.
+ **hi** là phần trăm thời gian CPU xử lý các ngắt phần cứng, tức là các sự kiện từ phần cứng như thiết bị ngoại vi.
+ **si** là phần trăm thời gian CPU xử lý các ngắt phần mềm, tức là các ngắt được tạo ra bởi phần mềm.
+ **st** là phần trăm thời gian mà CPU phải "mất" khi chạy trên môi trường ảo hóa, tức là thời gian mà một VM không thể sử dụng CPU vì các VM khác đang sử dụng nó.
+ **Zombie Process** là một process đã hoàn thành thực hiện nhưng vẫn còn tồn tại trong bảng điều khiển process. Điều này xảy ra khi process cha không đọc trạng thái kết thúc của nó. Zombie process chiếm dụng một chút tài nguyên hệ thống nhưng không hoạt động.
+ **Sleeping Process** là các process đang chờ một sự kiện hoặc tài nguyên nào đó (ví dụ: chờ dữ liệu từ đĩa hoặc mạng). Các process này không sử dụng CPU cho đến khi có sự kiện xảy ra.

**free command**

free -h

**Giải thích ram used, free, shared, buff/cache, free**

+ Ram used: Dung lượng RAM đang được sử dụng. Tuy nhiên, con số này có thể bao gồm cả bộ nhớ được sử dụng cho cache và buffer.
+ Free: Dung lượng RAM hiện không được sử dụng và có sẵn cho các ứng dụng.
+ Shared: Dung lượng RAM được chia sẻ giữa các tiến trình. Thông thường, điều này bao gồm bộ nhớ được sử dụng bởi các thư viện chia sẻ.
+ Buff: Bộ nhớ tạm thời dùng để lưu trữ dữ liệu tạm thời trong quá trình truyền tải, giúp cải thiện hiệu suất khi đọc/ghi đĩa.
+ Cache: Bộ nhớ được sử dụng để lưu trữ dữ liệu đã truy cập gần đây nhằm giảm thời gian truy cập cho các lần truy cập tiếp theo.

**df command**

**Xem dung lượng disk**

df -h

**Phân vùng / là gì**

/ (root fielsystem) là phân vùng chính và quan trọng nhất của hệ thống, chứa tất cả các tệp tin và thư mục cần thiết để hệ điều hành hoạt động.