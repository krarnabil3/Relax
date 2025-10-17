# Instagram Order Bot — Full Deploy

هذا الإصدار جاهز للنشر بالكامل، مع Dockerfile وملف render.yaml للنشر السريع على Render.

## خيارات النشر
### (أ) Deploy بنقرة واحدة على Render (Blueprint)
1) ارفع محتويات هذا المشروع إلى GitHub Repo.
2) ادخل Render → **New** → **Blueprint** واختر مستودعك (الملف `render.yaml` موجود).
3) بعد الإنشاء، افتح الخدمة وأضف المتغيرات:
   - `VERIFY_TOKEN` = كلمة قوية من اختيارك
   - `PAGE_ACCESS_TOKEN` = من Meta (Instagram Messaging)
   - `APP_SECRET` = من Meta App
4) انتظر نجاح البناء. رابط التطبيق يكون مثل: `https://your-app.onrender.com`

### (ب) Deploy خدمة Web عادية على Render
- New → Web Service → Connect Repo → Build: `npm i` ، Start: `node index.js`.
- أضف Env Vars نفسها أعلاه.

## ربط Webhook في Meta
- Webhooks (Page) → Callback URL: `https://YOUR-DOMAIN/webhook`
- Verify Token: نفس `VERIFY_TOKEN`
- اشترك بـ **instagram_messages**
- اربط صفحة فيسبوك مع حساب إنستغرام **Professional**.

## اختبار محلي/سريع
```bash
npm i
cp .env.example .env
# عبّي القيم
npm run start
```
> الويبهوك يحتاج HTTPS عام. للاختبار المحلي استعمل Tunnel مثل ngrok.

## أدوات اختبار
- `test/ig_sample_event.json`: مثال حمولة Webhook.
- `test/post-sample.sh`: يرسل الحدث للسيرفر (للتأكد من عدم وقوع أخطاء parsing).
- `test/webhook-local.js`: سكربت Node بسيط للفحص.

## ملاحظات
- الطلبات تُخزن في `data.sqlite` في نفس المجلد.
- عدّل المنتجات من `products.json`.
- استعرض الطلبات: `/admin/orders` (JSON).