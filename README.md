***

Ở project này, ta sẽ thu thập dữ liệu số ca nhiễm Covid 19 ở Việt Nam qua từng ngày khác nhau. Trang web tại [đây](https://web.archive.org/web/20210907023426/https://ncov.moh.gov.vn/vi/web/guest/dong-thoi-gian).

1. Xây dựng được Spider để tải và bóc tách các dữ liệu cần thiết.
2. Sử dụng Spider để xử lý việc chuyển trang web để lấy được các dữ liệu từ ngày cũ hơn.
3. Lấy được dữ liệu về ngày tháng và số ca nhiễm mới vào ngày đó.
4. Lưu các dữ liệu thu thập được dưới dạng .json.

***

Hướng dẫn

Trang web này không dùng Splash để click nút bấm được (hình dưới). Bạn có thể thử xem chứ lúc mình làm không được :D  

![img1](https://user-images.githubusercontent.com/105615288/169562908-696d7dcc-4dca-44a2-90f7-5af00a2ac220.png)


Mình chỉ cần dùng Scrapy cùng với số chỉ mục trang để chuyển trang. Xem tệp spiders/covid.py.

Nội dung được bỏ dấu bằng tệp no_accent_vietnamese.py. Trích xuất nội dung bằng Regular expression (regex).

Dữ liệu sau khi crawl thành dạng đơn giản trong tệp output_co_ban.json, và phức tạp hơn 1 chút trong output_nang_cao.json

Ouput thứ nhất chỉ gồm 2 thông tin: thời điểm và số ca mắc mới.

Output thứ hai gồm: thời điểm, số ca mắc mới và số ca từng thành phố/tỉnh (hình mẫu).

![image](https://user-images.githubusercontent.com/105615288/169566116-a4f9ae7b-8465-4585-80a6-9df7c49c3033.png)
