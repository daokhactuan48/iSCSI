iSCSI
=====

# Giới Thiệu về iSCSI 

iSCSI là từ viết tắt của Internet Small Computer System Interface, là giao thức được sử dụng để gửi các lệnh SCSI trong các gói tin. Nói một cách đơn giản iSCSI là giao thức được dành Storage initiator (thông thường là một server) gửi SCSI command đến storage target trên iternet.

# Một số khái niệm trong iSCSI

iSCSI target là nơi chịu trách nhiệm nhận các yêu cầu của iSCSI initiator hoặc là nói đưa ra các block size cho iSCSI initiator. Đây sẽ là nơi đặt storage.

iSCSI initiator nơi import các block device, format và sử dụng nó sau khi nhận được thông tin về block device của iSCSI target cung cấp 

LUN logical unit number là số được sử dụng để xác định logical units. Có thể hiểu LUN như là một logical disk. 

# Demo sử dụng Openfiler 

Openfiler là một hệ điều hành cung cấp dịch vụ NAS và SAN. 

## Cài đặt Openfiler trên Vmware. 

B1: Chuẩn bị máy ảo: 

<img src=http://i.imgur.com/trtWIsi.png width="60%" height="60%" border="1">

B2: Nhấn Enter khi gặp màn hình sau vào cài đặt bằng giao diện:

<img src=http://i.imgur.com/xSJvMiX.png width="60%" height="60%" border="1">

B3: Chọn phần cùng cài sau đó nhấn next: 

<img src=http://i.imgur.com/XvAyKJn.png width="60%" height="60%" border="1">

B4: Cấu hình card mạng: 

<img src=http://i.imgur.com/9w7UhPw.png width="60%" height="60%" border="1">

B5: Đặt tài khoản root

<img src=http://i.imgur.com/9w7UhPw.png width="60%" height="60%" border="1">

B6: Nhấn next sau đó sẽ cài đặt các gói và hoàn thành tiến trình cài đặt sẽ restart lại máy và xuất hiện màn hình sau:

<img src=http://i.imgur.com/iRgY6Jh.png width="60%" height="60%" border="1">

B7: Để cấu hình ta vào trình duyệt và gõ địa chỉ như sau: 

https://ip_address:446

Tài Khoản mặc định: openfiler  
password          : pasword


## Thiết lập dịch vụ iSCSI trong Openfiler.

B1: Cấu hình mạng để cho phép mang nào được sử dụng storage. 

<img src=http://i.imgur.com/paciWnT.png width="60%" height="60%" border="1">

B2: Vào tab volume: 

<img src=http://i.imgur.com/havABX7.png width="60%" height="60%" border="1">

Tạo các physical volume cho ổ cứng. 

B3: Vào section volume group để tạo ra các volume group. 

<img src=http://i.imgur.com/ALkOVDV.png width="60%" height="60%" border="1">

B4: Tạo logical volume 

<img src=http://i.imgur.com/GsUCC31.png width="60%" height="60%" border="1">

B5:Vào tab service enable dịch vụ iSCSI lên: 

<img src=http://i.imgur.com/0ksE360.png width="60%" height="60%" border="1">

B6: Quay lại tab volume để tạo ra các target. Vào sesion iSCSI target. 

Chọn tab target Configuration: Tạo ra các target 

<img src=http://i.imgur.com/4qU3IsX.png width="60%" height="60%" border="1">

Chọn lun map vào các target:

<img src=http://i.imgur.com/vQNgx4H.png width="60%" height="60%" border="1">

Chọn Network ACL: Allow IP lên mặc định là deny 

<img src=http://i.imgur.com/RAAiarq.png width="60%" height="60%" border="1">

B7: Hoàn thành quá trình tạo target trên Openfiler. 















