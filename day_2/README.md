# 📚 Network Terms - Day 2: Professional Revision Guide

## مراجعة الأمن والشبكات - Network Security & Fundamentals

---

## 🌐 Network Segmentation & Connectivity Concepts

### مفاهيم التقسيم والربط

### 1. Subnet (الشبكة الفرعية)

**Basic Definition:**

- تقسيم منطقي لشبكة IP أكبر باستخدام Subnet Mask
- تقليل Broadcast Domain وتحسين الأداء
- مثال: شبكة 192.168.1.0/24 → تقسم إلى /25 (192.168.1.0/25 و 192.168.1.128/25)

**Security Focus:**

- أساس **Network Segmentation** الأمني
- عزل الشبكات الحساسة (الخوادم) في Subnet منفصل
- منع **Lateral Movement** للمهاجمين بعد الاختراق الأولي
- تطبيق مبدأ **Zero Trust** - كل subnet غير موثوق افتراضياً

---

### 2. Router (الموجه)

**Basic Definition:**

- جهاز Layer 3 يربط شبكات مختلفة (Subnets)
- يوجه حزم IP باستخدام Logical Address
- يحتوي على **Routing Table** لتحديد أفضل مسار
- **Default Gateway** للأجهزة في الشبكة المحلية

**Security Focus:**

- **نقطة التحكم الحدودية** (Boundary Control Point)
- هدف رئيسي للمهاجمين
- يتطلب تأمين قوي: ACLs، تحديثات منتظمة
- تعطيل الخدمات غير المستخدمة
- مراقبة Routing Tables لاكتشاف التلاعب

---

### 3. InterNetwork

**Basic Definition:**

- شبكة مكونة من عدة شبكات متصلة عبر Routers
- مثال: شبكة الشركة الكبيرة أو الإنترنت نفسه

**Security Focus:**

- تأمين نقاط الاتصال بين الشبكات
- استخدام **Firewalls** و **IPS/IDS**
- منع انتشار التهديدات من شبكة إلى أخرى

---

### 4. Internet

**Basic Definition:**

- أكبر InterNetwork في العالم
- الشبكة العالمية العامة ببروتوكول TCP/IP

**Security Focus:**

- **مصدر التهديدات الخارجية** الرئيسي
- **قناة الهجمات** المباشرة
- أي عنوان Public IP يتطلب حماية قوية

---

### 5. ISP (مزود خدمة الإنترنت)

**Basic Definition:**

- الشركة التي توفر الاتصال بالإنترنت
- توفر عنوان Public IP للاتصال العالمي
- أمثلة: Vodafone, Etisalat, Orange

**Security Focus:**

- فهم خدمات الحماية المتاحة (DDoS Protection)
- إمكانية الجدران النارية الافتراضية
- اعتبارات الخصوصية وتتبع الأنشطة

---

### 6. Intranet

**Basic Definition:**

- شبكة داخلية خاصة تستخدم تقنيات الإنترنت
- مقصورة على موظفي المؤسسة
- مثال: شبكة الملفات الداخلية للشركة

**Security Focus:**

- **Inbound Protection**: الحماية من الوصول الخارجي
- **Internal Audits**: التدقيق الداخلي المنتظم
- منع التهديدات الداخلية (Insider Threats)

---

### 7. Extranet

**Basic Definition:**

- جزء من Intranet يُفتح بأمان لأطراف خارجية موثوقة
- للشركاء، الموردين، أو العملاء المحددين

**Security Focus:**

- **أعلى مستويات الأمان مطلوبة**
- **VPNs** للاتصال الآمن
- **MFA (Multi-Factor Authentication)**
- فصل صارم عن باقي الـ Intranet

---

## 🖥️ Devices & Roles

### الأجهزة والأدوار

### 8. Workstation (محطة العمل)

**Basic Definition:**

- جهاز الكمبيوتر الذي يستخدمه المستخدم النهائي
- متصل بالشبكة لأداء المهام اليومية

**Security Focus:**

- **هدف سهل للمخترقين** (Phishing, Malware)
- يتطلب **Endpoint Protection** قوي
- تقييد امتيازات المستخدمين (Least Privilege)
- تحديثات أمان منتظمة

---

### 9. Client (العميل)

**Basic Definition:**

- **Client OS:** نظام تشغيل للاستخدام الشخصي (Windows 10/11, Linux)
- **Client Network:** جهاز يطلب خدمة من Server

**Security Focus:**

- نقطة الدخول الأولى في **Penetration Testing**
- **Initial Access** للمهاجمين
- يُستخدم كجسر للوصول إلى الخوادم
- تطبيق سياسات أمان صارمة

---

### 10. Server & Server Roles

**Basic Definition:**

- جهاز مخصص يوفر خدمات للـ Clients
- **أدوار متعددة:**
  - **File Server**: مشاركة الملفات
  - **Print Server**: إدارة الطابعات
  - **Web Server**: استضافة المواقع
  - **Mail Server**: البريد الإلكتروني
  - **DHCP Server**: توزيع عناوين IP
  - **DNS Server**: تحويل أسماء النطاقات

**Security Focus:**

- **الأصل الأكثر قيمة** (Most Critical Asset)
- يتطلب **Server Hardening** شامل
- مراقبة مستمرة (24/7 Monitoring)
- تطبيق مبدأ **Least Privilege**
- **متطلبات أمان خاصة لكل دور:**
  - DNS Server ← حماية من Cache Poisoning
  - Database Server ← حماية من SQL Injection
  - Web Server ← حماية من XSS, CSRF

---

## 🔑 Addressing & Routing

### العناوين والتوجيه

### 11. IPv4 Address

**Basic Definition:**

- عنوان منطقي 32 بت للتوجيه بين الشبكات
- مثال: 192.168.1.10
- يمكن أن يكون Static أو Dynamic (DHCP)

**Security Focus:**

- أساس تحديد **نطاق الاستكشاف** في PenTest
- **Reconnaissance** الأولي لتحديد الأهداف
- التمييز بين Public/Private IPs للتقييم الأمني

---

### 12. MAC Address

**Basic Definition:**

- عنوان فيزيائي 48 بت فريد لكل NIC
- مثال: 00:1A:2B:3C:4D:5E
- يُستخدم للتواصل في الشبكة المحلية

**Security Focus:**

- يُستغل في هجمات Layer 2:
  - **ARP Spoofing**: انتحال هوية الأجهزة
  - **MAC Flooding**: إغراق Switch بعناوين وهمية
- السيطرة على حركة المرور المحلية

---

### 13. Subnet Mask

**Basic Definition:**

- قيمة 32 بت تحدد جزء الشبكة وجزء الجهاز
- مثال: 255.255.255.0 (/24)
- حساب نطاق الشبكة الفرعية

**Security Focus:**

- **ضروري لحساب Scope Definition** في PenTest
- تحديد حدود الشبكة الفرعية للمسح الأمني
- فهم البنية الشبكية للتخطيط الأمني

---

### 14. Logical Address & Routing

**Basic Definition:**

- IPv4 = Logical Address
- Routing: توجيه البيانات بين الشبكات
- Router يستخدم Routing Table لاتخاذ القرارات

**Security Focus:**

- مراقبة **Routing Tables** أمر حيوي
- أي تعديل غير مصرح = إمكانية تسلل
- الكشف عن إعادة التوجيه الخبيث للبيانات

---

## 🔐 Security Focus Questions

### أسئلة التركيز الأمني

### 1. ARP Spoofing Attack

**السؤال:** كيف تربط هجمة ARP Spoofing بين Logical Address و Physical Address؟

**الإجابة:**

- تهاجم بروتوكول ARP في Layer 2
- تربط عنوان IP الضحية بعنوان MAC المهاجم
- تمكن المهاجم من كونه **Man-in-the-Middle** محلياً
- تحويل كل البيانات عبر جهاز المهاجم

### 2. Network Segmentation & Zero Trust

**السؤال:** كيف يساهم مفهوم Subnet في استراتيجية Zero Trust؟

**الإجابة:**

- Subnet = الآلية الأساسية للفصل الأمني
- Zero Trust: كل subnet غير موثوق افتراضياً
- يتطلب التحقق من الهوية قبل السماح بالاتصال
- Micro-segmentation لتقليل نطاق التأثير

### 3. Client vs Server Firewall Policies

**السؤال:** ما الفرق الرئيسي في سياسات Firewall بين Client و Server؟

**الإجابة:**

- **Client Firewall:**
  - السماح بالـ Outbound traffic
  - حظر معظم Inbound traffic
  - استثناءات قليلة ومحددة
- **Server Firewall:**
  - **تقييد شديد جداً**
  - السماح فقط بالبورتات المطلوبة للخدمة
  - مثال: Port 443 للـ HTTPS فقط
  - حظر كل ما عدا ذلك (Default Deny)

---

## 📝 Quick Review Checklist

### قائمة المراجعة السريعة

- [ ] فهم الفرق بين Physical و Logical Addressing
- [ ] إتقان حساب Subnets و نطاقاتها
- [ ] معرفة أدوار الـ Server المختلفة
- [ ] فهم مفهوم Network Segmentation أمنياً
- [ ] التمييز بين Intranet, Extranet, Internet
- [ ] معرفة نقاط الضعف في كل نوع جهاز
- [ ] فهم كيفية عمل Routing و أهميته الأمنية
- [ ] إتقان مفاهيم Client-Server Architecture

---

\*This revision guide combines fundamental networking concepts with practical cybersecurity applications for comprehensive understanding.
