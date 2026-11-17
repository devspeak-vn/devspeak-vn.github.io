# devspeak-vn.github.io

Trang web của kênh **DevSpeak VN**: trang chủ, điều khoản sử dụng, chính sách quyền riêng tư (song ngữ Việt và Anh). Dùng làm link Home page, Privacy policy, Terms of service trong cấu hình OAuth của Google.

| Đường dẫn | File |
|---|---|
| https://devspeak-vn.github.io/ | `index.html` |
| https://devspeak-vn.github.io/privacy | `privacy.html` |
| https://devspeak-vn.github.io/terms | `terms.html` |

GitHub Pages tự phục vụ `/privacy` từ `privacy.html`, nên không cần thư mục con.

## Trước khi đăng: thay các chỗ giữ chỗ

```bash
grep -n "hieuhoang25102001td@gmail.com" *.html                 # email liên hệ (6 chỗ mỗi trang)
sed -i '' 's/hieuhoang25102001td@gmail.com@gmail.com/email.cua.ban@gmail.com/g' *.html   # macOS
```

Kiểm tra thêm link kênh trong `index.html` (`@devspeakvn` trên YouTube, Facebook, TikTok) cho khớp với tên kênh thật.

## Đăng lên GitHub Pages

1. Tạo tài khoản hoặc tổ chức GitHub tên **`devspeak-vn`**.
2. Trong đó, tạo repo **public** tên chính xác **`devspeak-vn.github.io`**.
3. Đẩy các file này lên nhánh `main`:
   ```bash
   git init && git add . && git commit -m "Trang DevSpeak VN"
   git branch -M main
   git remote add origin https://github.com/devspeak-vn/devspeak-vn.github.io.git
   git push -u origin main
   ```
4. Repo → **Settings → Pages** → Source: **Deploy from a branch**, nhánh `main`, thư mục `/ (root)` → **Save**. Sau 1–2 phút trang sẽ chạy.

## Khai báo trong Google Cloud

**Google Auth Platform → Branding:**
- Application home page: `https://devspeak-vn.github.io/`
- Application privacy policy link: `https://devspeak-vn.github.io/privacy`
- Application terms of service link: `https://devspeak-vn.github.io/terms`
- Authorized domains: `devspeak-vn.github.io`

Nếu Google yêu cầu xác minh quyền sở hữu domain, làm qua Google Search Console (thêm thẻ meta xác minh vào `<head>` của `index.html`).
