# Product Dashboard - Modern Management System

## 📋 Mô tả

Dashboard quản lý sản phẩm hiện đại với giao diện đẹp mắt, sử dụng API từ `https://api.escuelajs.co/api/v1/products`.

## ✨ Tính năng

### 1. **Hiển thị dữ liệu**
- ✅ Hiển thị toàn bộ hình ảnh sản phẩm
- ✅ Bảng có màu xen kẽ (dòng đen/trắng)
- ✅ Hiển thị đầy đủ thông tin: ID, Image, Title, Description, Price, Category

### 2. **Tìm kiếm**
- ✅ Tìm kiếm theo title
- ✅ Cập nhật real-time khi onChange
- ✅ Hiển thị số lượng kết quả tìm kiếm

### 3. **Phân trang**
- ✅ Lựa chọn số items mỗi trang: 5, 10, 20
- ✅ Nút Previous/Next
- ✅ Hiển thị trang hiện tại và tổng số trang
- ✅ Disable nút khi không thể chuyển trang

### 4. **Sắp xếp**
- ✅ Sắp xếp theo giá (tăng dần/giảm dần)
- ✅ Sắp xếp theo tên (A-Z / Z-A)
- ✅ Hiển thị trạng thái active của nút sắp xếp

### 5. **Thống kê**
- ✅ Tổng số sản phẩm
- ✅ Số sản phẩm đang hiển thị
- ✅ Trang hiện tại

## 🎨 Thiết kế

- **Typography**: Bebas Neue (headers) + Work Sans (body)
- **Color Scheme**: Black & White với accent màu đỏ (#ff3366)
- **Style**: Brutalist/Minimal modern
- **Animations**: Smooth transitions và hover effects
- **Responsive**: Tương thích với mobile và tablet

## 📁 Cấu trúc file

```
product-dashboard/
├── index.html          # File HTML chính
├── api.js             # Module xử lý API calls
└── README.md          # File hướng dẫn này
```

## 🚀 Cách sử dụng

### Chạy local

1. Tải xuống cả 2 file: `index.html` và `api.js`
2. Đảm bảo 2 file nằm cùng thư mục
3. Mở file `index.html` bằng trình duyệt web
4. Dashboard sẽ tự động load dữ liệu từ API

### Chạy với Live Server (khuyến nghị)

1. Cài đặt extension "Live Server" trong VS Code
2. Right-click vào `index.html` → "Open with Live Server"
3. Dashboard sẽ mở tại `http://localhost:5500`

## 🔧 API Reference

### Base URL
```
https://api.escuelajs.co/api/v1/products
```

### Endpoint sử dụng

#### Get All Products
```javascript
GET /products
```

**Response:**
```json
[
  {
    "id": 1,
    "title": "Product Name",
    "price": 99,
    "description": "Product description",
    "category": {
      "id": 1,
      "name": "Category Name"
    },
    "images": ["url1", "url2"]
  }
]
```

## 💻 Code Structure

### api.js
```javascript
const ProductAPI = {
    async getAllProducts() {
        // Fetch all products from API
    }
}
```

### index.html
- **State Management**: Quản lý trạng thái với JavaScript vanilla
- **Event Listeners**: Search, Sort, Pagination
- **Render Functions**: Dynamic table rendering
- **Responsive Design**: CSS Grid & Flexbox

## 🎯 Các chức năng chính

### Search Function
```javascript
searchInput.addEventListener('input', (e) => {
    const searchTerm = e.target.value.toLowerCase().trim();
    filteredProducts = allProducts.filter(product => 
        product.title.toLowerCase().includes(searchTerm)
    );
    // Update UI
});
```

### Sort Functions
```javascript
// Price Ascending
filteredProducts.sort((a, b) => a.price - b.price);

// Price Descending
filteredProducts.sort((a, b) => b.price - a.price);

// Name A-Z
filteredProducts.sort((a, b) => a.title.localeCompare(b.title));

// Name Z-A
filteredProducts.sort((a, b) => b.title.localeCompare(a.title));
```

### Pagination Logic
```javascript
const startIndex = (currentPage - 1) * itemsPerPage;
const endIndex = startIndex + itemsPerPage;
const productsToShow = filteredProducts.slice(startIndex, endIndex);
```

## 🌟 Highlights

- ✨ **Modern UI/UX**: Giao diện đẹp, chuyên nghiệp
- ⚡ **Performance**: Fast rendering với vanilla JavaScript
- 📱 **Responsive**: Hoạt động tốt trên mọi thiết bị
- 🎨 **Animations**: Smooth transitions và effects
- 🔍 **Real-time Search**: Tìm kiếm instant
- 📊 **Statistics**: Hiển thị số liệu thống kê

## 🐛 Troubleshooting

### Lỗi CORS
Nếu gặp lỗi CORS khi chạy trực tiếp file HTML:
- Sử dụng Live Server extension
- Hoặc chạy với Python: `python -m http.server 8000`

### Hình ảnh không hiển thị
- Kiểm tra kết nối internet
- API có thể trả về URL hình ảnh không hợp lệ
- Fallback image sẽ được hiển thị tự động

## 📝 Notes

- Dashboard sử dụng 100% vanilla JavaScript (không có framework)
- Tương thích với tất cả trình duyệt hiện đại
- Không cần cài đặt dependencies
- Data được fetch từ API thực

## 👨‍💻 Developer Info

**Technology Stack:**
- HTML5
- CSS3 (with CSS Variables, Grid, Flexbox)
- Vanilla JavaScript (ES6+)
- Google Fonts API
- External REST API

**Browser Support:**
- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)

## 📄 License

Free to use for educational purposes.

---

Enjoy using the Product Dashboard! 🚀
