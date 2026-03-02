# Instafinds.id - Admin Panel

Dashboard admin untuk mengelola produk, kategori, dan analytics untuk website Instafinds.id

## 📋 Struktur File

- `admin.html` - Interface admin dashboard
- `admin.css` - Styling admin panel  
- `admin.js` - Logic dan CRUD operations

## 🚀 Fitur

- **Dashboard** - Statistik total produk, clicks, views, dan platform aktif
- **Produk Management** - CRUD (Create, Read, Update, Delete) produk
- **Category Management** - Kelola kategori produk
- **Analytics** - Tracking clicks dan views per produk
- **Export/Import** - Backup dan restore data dalam format JSON
- **Multi-Platform Support** - Shopee, Tokopedia, Lazada, Amazon, Bukalapak

## 📦 Data Structure

### Produk (instafinds_products)
```json
{
  "id": "1234567890",
  "name": "Nama Produk",
  "image": "https://...",
  "category": "1",
  "originalPrice": 150000,
  "price": 100000,
  "discount": 33,
  "rating": 4.5,
  "reviews": 245,
  "description": "Deskripsi...",
  "affiliateLink": "https://...",
  "platforms": ["shopee", "tokopedia"],
  "clicks": 15,
  "views": 250,
  "createdAt": "2024-01-01T..."
}
```

### Kategori (instafinds_categories)
```json
{
  "id": 1,
  "name": "Kecantikan",
  "icon": "fas fa-lipstick",
  "description": "Produk kecantikan dan perawatan"
}
```

## 🎯 Cara Menggunakan

### 1. Menambah Produk
1. Klik "Kelola Produk" di sidebar
2. Klik tombol "Tambah Produk"
3. Isi semua field yang bertanda * (required)
4. Pilih minimal 1 platform affiliate
5. Klik "Simpan Produk"

### 2. Edit Produk
1. Cari produk di halaman "Kelola Produk"
2. Klik tombol "Edit"
3. Ubah data yang diperlukan
4. Klik "Simpan Produk"

### 3. Hapus Produk
1. Pilih produk yang ingin dihapus
2. Klik tombol "Hapus"
3. Konfirmasi penghapusan

### 4. Kelola Kategori
1. Klik "Kategori" di sidebar
2. Klik "Tambah Kategori" untuk tambah kategori baru
3. Gunakan Font Awesome class untuk icon (cth: `fas fa-shirt`)

### 5. Backup & Restore Data
1. Klik "Setelan" di sidebar
2. Klik "Export JSON" untuk download backup
3. Klik "Import JSON" untuk restore dari file backup

## 💾 LocalStorage

Data disimpan di browser LocalStorage:
- Key produk: `instafinds_products`
- Key kategori: `instafinds_categories`
- Max ukuran: ~5MB

## 🚀 Deployment

Admin Panel di-deploy di GitHub Pages:
- URL: https://botbynetz.github.io/Instafinds-Admin/

### Setup GitHub Pages (jika fork)

1. Push files ke repository `Instafinds-Admin`
2. Go to Settings → Pages
3. Source: Deploy from a branch
4. Branch: `main` / `master`
5. Save

## 🔄 Sinkronisasi dengan Website Publik

Admin Panel dan Website publik berbagi LocalStorage yang sama. Perubahan di admin akan otomatis terlihat di website publik dengan trigger:
- Refresh website publik
- Atau otomatis jika akses dari domain yang sama

## 📊 Analytics

Setiap produk track:
- **Clicks** - Jumlah klik tombol "Beli"
- **Views** - Jumlah kali produk ditampilkan
- **Rating** - Rating produk (0-5)
- **Reviews** - Jumlah review

Lihat di Dashboard → "Top Produk" untuk produk dengan clicks tertinggi.

## 🎨 Interface

- **Sidebar** - Navigasi utama dengan gradient ungu-pink
- **Top Bar** - User info dan page title
- **Dashboard** - Overview statistics dan recent products
- **Modal Forms** - Dialog untuk add/edit produk dan kategori
- **Responsive Design** - Optimal di desktop, tablet, dan mobile

## 🔐 Features

- Form validation untuk input data
- Konfirmasi penghapusan untuk mencegah accident delete
- Auto-save ke LocalStorage
- Notification system untuk feedback user
- Mobile menu toggle untuk responsive navigation

## 🐛 Troubleshooting

**Data tidak muncul?**
- Check browser LocalStorage (F12 → Application → LocalStorage)
- Pastikan key `instafinds_products` dan `instafinds_categories` ada

**Data tidak sync ke website?**
- Pastikan website publik sudah refresh
- Check browser console untuk error messages

**Max storage reached?**
- Export data dulu sebagai backup
- Klik "Reset Semua Data" untuk hapus semua
- Import backup jika diperlukan

## 📝 Catatan Penting

1. **Backup Rutin** - Export data secara berkala
2. **URL Produk** - Gunakan URL langsung (bukan shorlink) untuk affiliate links
3. **Icon Kategori** - Gunakan Font Awesome 6.0 class
4. **Platform Selection** - Minimal 1 platform harus dipilih

## 🌐 Koneksi ke Website Publik

Website publik otomatis load produk dari LocalStorage yang ada:

```javascript
const STORAGE_KEY = 'instafinds_products';
const products = JSON.parse(localStorage.getItem(STORAGE_KEY));
```

Pastikan URL website publik sama domain dengan admin untuk LocalStorage sync.

## 📞 Support

- Check console (F12) untuk debugging
- Verify data di LocalStorage
- Export/Import untuk backup recovery

---

Last Updated: 2024
Instafinds Admin Team
