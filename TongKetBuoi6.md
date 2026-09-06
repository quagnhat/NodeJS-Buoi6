# 🌟 TỔNG KẾT KIẾN THỨC BUỔI 6: EXPRESS.JS CƠ BẢN

## 1. Express.js Là Gì?
- Là framework web phổ biến nhất của Node.js.
- Giúp viết code ngắn gọn hơn rất nhiều so với module `http` thuần.
- Cài đặt: `npm install express`

## 2. So Sánh Thu Nhận Dữ Liệu (Request)
- **`req.query`**: Đọc tham số sau dấu `?` trên URL (Ví dụ: `/search?keyword=nodejs` -> `req.query.keyword`).
- **`req.params`**: Đọc tham số động trên đường dẫn (Ví dụ: `/products/:id` -> `req.params.id`).
- **`req.body`**: Đọc dữ liệu gửi kèm khi dùng `POST`, `PUT`.
  - Cần middleware: `app.use(express.json())` cho API hoặc `app.use(express.urlencoded({ extended: true }))` cho Form HTML.

## 3. Trả Dữ Liệu (Response)
- `res.send("...")`: Trả text hoặc HTML.
- `res.json({...})`: Trả dữ liệu JSON (Express tự stringify, không cần viết thủ công).
- `res.status(404)`: Gán mã trạng thái trước khi gửi.

## 4. Middleware & Xử Lý 404
- Middleware chạy theo thứ tự từ trên xuống dưới.
- Luôn đặt middleware đọc body trước các route.
- Route 404 luôn đặt ở cuối cùng của file:
```javascript
app.use((req, res) => {
  res.status(404).json({ message: "Route not found" });
});
```
