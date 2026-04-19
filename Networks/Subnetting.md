---
tags:
  - networks
  - subnetting
---
تقسيم الشبكات (Subnetting) ببساطة هو عملية تقسيم شبكة كبيرة واحدة إلى شبكات أصغر لتنظيم المرور وزيادة الأمان [1, 8]. إليك الطريقة الأسهل لفهمها وحسابها دون تعقيد: [1, 2]

## 1. الفكرة الأساسية: العنوان يتكون من جزأين

كل عنوان IP (مثل `192.168.1.10`) يشبه عنوان المنزل؛ فهو يتكون من: [3, 4]

- جزء الشبكة (Network ID): يشبه اسم الشارع أو المدينة [11, 22].
- جزء الجهاز (Host ID): يشبه رقم المنزل [22, 23]. [5, 6, 7]

قناع الشبكة (Subnet Mask): هو الأداة التي تخبر الكمبيوتر أين ينتهي "اسم الشارع" ويبدأ "رقم المنزل" [2, 18]. [8, 9]

- رقم 255 يعني: "هذا الجزء هو اسم الشبكة، لا تلمسه" [18].
- رقم 0 يعني: "هذا الجزء مخصص للأجهزة، يمكنك تغييره" [18]. [9]

---

## 2. طريقة "الرقم السحري" (The Magic Number) للحساب السريع [3]

هذه أسهل طريقة لحساب نطاقات الشبكة ذهنياً [22, 25, 28]: [6, 10, 11]

1. اطرح الرقم الأخير في قناع الشبكة من 256:
    
    - إذا كان القناع `255.255.255.192`...
    - العملية: 256 - 192 = 64.
    - الرقم 64 هو "الرقم السحري" أو حجم القفزة [22, 24, 27].
    
2. حدد نطاقات الشبكة:
    
    - ابدأ دائماً من 0.
    - أضف الرقم السحري في كل مرة: 0، 64، 128، 192.
    - هذه هي بدايات شبكاتك الصغيرة (Subnet IDs) [22, 24]. [6, 12, 13]
    

---

## 3. قاعدة الـ (2-) الذهبية

في كل شبكة فرعية، هناك عنوانان لا يمكنك استخدامهما للأجهزة أبداً [2, 6, 23]: [4, 7, 8]

1. العنوان الأول: هو عنوان الشبكة نفسها (Network ID) [4, 13].
2. العنوان الأخير: هو عنوان البث (Broadcast Address) لإرسال البيانات للجميع [4, 13]. [14, 15]

- القاعدة: عدد الأجهزة المتاحة = (2 ^ عدد الأصفار في القناع) - 2 [2, 6, 34]. [3, 4, 8]

---

## 4. جدول المساعدة السريع (Cheat Sheet)

هذا الجدول يلخص أشهر التقسيمات لشبكة تبدأ بـ `192.168.1.0` (Class C) [22, 24, 30]: [6, 12, 16]

|القناع (CIDR) [3, 16, 17, 18, 19]|قناع الشبكة (Decimal)|الرقم السحري (القفزة)|عدد الأجهزة المتاحة|
|---|---|---|---|
|/24|255.255.255.0|256 (شبكة واحدة)|254 جهاز|
|/25|255.255.255.128|128|126 جهاز لكل شبكة|
|/26|255.255.255.192|64|62 جهاز لكل شبكة|
|/27|255.255.255.224|32|30 جهاز لكل شبكة|
|/30|255.255.255.252|4|جهازيْن فقط (للراوترات)|

## 5. مثال عملي سريع

إذا كان لديك العنوان `192.168.1.50/26`:

- بما أن /26 تعني القفزة هي 64 (من الجدول أعلاه).
- الشبكات هي: `0-63` ثم `64-127`... إلخ.
- رقمك (50) يقع في الشبكة الأولى التي تبدأ بـ .0 وتنتهي بـ .63.
- إذن: عنوان الشبكة: `192.168.1.0` | عنوان البث: `192.168.1.63` [25, 27]. [10, 13]

هل تريد مثالاً تطبيقياً على عدد معين من الأجهزة أو تقسيم شبكة معينة لديك؟

  

[1] [https://www.geeksforgeeks.org](https://www.geeksforgeeks.org/computer-networks/introduction-to-subnetting/)

[2] [https://infosecwriteups.com](https://infosecwriteups.com/subnetting-101-simple-guide-to-ip-addressing-0a1ecac6a0ef)

[3] [https://www.zframez.com](https://www.zframez.com/articles/networking-fundamentals/understanding-ip-addressing-cidr-subnet-masks-network-and-host-calculation)

[4] [https://thepower.education](https://thepower.education/en/blog/subnetting-what-is-it)

[5] [https://www.cbtnuggets.com](https://www.cbtnuggets.com/blog/technology/networking/networking-basics-what-is-ipv4-subnetting)

[6] [https://www.packetcoders.io](https://www.packetcoders.io/a-beginners-guide-to-subnetting/)

[7] [https://netest.in](https://netest.in/blogsPub/UnderstandingSubnetting.html)

[8] [https://medium.com](https://medium.com/@abidshafee/subnetting-made-easy-a-step-by-step-guide-8599fb235912)

[9] [https://www.kollmorgen.com](https://www.kollmorgen.com/en-us/developer-network/what-subnet-mask)

[10] [https://learningnetwork.cisco.com](https://learningnetwork.cisco.com/s/question/0D53i00000KszgrCAB/my-fastest-way-of-subnetting-through-mind)

[11] [https://www.reddit.com](https://www.reddit.com/r/ccna/comments/1auvd7t/any_tipsmethods_for_subnetting_quickly/)

[12] [https://ipcisco.com](https://ipcisco.com/lesson/ip-subnetting-and-subnetting-examples/)

[13] [https://tsmith6421.medium.com](https://tsmith6421.medium.com/tricks-for-simple-subnetting-fb5b9ef17d3)

[14] [https://www.youtube.com](https://www.youtube.com/watch?v=5-wlfAdcmFQ&t=117)

[15] [https://www.auvik.com](https://www.auvik.com/franklyit/blog/subnetting-primer/)

[16] [https://docs.netgate.com](https://docs.netgate.com/pfsense/en/latest/network/cidr.html)

[17] [https://dev.to](https://dev.to/574n13y/a-beginners-guide-to-subnetting-cidr-network-and-hosts-3a4l#:~:text=/24%20in%20CIDR%20translates%20to%20a%20subnet%20mask%20of%20255.255.%20255.0%20.)

[18] [https://www.9tut.com](https://www.9tut.com/subnetting-tutorial)

[19] [https://www.linkedin.com](https://www.linkedin.com/pulse/understanding-cidr-notation-subnet-masks-quick-guide-steven-wright-etewe#:~:text=In%20CIDR%20notation%2C%20a%20/25%20%28255.255.%20255.128%29,we%20will%20set%20in%20the%20fourth%20octet.)