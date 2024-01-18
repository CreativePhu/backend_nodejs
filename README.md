Các bước tạo một server backend với nodejs:

B1: tạo một folder dự án

B2: chạy lệnh npm init để khởi tạo dự án với file package.json

B3: chạy lệnh npm install express --save để cài môi trường làm việc với express

B4: gán câu lệnh dưới đây vào file js chính để tiến hành câu lệnh hello world đầu tiên cũng như kiểm tra project đang hoạt động ổn định !


const express = require('express')

const app = express()

const port = 3000


app.get('/', (req, res) => {

  res.send('Hello World!')
  
})


app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})


B5: tiến hành chạy câu lệnh **npm i ejs** để cài template engines (ejs)

B6: thêm các câu lện dưới đây vào file js chính để cấu hình cho biết sử dụng template nào và sử dụng ở đâu 

với path là một thư viện giúp lấy các đường dẫn bắt đầu từ thư mục chứa file đang đứng !


const path = require('path')

app.set('views', path.join(__dirname, "views"));

app.set('view engine', 'ejs');


sau đó ta có thể dùng câu lệnh: (lưu ý phải tạo file sample.ejs lưu trong thư mục views đã khai báo ở bước 6)

để render ra một giao diện html có thể sử dụng ejs

app.get('/', (req, res) => {

    res.render("sample.ejs")
    
})

lưu ý: ta có file .env là một file lưu giữ các keyword cấu hình ta có thể đọc giá trị các keyword đó nhưng phải tải thư viện

npm i dotenv

là một thư viện giúp có thể đọc các keyword từ file .env bằng cách

require('dotenv').config() --import thư viện vào file

const port = process.env.PORT --có thể lấy ra các giá trị trong file thông qua process.env trong đó .PORT là tên keyword trong file .evn
