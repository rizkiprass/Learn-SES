# Amazon SES Learning Project 🚀

Proyek pembelajaran Amazon Simple Email Service (SES) dengan hands-on examples untuk SMTP dan API integration.

## 📖 Apa itu Amazon SES?

Amazon Simple Email Service (SES) adalah layanan email cloud yang **scalable**, **cost-effective**, dan **highly reliable** untuk mengirim dan menerima email.

### Use Cases
- 📧 **Transactional Emails** - Order confirmations, password resets, notifications
- 📰 **Marketing Emails** - Newsletters, promotions, campaigns
- 🔔 **System Notifications** - Alerts, monitoring, reports
- ✅ **Email Verification** - OTP, account verification

### Keunggulan Amazon SES
| Feature | Benefit |
|---------|---------|
| **Cost** | $0.10 per 1000 emails |
| **Deliverability** | High reputation, ISP whitelisting |
| **Scalability** | Handle millions of emails |
| **Integration** | SMTP & API support |
| **Analytics** | Bounce, complaint, delivery tracking |

---

## 🏗️ Struktur Proyek

```
SES/
├── README.md                    # Dokumentasi ini
├── docs/                        # Panduan detail
│   ├── 01-getting-started.md   # Setup AWS SES
│   ├── 02-smtp-guide.md        # SMTP configuration
│   └── 03-api-guide.md         # API dengan AWS SDK
├── smtp-example/               # Contoh SMTP dengan Nodemailer
├── api-example/                # Contoh API dengan AWS SDK
└── full-app/                   # Aplikasi lengkap
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js 18+
- AWS Account dengan SES enabled
- Verified email address (untuk sandbox mode)

### 1. SMTP Example
```bash
cd smtp-example
npm install
cp .env.example .env
# Edit .env dengan credentials Anda
node index.js
```

### 2. API Example
```bash
cd api-example
npm install
cp .env.example .env
# Edit .env dengan AWS credentials
node index.js
```

### 3. Full Application
```bash
cd full-app
npm install
cp .env.example .env
# Edit .env dengan credentials
npm run dev
# Buka http://localhost:3000
```

---

## 📚 Dokumentasi

| Doc | Deskripsi |
|-----|-----------|
| [Getting Started](./docs/01-getting-started.md) | Setup AWS SES dari nol |
| [SMTP Guide](./docs/02-smtp-guide.md) | Konfigurasi SMTP credentials |
| [API Guide](./docs/03-api-guide.md) | Menggunakan AWS SDK |

---

## ⚠️ Important: Sandbox Mode

Secara default, Amazon SES berada dalam **sandbox mode**:
- ✅ Hanya bisa kirim ke verified email addresses
- ✅ Maximum 200 emails per 24 jam
- ✅ Maximum 1 email per detik

Untuk production, Anda perlu [request production access](https://docs.aws.amazon.com/ses/latest/DeveloperGuide/request-production-access.html).

---

## 🔐 AWS Credentials

### Untuk SMTP
Buat SMTP credentials di SES Console:
1. Buka AWS SES Console
2. SMTP Settings → Create SMTP credentials
3. Simpan username dan password

### Untuk API
Buat IAM User dengan permissions:
```json
{
  "Version": "2012-10-17",
  "Statement": [{
    "Effect": "Allow",
    "Action": [
      "ses:SendEmail",
      "ses:SendRawEmail",
      "ses:SendTemplatedEmail"
    ],
    "Resource": "*"
  }]
}
```

---

## 📝 License

MIT License - Feel free to use for learning!
