# 🚀 Getting Started dengan Amazon SES

Panduan lengkap untuk memulai Amazon Simple Email Service dari nol.

## 1. Buat/Login AWS Account

1. Buka [AWS Console](https://aws.amazon.com/console/)
2. Sign in atau create new account
3. Pastikan billing sudah aktif

---

## 2. Enable Amazon SES

### Pilih Region
Amazon SES tersedia di beberapa region. Pilih yang terdekat:

| Region | Endpoint |
|--------|----------|
| US East (N. Virginia) | `email.us-east-1.amazonaws.com` |
| US West (Oregon) | `email.us-west-2.amazonaws.com` |
| EU (Ireland) | `email.eu-west-1.amazonaws.com` |
| Asia Pacific (Singapore) | `email.ap-southeast-1.amazonaws.com` |
| Asia Pacific (Tokyo) | `email.ap-northeast-1.amazonaws.com` |

### Langkah-langkah:
1. Buka [Amazon SES Console](https://console.aws.amazon.com/ses/)
2. Pilih region di pojok kanan atas
3. SES akan otomatis ter-enable

---

## 3. Verify Email Address

> ⚠️ **Sandbox Mode**: Di sandbox, Anda hanya bisa kirim dari DAN ke verified addresses.

### Verify Sender Email:
1. SES Console → **Verified identities**
2. Klik **Create identity**
3. Pilih **Email address**
4. Masukkan email Anda
5. Klik **Create identity**
6. Cek inbox, klik link verifikasi

### Verify Recipient Email (untuk testing):
Ulangi langkah di atas untuk email penerima.

---

## 4. Buat IAM User untuk API Access

### Langkah-langkah:
1. Buka [IAM Console](https://console.aws.amazon.com/iam/)
2. Users → **Create user**
3. Nama: `ses-user`
4. Pilih **Attach policies directly**
5. Cari dan pilih: `AmazonSESFullAccess`
6. Create user
7. Buka user → **Security credentials**
8. **Create access key** → pilih "Application running outside AWS"
9. **Simpan Access Key ID dan Secret Access Key!**

---

## 5. Buat SMTP Credentials (untuk SMTP)

### Langkah-langkah:
1. SES Console → **SMTP settings**
2. Klik **Create SMTP credentials**
3. IAM User Name: `ses-smtp-user`
4. Klik **Create**
5. **Download credentials** atau copy SMTP username & password

> ⚠️ Password SMTP berbeda dengan Secret Access Key IAM!

---

## 6. Test Kirim Email (Console)

Sebelum coding, test via console:

1. SES Console → **Verified identities**
2. Klik email yang sudah verified
3. Klik **Send test email**
4. Isi:
   - **From**: email Anda (verified)
   - **To**: email penerima (verified di sandbox)
   - **Subject**: Test
   - **Body**: Hello from SES!
5. Klik **Send test email**
6. Cek inbox penerima

---

## 7. Request Production Access (Optional)

Untuk keluar dari sandbox mode:

1. SES Console → **Account dashboard**
2. Klik **Request production access**
3. Isi form:
   - **Mail type**: Transactional / Marketing
   - **Website URL**: URL aplikasi Anda
   - **Use case description**: Jelaskan penggunaan
4. Submit dan tunggu approval (biasanya 24-48 jam)

---

## ✅ Checklist Sebelum Lanjut

- [ ] AWS Account aktif
- [ ] SES enabled di region pilihan
- [ ] Email sender verified
- [ ] Email recipient verified (untuk sandbox)
- [ ] IAM User dengan access key (untuk API)
- [ ] SMTP credentials (untuk SMTP)

---

## 📌 Tips

1. **Simpan credentials dengan aman** - Jangan commit ke Git!
2. **Gunakan .env file** - Untuk menyimpan credentials
3. **Test di sandbox dulu** - Sebelum request production
4. **Monitor bounces & complaints** - Untuk menjaga reputation

---

**Next:** [SMTP Guide →](./02-smtp-guide.md)
