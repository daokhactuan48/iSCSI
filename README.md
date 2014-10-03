iSCSI
=====

# Giới Thiệu về iSCSI 

iSCSI là từ viết tắt của Internet Small Computer System Interface, là giao thức được sử dụng để gửi các lệnh SCSI trong các gói tin. Nói một cách đơn giản iSCSI là giao thức được dành Storage initiator (thông thường là một server) gửi SCSI command đến storage target trên iternet.

# Một số khái niệm trong iSCSI

iSCSI target là nơi chịu trách nhiệm nhận các yêu cầu của iSCSI initiator hoặc là nói đưa ra các block size cho iSCSI initiator. Đây sẽ là nơi đặt storage.
iSCSI initiator nơi import các block device, format và sử dụng nó sau khi nhận được thông tin về block device của iSCSI target cung cấp 
LUN logical unit number là số được sử dụng để xác định logical units. Có thể hiểu LUN như là một logical disk. 


