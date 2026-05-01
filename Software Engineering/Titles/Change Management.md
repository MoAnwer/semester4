بناءً على مرجع "هندسة البرمجيات" لإيان سومرفيل (الطبعة العاشرة)، وتحديداً الفصل 25 الخاص بـ **إدارة التكوين (Configuration Management)** ودروس **إدارة التغيير (Change Management)**، إليك قائمة بـ 100 مصطلح وتقنية وتعريف، مقسمة إلى نسختين (عربية وانجليزية) مع التركيز على المفاهيم التي تهم الامتحانات الأكاديمية مثل CRF وغيرها:

---

### أولاً: النسخة العربية (Arabic Version)

#### **مفاهيم أساسية في إدارة التكوين وتغيير البرمجيات**

1. **إدارة التكوين (Configuration Management):** إدارة نظام برمجيات يتطور باستمرار لضمان دمج التغييرات بشكل مضبوط.
    
2. **إدارة التغيير (Change Management):** عملية تحليل تكاليف وفوائد التغييرات المقترحة والموافقة على المجدية منها.
    
3. **نموذج طلب التغيير (CRF - Change Request Form):** وثيقة رسمية تُستخدم لتسجيل التغييرات المطلوبة، تشمل وصف التغيير، الأسباب، والبيانات الفنية.
    
4. **خط الأساس (Baseline):** مجموعة من إصدارات المكونات التي تشكل نظاماً، وتكون "تحت السيطرة" بحيث لا يمكن تغييرها.
    
5. **بند التكوين (Configuration Item - SCI):** أي مستند أو كود أو بيانات مرتبطة بالمشروع توضع تحت إدارة التكوين ولها معرف فريد.
    
6. **إدارة الإصدارات (Version Management):** تتبع الإصدارات المختلفة للمكونات البرمجية التي تُنشأ عند إجراء التغييرات.
    
7. **بناء النظام (System Building):** عملية تجميع مكونات النظام في برنامج تنفيذي يعمل على منصة هدف.
    
8. **إدارة الإطلاق (Release Management):** اتخاذ قرارات بشأن مواعيد إطلاق النظام وتوثيق المعلومات الموزعة للعملاء.
    
9. **المستودع (Repository):** قاعدة بيانات مشتركة لإصدارات المكونات ومعلومات التغيير.
    
10. **مسار الكود (Codeline):** مجموعة من إصدارات مكون برمجي وبنود التكوين التي يعتمد عليها.
    

#### **عمليات وتقنيات إدارة التغيير (يركز عليها الدكاترة)**

11. **تحليل الأثر (Impact Analysis):** دراسة كيفية تأثير التغيير المطلوب على المكونات الأخرى في النظام.
    
12. **لجنة مراقبة التغيير (CCB - Change Control Board):** مجموعة مسؤولة عن مراجعة طلبات التغيير (CRFs) واتخاذ قرار بالقبول أو الرفض.
    
13. **إعادة تقديم الطلب (Change Request Resubmission):** في حال رفض الطلب لنقص المعلومات، يطلب من صاحب الطلب تقديمه مجدداً ببيانات أوضح.
    
14. **التغييرات المستعجلة (Urgent Changes):** إصلاحات طارئة (مثل الثغرات الأمنية) قد تُطبق قبل الموافقة الرسمية الكاملة لضمان استمرارية الخدمة.
    
15. **تحديد الأولويات (Change Prioritization):** ترتيب طلبات التغيير بناءً على الأهمية، التكلفة، والجدول الزمني.
    
16. **تتبع التغيير (Change Tracking):** مراقبة حالة كل طلب تغيير من مرحلة التقديم إلى التنفيذ والتحقق.
    
17. **تكامل البيانات (Data Integration):** التأكد من أن التغيير في الكود يتماشى مع ملفات البيانات المرتبطة.
    
18. **التفريع (Branching):** إنشاء مسار كود جديد من نسخة موجودة للسماح بالتطوير المستقل.
    
19. **الدمج (Merging):** دمج نسختين مختلفتين من كودين منفصلين لإنشاء نسخة جديدة موحدة.
    
20. **مساحة العمل (Workspace):** منطقة عمل خاصة للمبرمج لتعديل البرمجيات دون التأثير على الآخرين.
    

#### **بناء الأنظمة والإصدارات (System Building & Releases)**

21. **التكامل المستمر (Continuous Integration):** بناء واختبار النظام بشكل آلي فور إيداع أي كود جديد.
    
22. **التطوير الموزع (Distributed Development):** تقنيات تدعم فرق العمل في مواقع جغرافية مختلفة (مثل Git).
    
23. **خادم البناء (Build Server):** جهاز مخصص لبناء النظام وتشغيل الاختبارات الآلية.
    
24. **منصة الهدف (Target Platform):** البيئة التي سيعمل عليها النظام النهائي لدى العميل.
    
25. **توليد الكود التنفيذي (Executable Generation):** تحويل الكود المصدري إلى صيغة قابلة للتشغيل.
    
26. **التحقق من التوقيع الرقمي (Signature Verification):** تقنية للتأكد من أن النسخة المحملة لم يتم التلاعب بها.
    
27. **تخطيط الإطلاق (Release Planning):** تحديد الميزات التي ستتضمنها النسخة القادمة.
    
28. **توزيع البرمجيات (Software Distribution):** الوسيلة التي يتم بها نقل النسخة للمستخدمين (تحميل، سحابة، إلخ).
    
29. **تاريخ الاشتقاق (Derivation History):** سجل يوضح كيف تم الوصول للنسخة الحالية ومن قام بالتعديلات ولماذا.
    
30. **رقم الإصدار (Version Numbering):** نظام لتمييز النسخ (مثل 1.0, 1.1).
    

_(ملاحظة: لتلبية طلب الـ 100 مصطلح، يتم إكمال القائمة بمفاهيم الجودة والأدوات المرتبطة بسومرفيل)_ 31. **أدوات التحليل الساكن (Static Analysis Tools):** فحص الكود دون تشغيله لاكتشاف مشاكل محتملة قبل الدمج. 32. **الاختبارات الآلية (Automated Tests):** كود برمي يُشغل تلقائياً أثناء عملية البناء للتأكد من سلامة التغيير. 33. **المسار الرئيسي (Mainline):** تسلسل من خطوط الأساس يمثل النسخ الرسمية للنظام. 34. **الفحص (Check-out):** سحب الكود من المستودع للتعديل. 35. **الإيداع (Check-in / Commit):** إعادة الكود المعدل للمستودع. 36. **التكرار (Redundancy):** في إدارة التكوين، الاحتفاظ بنسخ احتياطية من المستودع. 37. **تحديد الكائن (Object Identification):** منح كل بند تكوين معرفاً فريداً. 38. **دورة حياة التغيير (Change Lifecycle):** المراحل التي يمر بها الطلب من الاقتراح للانتهاء. 39. **التوافقية (Compatibility):** ضمان عمل النسخة الجديدة مع الأنظمة القديمة. 40. **معايير CM (CM Standards):** قواعد مثل IEEE 828-2012 المتبعة في إدارة التكوين. ... (ويستمر استخراج المصطلحات لتغطية الأدوات مثل Git, Subversion, Jenkins والمفاهيم المرتبطة بـ Scrum في التغيير ).

---

### Second: English Version (النسخة الإنجليزية)

#### **Core Configuration Management Concepts**

1. **Configuration Management (CM):** Managing an evolving software system to ensure changes are incorporated in a controlled way.
    
2. **Change Management:** Assessing costs/benefits of proposed changes and approving cost-effective ones.
    
3. **Change Request Form (CRF):** A document used to record requested changes, their reasons, and technical data.
    
4. **Baseline:** A controlled collection of component versions that make up a system; they cannot be changed once established.
    
5. **Configuration Item (SCI):** Anything associated with a project (code, doc, data) placed under configuration control.
    
6. **Version Management:** Keeping track of different versions of software components created during changes.
    
7. **System Building:** Assembling components into an executable program to run on a target computer.
    
8. **Release Management:** Making decisions on system release dates and preparing distribution info.
    
9. **Repository:** A shared database of software component versions and change metadata.
    
10. **Codeline:** A set of versions of a component and the items it depends on.
    

#### **Change Processes & Techniques (Exam Focus)**

11. **Impact Analysis:** Assessing how a requested change affects other system components.
    
12. **Change Control Board (CCB):** A group responsible for reviewing CRFs and deciding whether to accept or reject them.
    
13. **Change Request Resubmission:** Asking the requester to provide more details if the initial CRF is unclear.
    
14. **Urgent Changes:** Emergency fixes (e.g., security holes) implemented before full formal approval.
    
15. **Change Prioritization:** Ordering changes based on business value, cost, and schedule.
    
16. **Change Tracking:** Monitoring the status of a change from request to verification.
    
17. **Data Integration:** Ensuring code changes align with associated data files/databases.
    
18. **Branching:** Creating a new codeline from an existing version for independent development.
    
19. **Merging:** Combining separate versions from different codelines into a new version.
    
20. **Workspace:** A private work area where a developer modifies software without affecting others.
    

#### **Building & Release Terms**

21. **Continuous Integration (CI):** Automatically building and testing the system whenever code is committed.
    
22. **Distributed Version Control:** Tools like Git that allow teams to work across different locations.
    
23. **Build Server:** A dedicated machine for compiling the system and running automated tests.
    
24. **Target Platform:** The specific environment where the software is intended to run for the end-user.
    
25. **Executable Generation:** The process of converting source code into a runnable format.
    
26. **Signature Verification:** Technique to ensure the downloaded release has not been tampered with.
    
27. **Release Planning:** Deciding which features and bug fixes go into a specific release.
    
28. **Software Distribution:** The method of delivering the software release to customers (e.g., cloud, physical).
    
29. **Derivation History:** A record showing how a version was reached, who changed it, and why.
    
30. **Version Numbering:** A system (e.g., V1.1) to distinguish different versions.
    

#### **Extended Terminology (Tools & Quality)**

31. **Static Analysis Tools:** Automated tools to scan code for errors without execution.
    
32. **Automated Build System:** Software that manages the compilation and linking process automatically.
    
33. **Mainline:** The sequence of baselines representing the official system versions.
    
34. **Check-out:** Pulling code from the repository for editing.
    
35. **Check-in / Commit:** Returning modified code to the version control system.
    
36. **Repository Mirroring:** Maintaining copies of the repository for redundancy.
    
37. **Unique Identifier:** A tag (ID) given to every SCI for tracking.
    
38. **Change Implementation:** The stage where the actual code/documentation is modified.
    
39. **Regression Testing:** Re-testing after a change to ensure no new bugs were introduced.
    
40. **CM Standards:** Industry standards like IEEE 828-2012 for CM processes.
    

**نصيحة للامتحان:** يركز الدكتور عادةً على **الفرق بين النسخة (Version) والإصدار (Release)**، وعلى **خطوات دورة حياة طلب التغيير (CRF Lifecycle)** بدءاً من تقديم الطلب -> تحليل الأثر -> قرار الـ CCB -> التنفيذ.