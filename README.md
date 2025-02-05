Cross-Compiler Instructions
Hướng dẫn này giúp bạn cross-compile ứng dụng từ máy tính khác cho Raspberry Pi.

1. Kiểm tra kiến trúc của Raspberry Pi
Mở terminal và chạy lệnh sau:

bash
Sao chép
Chỉnh sửa
gcc -dumpmachine
Kết quả trả về cần giống như arm-linux-gnueabihf hoặc tương tự.

2. Tải toolchain phù hợp
Tải toolchain từ liên kết này:
https://shorturl.at/binzO

3. Giải nén toolchain
Chạy lệnh sau để giải nén file đã tải:

bash
Sao chép
Chỉnh sửa
tar -xvf gcc-arm-*.tar.bz2
4. Thêm toolchain vào PATH
Thêm đường dẫn toolchain vào biến môi trường:

bash
Sao chép
Chỉnh sửa
export PATH=/path/to/gcc-arm-10.3-2021.07/bin:$PATH
Thay /path/to bằng thư mục bạn đã giải nén toolchain.

5. Cross-compile mã nguồn
Chạy lệnh sau để biên dịch mã nguồn của bạn:

bash
Sao chép
Chỉnh sửa
arm-none-linux-gnueabihf-gcc -o my_app my_code.c
Thay my_code.c bằng file mã nguồn và my_app bằng tên file đầu ra bạn muốn.

6. Chuyển binary đến Raspberry Pi
Dùng lệnh scp để chuyển file đã biên dịch sang Raspberry Pi:

bash
Sao chép
Chỉnh sửa
scp -P 5022 my_app pi@<raspberry_pi_ip>:/home/pi/
Thay <raspberry_pi_ip> bằng địa chỉ IP của Raspberry Pi.
Thay 5022 nếu cần sửa cổng.
7. Chạy ứng dụng trên Raspberry Pi
SSH vào Raspberry Pi và chạy ứng dụng:

bash
Sao chép
Chỉnh sửa
./my_app
Bạn chỉ cần sao chép nội dung này vào tệp README.md. Nếu cần chỉnh sửa, hãy báo tôi biết!
