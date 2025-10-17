# 🚀 Smart IG Commerce Bot — PRO (v2)
تاريخ الإنشاء: 2025-10-17

## الميزات الجديدة
- 🌍 قوالب **عربي/إنكليزي** مع كشف تلقائي للغة.
- 🧮 أكواد خصم **(percent/fixed)** + حساب إجمالي مع شحن.
- 🚚 **مناطق شحن** (بغداد/المحافظات) قابلة للتعديل.
- 🗂️ أقسام منتجات + أسماء بديلة + روابط صور.
- 🧾 **سير عمل الطلب** (pending → confirmed → shipped → delivered/canceled) + **سجل زمني**.
- 🏭 إنقاص المخزون تلقائي عند إنشاء الطلب.
- 💬 الرد من لوحة الإدارة مباشرة للزبون (DM).
- 🔔 إشعار **Telegram** اختياري عند كل طلب.
- 🛡️ Rate limiting على `/webhook` + توقيع Meta + JWT.
- 📊 إحصائيات ولوحة مؤشرات + تصدير CSV.
- 🔎 واجهة **/catalog/products.json** لعرض الكاتالوج خارجيًا.
- 📥 استيراد CSV للمنتجات من اللوحة.

## تشغيل
```bash
npm i
cp .env.sample .env
# عبي القيم: PAGE_ACCESS_TOKEN, APP_SECRET, VERIFY_TOKEN, ADMIN_USERNAME, ADMIN_PASSWORD, JWT_SECRET, DEFAULT_STORE_NAME, (اختياري TELEGRAM/SHEETS)
npm run start
```
لوحة الإدارة: `/admin/`

## ربط Meta Webhook
- Callback URL: `https://YOUR-SERVICE/webhook`
- Verify Token: نفس `.env`
- فعّل Instagram Messaging + Page events.