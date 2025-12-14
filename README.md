# Write-Up-KCSC-Recruitment-2026

Bài thi này mình làm rất tệ, chỉ được một bài như sau:

<img width="497" height="570" alt="image" src="https://github.com/user-attachments/assets/703ea6dd-7441-4170-9a56-4ca2f384f9b2" />

## Lối giải:

Đưa chương trình vào IDA, tìm được hàm main và decompile như sau:

<img width="1919" height="1077" alt="image" src="https://github.com/user-attachments/assets/ebbda2a9-5278-4bee-86d3-1ae452205cb6" />

Chú ý đến đoạn mã sau:

<img width="584" height="240" alt="image" src="https://github.com/user-attachments/assets/4e1fc2d8-31a0-4181-9575-89ac9cc07c7f" />

Khi v7, thông qua hàm sub_1400013F0 của v9 và 1337 đúng với giá trị 0xD427202CB4B2LL thì giải mã frag thông qua việc lặp lại hàm sub_1400013F0 của v9 nhưng với 9999

Khi xem hàm sub_1400013F0, ta thấy:

<img width="663" height="267" alt="image" src="https://github.com/user-attachments/assets/c71a1ce7-782c-43be-b5dc-895705d83218" />

Nhiệm vụ của hàm này là tính harsh ở đây là của v9 với 1337 và so sánh với 0xD427202CB4B2LL. Cũng như tính harse của v9 với 9999 nhằm giải mã key\

Nhìn lại v9, ta thấy trước đó v9 đi qua một hàm là hàm sub_1400012C0. Hàm này có nhiệm vụ cộng giá trị của input với những giá trị tĩnh có sẵn trong dữ liệu chương trình rồi chia lấy dư cho 256.

Từ đầy ta viết chương trình này:

"""

"""


Ở cửa sổ IDA, chọn File -> Script commands rồi làm và lấy output như trong hình này:

<img width="1924" height="1079" alt="image" src="https://github.com/user-attachments/assets/2fe06ff9-0f0e-413e-b2b6-004c3820ab0e" />

Copy mã vào ô (1), chọn Python ở ô (2) và lấy kết quả ở ô (3)

Sau đó mở file chương trình lên. Ở đây vì mình để các file chương trình cùng 1 thư mục nên chúng bị trùng nhau. File chell.exe đã trở thành file chell_10.exe

Nhập các input bạn vừa lấy như sau:

<img width="977" height="502" alt="image" src="https://github.com/user-attachments/assets/c7be02b1-772f-4884-b311-e391687ec306" />

Tuy nhiên, khi nhấn Enter, chương trình lập tức thoát ra. Giải pháp cho vấn đề này là mở nó trong cmd.

Mở CMD lên rồi kéo file chương trình vào CMD. Sau đó thì nhập 3 key thu được và ta ra được kết quả

<img width="964" height="510" alt="image" src="https://github.com/user-attachments/assets/a09f5588-2ae0-4c8a-ae46-7f829b67d0ce" />

Giải ra được flag, kết thúc bài.
