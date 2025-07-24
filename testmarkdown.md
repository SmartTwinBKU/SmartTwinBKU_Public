# Cài đặt SmartTwin

Để bắt đầu sử dụng SmartTwin, bạn cần thực hiện các bước cài đặt sau:

## 1. Yêu cầu hệ thống

- Node.js (phiên bản 18 trở lên)  
- npm hoặc Yarn  
- Tài khoản Vercel (để triển khai)  
- Tài khoản cơ sở dữ liệu (ví dụ: Supabase, Neon)  
- Tài khoản dịch vụ IoT (ví dụ: AWS IoT, Azure IoT Hub)

## 2. Sao chép dự án

Sử dụng Git để sao chép kho lưu trữ SmartTwin:
<pre>
```bash
git clone [URL_KHO_LƯU_TRỮ_CỦA_BẠN]
cd smarttwin
```
</pre>

## 3. Cài đặt phụ thuộc

Cài đặt các gói phụ thuộc cần thiết:

```bash
npm install # hoặc yarn install
```

## 4. Cấu hình biến môi trường

Tạo một file `.env.local` trong thư mục gốc của dự án và thêm các biến môi trường sau:

```bash
# Cấu hình cơ sở dữ liệu (ví dụ Supabase)
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

# Cấu hình IoT (ví dụ AWS IoT)
AWS_IOT_ENDPOINT=your_aws_iot_endpoint
AWS_ACCESS_KEY_ID=your_aws_access_key_id
AWS_SECRET_ACCESS_KEY=your_aws_secret_access_key

# Các biến khác
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

Đảm bảo thay thế các giá trị giữ chỗ bằng thông tin cấu hình thực tế của bạn.

## 5. Khởi tạo cơ sở dữ liệu

Nếu bạn đang sử dụng Supabase, bạn có thể sử dụng các script SQL để tạo bảng và dữ liệu mẫu.  
Tham khảo thư mục `scripts/db` để biết thêm chi tiết.

```bash
# Ví dụ: chạy migration Supabase
npx supabase db push
```

## 6. Chạy ứng dụng

Khởi động máy chủ phát triển:

```bash
npm run dev # hoặc yarn dev
```

Ứng dụng sẽ chạy trên `http://localhost:3000`.

## 7. Triển khai lên Vercel

Để triển khai ứng dụng của bạn lên Vercel, hãy đảm bảo bạn đã cài đặt Vercel CLI:

```bash
npm i -g vercel
```

Sau đó, chạy lệnh triển khai từ thư mục gốc của dự án:

```bash
vercel
```

Bạn sẽ được nhắc cấu hình các biến môi trường trên Vercel.  
Đảm bảo thêm tất cả các biến từ file `.env.local` của bạn vào cấu hình dự án Vercel.