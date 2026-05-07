# 🐧 دليل لينكس الشامل — من الصفر

![Linux](https://img.shields.io/badge/Linux-Guide-blue)
![Arabic](https://img.shields.io/badge/Language-Arabic-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
> 📖 Better reading experience on Notion:
> [Read on Notion](https://www.notion.so/35862bea50cd8040811de2759ffbdc0e)
> **ملاحظة:**  كل فصل مبني على اللي قبله.
> 

---

# 📖 الفصل الأول: من أين جاء لينكس؟ — القصة الكاملة

## 1.1 البداية: عالم يونكس (Unix)

في الستينات، كانت الحواسيب ضخمة زي الغرف وغالية جدا. شركة **Bell Labs** (تابعة لـ AT&T) كانت بتطور نظام اسمه **Multics**، لكن المشروع فشل وكان معقد أكتر من اللازم.

سنة **1969**، قرر اتنين مهندسين اسمهم **Ken Thompson** و**Dennis Ritchie** يبدأوا من الصفر. عملوا OS صغير وبسيط على جهاز قديم اسمه PDP-7، وسموه **Unix** — كـ joke على اسم Multics

```
Timeline:
1969 → Unix اتكتب بلغة Assembly على PDP-7
1972 → Dennis Ritchie اخترع لغة C
1973 → Unix أعيد كتابته بلغة C 
1975 → AT&T بدأت توزع Unix للجامعات
```

### ليه لغة C كانت ثورة؟

قبل C، كان كل نظام تشغيل بيتكتب لمعالج معين (Assembly). لما Unix اتكتب بـ C، بقى يشتغل على أي جهاز بس بتعمل compile — ده كان تحول ضخم في تاريخ الحوسبة.

---

## 1.2 ريتشارد ستالمان و ال Open Source

في **1983**، مبرمج اسمه **Richard Stallman** في MIT كان زعلان جداً — ليه؟

لأن شركة Xerox كانت عندها طابعة بـ software مغلق، ولما حاول يصلح بـ bug فيها، مقدرش لأن الكود مش متاح فقرر يعمل حاجة ضد ده.

أعلن عن مشروع **GNU** (بتتقرا : "g-new") — وده اختصار ساخر يعني: **GNU's Not Unix**

**هدف GNU:**

- يكتب نظام تشغيل كامل مجاني ومفتوح المصدر
- أي حد يقدر يقرأ الكود ويعدله ويوزعه

**إنجازات GNU المهمة:**

- `GCC` — أقوى compiler في التاريخ (لسه بنستخدمه لحد دلوقتي)
- `Bash` — الـ shell
- `Emacs` و `GDB` وعشرات الأدوات

**لكن في مشكلة واحدة:** GNU مكانش عنده **kernel** (قلب النظام)! كانوا بيشتغلوا على واحد اسمه Hurd، بس فضل بطيء وما اكتملش.

---

## 1.3 لينوس تورفالدز والكرنل 🇫🇮

**21 أغسطس 1991**

طالب فنلندي عنده **21 سنة** اسمه **Linus Benedict Torvalds** كان في جامعة هلسنكي بيدرس علوم الحاسب. اشترى كمبيوتر Intel 386 جديد، وكان حابب يستخدم Unix عليه. الـ Unix التجاري كان غالي، وكان في نظام صغير اسمه **Minix** للتعليم فقط.

قرر Linus يكتب kernel خاص بيه، وكتب على منتدى تكنولوجي:

> *"أنا بعمل نظام تشغيل مجاني (بس مجرد هواية، مش هيبقى كبير أو محترف زي GNU) لأجهزة 386/486..."*
> 

بعد شهرين، **25 أغسطس 1991**، نزل Linux kernel نسخة 0.01.

```
Linux Timeline:
1991 (v0.01) → أول نسخة، 10,239 سطر كود
1994 (v1.0)  → أول نسخة رسمية مستقرة
2003 (v2.6)  → دخل لكل السيرفرات الكبيرة
2023 (v6.x)  → 27+ مليون سطر كود، 4000+ مطور
```

### التسمية "Linux"

كان Linus Torvalds عايز يسمي النظام **Freax**

(دمج بين: **Free + Freak + Unix**)

لكن صاحبه Ari Lemmke، وهو بيرفع الكود على الـ server، عجبه اسم **Linux** أكتر فسمّاه كده من غير ما يرجعله

---

## 1.4 GNU + Linux = نظام كامل 💡

لما Linux kernel اتجمع مع أدوات GNU، بقى عندنا نظام تشغيل كامل

```
GNU Tools (Stallman)  +  Linux Kernel (Torvalds) = GNU/Linux
        ↓                        ↓
               
        ↓                        ↓
        
														               قلب النظام                    أدوات وبرامج
      
```

> **ملاحظة:** ده سبب مناقشة طويلة — Stallman بيصر على التسمية "GNU/Linux" مش "Linux" فقط، لأن GNU جاب معظم الأدوات. لكن الناس في الغالب بتقول "Linux" بس
> 

---

## 1.5 التوزيعات (Distributions) — إيه الفرق؟

الKernel هو القلب فقط. التوزيعات هي اللي بتاخد الـ الكيرنل وتضيف عليه أدوات وواجهة وبرامج عشان يبقى قابل للاستخدام.

| التوزيعة | سنة الإنشاء | مناسبة لـ | الشركة/المجتمع |
| --- | --- | --- | --- |
| **Slackware** | 1993 | المحترفين القدام | Patrick Volkerding |
| **Debian** | 1993 | الاستقرار والسيرفرات | مجتمع مفتوح |
| **Red Hat** | 1994 | الشركات والمؤسسات | Red Hat (IBM) |
| **Ubuntu** | 2004 | المبتدئين، سطح المكتب | Canonical |
| **Arch** | 2002 | المتقدمين، التخصيص | مجتمع |
| **Kali** | 2013 | الأمن السيبراني | Offensive Security |
| **Fedora** | 2003 | المطورين | Red Hat |
| **CentOS/RHEL** | 2004 | سيرفرات الشركات | Red Hat |

---

## 1.6 لينكس في الحياة

مش بس على الكمبيوتر لينكس موجود في:

- **أندرويد** — نظام Android مبني على Linux kernel
- **الإنترنت** — 96% من السيرفرات تشغّل لينكس
- الكلاود — AWS, Google Cloud, Azure — كلهم لينكس
- **الفضاء** — محطة الفضاء الدولية (ISS) تشغّل Linux
- **السيارات** — Tesla وكتير من السيارات الذكية
- **الأجهزة** — Smart TVs, Routers, Raspberry Pi
- **الألعاب** — Steam Deck بتشغّل Linux (SteamOS)
- **العلوم** — كل الـ supercomputers في العالم!

---

# 🗂️ الفصل الثاني: بنية نظام الملفات

## 2.1 الفكرة الأساسية

في لينكس، **كل شيء ملف** — حتى الأجهزة (زي USB) والعمليات والشبكة. ده المبدأ الأساسي اللي Unix اتبنى عليه.

نظام الملفات بيبدأ من نقطة واحدة: `/` (الجذر أو Root). مفيش حروف زي C:\ أو D:\  — في شجرة واحدة بس.

```
/
├── home/          ← مجلدات المستخدمين
│   └── eiad/      ← مجلدك الشخصي (~)
│       ├── Documents/
│       ├── Downloads/
│       └── .bashrc
├── etc/           ← إعدادات النظام
├── bin/           ← أوامر ضرورية للنظام
├── sbin/          ← أوامر للـ admin فقط
├── usr/           ← برامج المستخدمين
│   ├── bin/       ← معظم البرامج هنا
│   └── lib/       ← المكتبات
├── var/           ← ملفات بتتغير (logs, cache)
│   └── log/       ← كل logs النظام
├── tmp/           ← ملفات مؤقتة (بتتمسح عند Reboot)
├── dev/           ← الأجهزة (كأنها ملفات)
│   ├── sda        ← أول قرص صلب
│   └── null       ← "سلة المهملات" الخاصة بلينكس
├── proc/          ← معلومات العمليات الشغّالة (Virtual)
├── sys/           ← معلومات الـ hardware (Virtual)
├── mnt/           ← نقاط تركيب الأقراص المؤقتة
├── media/         ← USB وأقراص خارجية
├── boot/          ← ملفات الإقلاع (Bootloader, Kernel)
├── lib/           ← المكتبات الأساسية
├── opt/           ← برامج خارجية (زي Chrome مثلاً)
└── root/          ← مجلد المستخدم root (مش زي /home)
```

## 2.2 شرح المجلدات المهمة

### `/home` — البيت

كل مستخدم عنده مجلد في `/home/username`. ده هو المكان الوحيد اللي تعمل فيه اللي تحب من غير ما تحتاج صلاحيات.

**اختصار مهم:** `~` تعني مجلدك الشخصي دايما.

```bash
cd ~          # روح لمجلدك
cd ~/Desktop  # روح للـ Desktop
echo $HOME    # يطبع المسار الكامل لمجلدك
```

### `/etc` — قلب الإعدادات

كل إعدادات النظام هنا. الاسم جاء من "et cetera" (وغيره)، لكن بيُقال إنه اختصار لـ "Editable Text Configuration".

```bash
/etc/hostname        # اسم جهازك
/etc/passwd          # معلومات المستخدمين
/etc/hosts           # ملف DNS محلي
/etc/fstab           # الأقراص والـ mount points
/etc/crontab         # المهام المجدولة
/etc/ssh/sshd_config # إعدادات SSH
/etc/apt/sources.list# مصادر البرامج (Ubuntu/Debian)
```

### `/var` — البيانات المتغيرة

Log files، databases، cache، mail — كل اللي بيكبر مع الوقت.

```bash
/var/log/syslog      # log النظام الرئيسي
/var/log/auth.log    # محاولات تسجيل الدخول
/var/log/apt/        # سجل تنصيب البرامج
/var/cache/apt/      # ملفات الـ packages المحملة
```

### `/proc` — النظام الحي

مش مجلد حقيقي على الهارد. ده virtual filesystem بيعرض معلومات النظام في الوقت الحقيقي.

```bash
cat /proc/cpuinfo    # معلومات المعالج
cat /proc/meminfo    # معلومات الرام
cat /proc/version    # نسخة الـ kernel
ls /proc/            # كل العمليات الشغالة برقمها
```

---

# ⌨️ الفصل الثالث: الأوامر الأساسية

## 3.1 التنقل في النظام

### `pwd` — Print Working Directory

```bash
$ pwd
/home/eiad/projects
```

دايماً ابدأ بـ `pwd` لو مش عارف إنت فين.

### `ls` — List Directory Contents

```bash
$ ls                    # عرض المحتويات
$ ls -l                 # عرض تفصيلي مع الصلاحيات
$ ls -a                 # عرض الملفات المخفية (بتبدأ بـ.)
$ ls -la                # تفصيلي + مخفية
$ ls -lh                # بـ file sizes مقروءة (KB, MB) h ل human
$ ls -lt                # مرتبة بتاريخ التعديل
$ ls -R                 # عرض كل المجلدات الداخلية
$ ls /etc               # عرض مجلد معين
$ ls *.txt              # عرض ملفات txt فقط
```

**فهم ناتج `ls -la`:**

```
drwxr-xr-x  2 eiad eiad 4096 Jan 15 10:30 projects
│││││││││  │ │    │    │    │      │     └── File name
│││││││││  │ │    │    │    │      └──────── Last modified date
│││││││││  │ │    │    │    └─────────────── File size (bytes)
│││││││││  │ │    │    └──────────────────── Group
│││││││││  │ │    └───────────────────────── Owner
│││││││││  │ └────────────────────────────── Hard links count
│└─────────┴───────────────────────────────── Permissions
└──────────────────────────────────────────── File type

File type:
d = Directory
- = Regular file
l = Symbolic link

Permissions:
r = Read
w = Write
x = Execute
```

### `cd` — Change Directory

```bash
$ cd /home/eiad/projects   # انتقل لمسار كامل (Absolute)
$ cd projects              # انتقل لمجلد داخل الحالي (Relative)
$ cd ..                    # ارجع مجلد للخلف
$ cd ../..                 # ارجع مجلدين للخلف
$ cd ~                     # روح لمجلدك الشخصي
$ cd -                     # روح للمجلد اللي كنت فيه قبل كده
$ cd /                     # روح للروت
```

> 💡 **Tip:** اضغط `Tab` للإكمال التلقائي — لينكس هيكمل اسم المجلد أو الملف لوحده!
> 

---

## 3.2 إدارة الملفات والمجلدات

### `mkdir` — Make Directory

```bash
$ mkdir projects                    # إنشاء مجلد
$ mkdir -p a/b/c                    # إنشاء مسار متداخل دفعة واحدة
$ mkdir project_{1..5}              # إنشاء مجلدات: project_1, 2, 3, 4, 5
$ mkdir "My Project"                # اسم فيه مسافة (استخدم quotes)
```

### `touch` — إنشاء ملف فاضي / تحديث التاريخ

```bash
$ touch notes.txt                   # إنشاء ملف جديد
$ touch file1.txt file2.txt         # إنشاء أكتر من ملف
$ touch {jan,feb,mar}_report.txt    # إنشاء jan_report.txt, feb_report.txt, ...
```

### `cp` — Copy

```bash
$ cp file.txt copy.txt              # نسخ ملف
$ cp file.txt /tmp/                 # نسخ لمجلد تاني
$ cp -r folder/ backup/             # نسخ مجلد كامل (-r = recursive)
$ cp -i file.txt dest/              # يسألك قبل الاستبدال (-i = interactive)
$ cp -p file.txt dest/              # يحافظ على الصلاحيات والتاريخ (-p = preserve)
```

### `mv` — Move / Rename

```bash
$ mv old.txt new.txt                # إعادة تسمية
$ mv file.txt /tmp/                 # نقل لمكان تاني
$ mv folder/ /home/eiad/backup/     # نقل مجلد كامل
$ mv *.log /var/log/archive/        # نقل كل ملفات log
```

### `rm` — Remove (⚠️ خطير — مفيش Recycle Bin!)

```bash
$ rm file.txt                       # حذف ملف
$ rm -i file.txt                    # يسألك تأكيد قبل الحذف
$ rm -r folder/                     # حذف مجلد وكل محتوياته
$ rm -rf folder/                    # حذف قسري بدون أسئلة (خطير جداً!)
$ rm *.tmp                          # حذف كل ملفات .tmp
```

> ⚠️ **تحذير:** `rm -rf /` = حذف كل النظام! لينكس مش هيسألك. اتأكد دايماً قبل ما تستخدم rm -rf.
> 

---

## 3.3 عرض محتوى الملفات

### `cat` — Concatenate (عرض ملف)

```bash
$ cat notes.txt                     # عرض محتوى الملف
$ cat -n notes.txt                  # مع أرقام الأسطر
$ cat file1.txt file2.txt           # دمج ملفين وعرضهم
$ cat file1.txt file2.txt > merged.txt  # دمج وحفظ في ملف جديد
```

### `less` و `more` — للملفات الكبيرة

```bash
$ less /var/log/syslog              # View a large file (with scrolling)

# Inside less:
# Space = Next page     |  b = Previous page
# /word = Search        |  q = Quit
# G = End of file       |  g = Start of file
```

### `head` و `tail` — جزء من الملف

```bash
$ head file.txt                     # أول 10 أسطر
$ head -n 20 file.txt               # أول 20 سطر
$ tail file.txt                     # آخر 10 أسطر
$ tail -n 50 file.txt               # آخر 50 سطر
$ tail -f /var/log/syslog           # عرض مباشر وهو بيتحدث (مفيد للـ logs!)
```

### `grep` — البحث في الملفات

```bash
$ grep "error" syslog               # البحث عن كلمة
$ grep -i "error" syslog            # بحث بدون حساسية للحروف الكبيرة
$ grep -n "error" syslog            # مع أرقام الأسطر
$ grep -r "TODO" ./                 # بحث في كل الملفات
$ grep -v "error" syslog            # عرض الأسطر اللي مش فيها الكلمة
$ grep "^#" config.txt              # الأسطر اللي بتبدأ بـ #
$ grep -c "error" syslog            # عدد مرات التكرار
$ ps aux | grep python              # دمج مع أوامر أخرى
```

---

## 3.4 ربط الأوامر (Pipes و Redirection)

### `|` — الـ Pipe (بيربط الأوامر)

```bash
$ ls -la | grep ".txt"              # اعرض ls واعمل فيه grep
$ cat file.txt | sort | uniq        # اعرض → رتب → شيل المكرر
$ ps aux | grep firefox | wc -l     # عدد processes firefox
```

### `>` و `>>` — إعادة توجيه الناتج

```bash
$ echo "مرحبا" > file.txt           # كتابة في ملف (يمسح القديم)
$ echo "سطر جديد" >> file.txt       # إضافة في نهاية الملف
$ ls -la > list.txt                 # حفظ ناتج ls في ملف
$ cat /etc/passwd > /tmp/backup.txt # نسخ ملف بطريقة تانية
$ grep "error" syslog > errors.txt  # حفظ نتايج البحث
```

### `2>` — إعادة توجيه الأخطاء

```bash
$ command 2> errors.log             # حفظ الايرورز في ملف
$ command > output.txt 2>&1         # حفظ الناتج والايرورز مع بعض
$ command > /dev/null 2>&1          # تجاهل كل ناتج الأمر
```

---

## 3.5 أوامر النصوص المتقدمة

### `sort` — الترتيب

```bash
$ sort names.txt                    # ترتيب أبجدي
$ sort -r names.txt                 # ترتيب عكسي
$ sort -n numbers.txt               # ترتيب رقمي
$ sort -k2 file.txt                 # ترتيب حسب العمود التاني
```

### `wc` — عد الكلمات والأسطر

```bash
$ wc file.txt                       # أسطر، كلمات، حروف
$ wc -l file.txt                    # عدد الأسطر 
$ wc -w file.txt                    # عدد الكلمات 
$ ls | wc -l                        # عدد الملفات في المجلد
```

### `sed` — تعديل النصوص

```bash
$ sed 's/قديم/جديد/' file.txt       # استبدال أول match في كل سطر
$ sed 's/قديم/جديد/g' file.txt      # استبدال كل اللي بيماتش
$ sed -i 's/error/ERROR/g' log.txt  # التعديل داخل الملف بشكل فعلي مش مجرد preview
$ sed '/^#/d' config.txt            # حذف أسطر التعليقات
```

### `awk` — معالجة الأعمدة

```bash
$ awk '{print $1}' file.txt         # طبع العمود الأول
$ awk '{print $1, $3}' file.txt     # طبع العمود الأول والتالت
$ awk -F: '{print $1}' /etc/passwd  # استخدام : كـ separator
$ awk 'NR>5' file.txt               # عرض من السطر 6 فما بعد
```

---

# 🔐 الفصل الرابع: الصلاحيات

## 4.1 فهم نظام الصلاحيات

لما بتكتب `ls -l` بتشوف حاجة زي:

```
-rwxr-xr--  1  eiad  eiad  4096  Jan 15  script.sh
```

### قراءة الصلاحيات:

```
-rwxr-xr--
│└┴┴┘└┴┴┘└┴┴┘
│   │    │
│   │    └──── Others: r--  = Read only
│   └───────── Group:  r-x  = Read + Execute
└───────────── Owner:  rwx  = Read + Write + Execute

First character:
- = Regular file
d = Directory
l = Symbolic link
```

| الحرف | المعنى | على ملف | على مجلد |
| --- | --- | --- | --- |
| `r` | Read | قراءة الملف | عرض المحتويات |
| `w` | Write | تعديل الملف | إضافة/حذف ملفات |
| `x` | Execute | تشغيل كبرنامج | الدخول للمجلد |
| `-` | بدون صلاحية | — | — |

## 4.2 الأرقام الثماني للصلاحيات (Octal)

```
r = 4
w = 2
x = 1
─────────
rwx = 4+2+1 = 7  (كامل)
rw- = 4+2+0 = 6  (قراءة وكتابة)
r-x = 4+0+1 = 5  (قراءة وتنفيذ)
r-- = 4+0+0 = 4  (قراءة فقط)
--- = 0+0+0 = 0  (لا شيء)
```

**الأرقام الشائعة:**

| الرقم | Owner | Group | Others | الاستخدام |
| --- | --- | --- | --- | --- |
| **777** | rwx | rwx | rwx | خطير — الكل يعمل أي حاجة |
| **755** | rwx | r-x | r-x | برامج وسكريبتات |
| **644** | rw- | r-- | r-- | ملفات عادية |
| **600** | rw- | --- | --- | ملفات سرية (مثل .ssh/id_rsa) |
| **700** | rwx | --- | --- | مجلدات خاصة جداً |

## 4.3 أوامر الصلاحيات

### `chmod` — تغيير الصلاحيات

```bash
# بالأرقام (Numeric)
$ chmod 755 script.sh
$ chmod 644 config.txt
$ chmod 600 ~/.ssh/id_rsa

# بالحروف (Symbolic) — أسهل للفهم
$ chmod +x script.sh         # إضافة تنفيذ للكل
$ chmod -w file.txt          # إزالة الكتابة من الكل
$ chmod u+x script.sh        # إضافة تنفيذ للمالك فقط
$ chmod g+w folder/          # إضافة كتابة للمجموعة
$ chmod o-r secret.txt       # إزالة قراءة من البقية
$ chmod a+r public.txt       # إضافة قراءة للكل (a = all)

# على مجلدات كاملة
$ chmod -R 755 /var/www/     # -R = تطبيق على كل المحتويات
```

### `chown` — تغيير المالك

```bash
$ chown eiad file.txt              # تغيير المالك
$ chown eiad:developers file.txt   # تغيير المالك والمجموعة
$ chown -R eiad:eiad ~/projects/   # على مجلد كامل
$ sudo chown root /etc/config.txt  # تحويل الملكية للـ root
```

### `chgrp` — تغيير المجموعة

```bash
$ chgrp developers project/
$ chgrp -R www-data /var/www/
```

---

# 📦 الفصل الخامس: إدارة الحزم

## 5.1 نظام APT (Ubuntu / Debian)

APT = Advanced Package Tool — النظام المستخدم في Ubuntu وDebian وكل مشتقاتهم.

### التحديث والبحث

```bash
$ sudo apt update                   # تحديث قائمة الحزم (مش البرامج نفسها)
$ sudo apt upgrade                  # تحديث كل البرامج المنصبة
$ sudo apt full-upgrade             # تحديث شامل مع حذف القديم
$ sudo apt search python            # بحث عن حزمة
$ apt show python3                  # معلومات عن حزمة
$ apt list --installed              # البرامج المنصبة
$ apt list --upgradable             # البرامج اللي محتاجة تحديث
```

### التنصيب والحذف

```bash
$ sudo apt install git              # تنصيب برنامج
$ sudo apt install git vim curl wget  # تنصيب كذا برنامج دفعة واحدة
$ sudo apt remove vim               # حذف برنامج (يسيب الإعدادات)
$ sudo apt purge vim                # حذف كامل مع الإعدادات
$ sudo apt autoremove               # حذف الحزم غير المستخدمة
$ sudo apt clean                    # مسح cache التنصيب
```

### إصلاح المشاكل

```bash
$ sudo apt --fix-broken install     # إصلاح تنصيبات ناقصة
$ sudo dpkg --configure -a          # إكمال تنصيبات معلقة
$ sudo apt-get install -f           # إصلاح dependencies
```

## 5.2 نظام DNF/YUM (Red Hat / Fedora / CentOS)

```bash
$ sudo dnf update                   # تحديث
$ sudo dnf install httpd            # تنصيب
$ sudo dnf remove httpd             # حذف
$ sudo dnf search nginx             # بحث
$ sudo dnf list installed           # المنصبات
```

## 5.3 تنصيب خارج الـ Repository

### من ملف .deb

```bash
$ sudo dpkg -i package.deb
$ sudo apt install -f               # إصلاح dependencies بعد التنصيب
```

### من الـ Source Code

```bash
$ ./configure
$ make
$ sudo make install
```

### Snap Packages

```bash
$ sudo snap install vlc             # تنصيب
$ snap list                         # المنصبات
$ sudo snap remove vlc              # حذف
```

---

# 🔑 الفصل السادس: إدارة المستخدمين

## 6.1 sudo — السلاح السري

**sudo** = Super User do — بيديك صلاحيات الـ root مؤقتاً.

```bash
$ sudo command                      # تنفيذ أمر بصلاحيات root
$ sudo -i                           # فتح shell كـ root (خطر)
$ sudo su -                         # التحول لـ root user
$ sudo -l                           # شوف إيه اللي مسموحلك تعمله
$ sudo !!                           # تكرار آخر أمر مع sudo
```

> ⚠️ **مبدأ أساسي:** استخدم sudo بس لما تحتاجه. البرامج العادية شغلها من غير sudo.
> 

## 6.2 إدارة المستخدمين

```bash
$ whoami                            # مين انت
$ who                               # مين متسجل دلوقتي
$ id                                # معرفك (UID, GID)
$ id username                       # معرف مستخدم معين

# إضافة وحذف مستخدمين
$ sudo adduser ahmed                # إضافة مستخدم (الطريقة السهلة)
$ sudo useradd -m -s /bin/bash ali  # إضافة مستخدم (الطريقة التفصيلية)
$ sudo deluser ahmed                # حذف مستخدم
$ sudo deluser --remove-home ahmed  # حذف مع مجلده

# كلمات المرور
$ passwd                            # تغيير كلمة مرورك
$ sudo passwd ahmed                 # تغيير كلمة مرور مستخدم

# المجموعات
$ groups                            # مجموعاتك
$ sudo usermod -aG docker eiad      # إضافة مستخدم لمجموعة
$ sudo usermod -aG sudo ahmed       # منح صلاحيات sudo
```

---

# ⚙️ الفصل السابع: إدارة العمليات

## 7.1 عرض العمليات

### `ps` — Process Status

```bash
$ ps                                # عمليات الـ session الحالي
$ ps aux                            # كل العمليات بالتفصيل
$ ps aux | grep firefox             # ابحث عن عملية معينة
$ ps -p 1234                        # عرض عملية برقمها
$ ps --forest                       # عرض هرمي (شجرة العمليات)
```

**فهم ناتج `ps aux`:**

```
USER    PID   %CPU  %MEM   VSZ    RSS    STAT  COMMAND
eiad    1234   0.5   2.3  12345  45678   Sl    /usr/bin/firefox
│       │      │     │      │      │      │          └── Command
│       │      │     │      │      │      └────────── Process state
│       │      │     │      │      └───────────────── Physical RAM used (RSS)
│       │      │     │      └──────────────────────── Virtual memory size (VSZ)
│       │      │     └─────────────────────────────── Memory usage percentage
│       │      └───────────────────────────────────── CPU usage percentage
│       └──────────────────────────────────────────── Process ID (PID)
└──────────────────────────────────────────────────── User
```

**حالات العمليات:**

- `R` = Running (شغّالة)
- `S` = Sleeping (نايمة تستنى input)
- `D` = Disk Sleep (منتظرة disk)
- `Z` = Zombie (ماتت بس لسه موجودة!)
- `T` = Stopped (موقوفة)

### `top` و `htop`

```bash
$ top                               # Real-time process monitoring (built-in)
$ htop                              # Better interactive version (install separately)
وفيه btop احلى برضو
# Inside top/htop:
# q = Quit
# k = Kill process
# r = Renice (change process priority)

# Sorting:
# M = Sort by RAM usage
# P = Sort by CPU usage
```

```bash
$ sudo apt install htop             # تنصيب htop
$ htop                              # مراقبة تفاعلية
```

## 7.2 إيقاف العمليات

### `kill` — إرسال Signal

```bash
$ kill 1234                         # إيقاف عملية (SIGTERM - ودي)
$ kill -9 1234                      # إيقاف قسري (SIGKILL - بدون رجعة)
$ kill -l                           # قائمة كل الـ signals

$ pkill firefox                     # إيقاف بالاسم
$ pkill -9 chrome                   # إيقاف قسري بالاسم
$ killall python3                   # إيقاف كل العمليات بنفس الاسم
```

**Signals مهمة:**

| Signal | Name | Meaning |
| --- | --- | --- |
| 1 | SIGHUP | Reload configuration |
| 2 | SIGINT | Interrupt (like `Ctrl + C`) |
| 9 | SIGKILL | Force kill immediately |
| 15 | SIGTERM | Graceful termination request (default) |

## 7.3 العمليات في الخلفية

```bash
$ command &                         # Run command in background

$ sleep 100 &                       # Example
[1] 5678                            # [Job number] PID

$ jobs                              # Show background jobs

$ fg                                # Bring last job to foreground
$ fg %1                             # Bring job 1 to foreground

$ bg %1                             # Resume job 1 in background

# Keyboard shortcuts:
# Ctrl+Z = Suspend current process
# Ctrl+C = Terminate current process
# Ctrl+D = Close terminal / EOF

$ nohup command &                   # Keep running after terminal closes

$ disown %1                         # Detach job 1 from terminal
```

---

# 🌐 الفصل الثامن: الشبكة

## 8.1 أوامر الشبكة الأساسية

### `ip` — معلومات الشبكة (الحديثة)

```bash
$ ip addr                           # كل الـ interfaces والـ IPs
$ ip addr show eth0                 # interface معين
$ ip route                          # جدول التوجيه
$ ip route show default             # الـ gateway
$ ip link                           # حالة الـ interfaces
```

### `ping` — اختبار الاتصال

```bash
$ ping google.com                   # اختبار مستمر
$ ping -c 4 google.com              # 4 packets بس
$ ping -i 0.5 google.com            # كل نص ثانية
$ ping6 google.com                  # IPv6
```

### `ss` و `netstat` — البورتات المفتوحة

```bash
$ ss -tulpn                         # كل البورتات المفتوحة
# t = TCP  u = UDP  l = Listening  p = Process  n = Numbers

$ netstat -tulpn                    # نفس الحاجة (قديمة)
$ ss -s                             # إحصائيات الشبكة
```

## 8.2 تحميل الملفات

### `wget` — تحميل ملفات

```bash
$ wget https://example.com/file.zip            # تحميل عادي
$ wget -O output.zip https://example.com/file  # تحديد اسم الملف
$ wget -c https://example.com/file.zip         # استكمال تحميل ناقص
$ wget -r https://example.com/                 # تحميل موقع كامل
```

### `curl` — أقوى وأمرن

```bash
$ curl https://api.example.com/data           # GET request
$ curl -X POST https://api.example.com/data   # POST request
$ curl -H "Authorization: Bearer TOKEN" url   # مع header
$ curl -d '{"key":"value"}' -H "Content-Type: application/json" url
$ curl -o file.zip https://example.com/file   # حفظ في ملف
$ curl -L url                                 # تتبع الـ redirects
```

## 8.3 SSH — الاتصال الآمن

```bash
$ ssh user@hostname                            # اتصال عادي
$ ssh user@192.168.1.50                        # بالـ IP
$ ssh -p 2222 user@hostname                    # بورت مختلف
$ ssh -i ~/.ssh/mykey.pem user@hostname        # بـ key معين

# نقل ملفات عبر SSH
$ scp file.txt user@host:/remote/path/         # نقل ملف
$ scp user@host:/remote/file.txt ./            # جلب ملف
$ scp -r folder/ user@host:/remote/            # نقل مجلد كامل
$ rsync -avz folder/ user@host:/remote/        # مزامنة (أذكى من scp)
```

### إعداد SSH Key (بدل كلمة المرور)

```bash
$ ssh-keygen -t ed25519 -C "eiad@example.com"  # إنشاء Key
$ ssh-copy-id user@hostname                     # نقل الـ Public Key للسيرفر
$ ssh user@hostname                             # الاتصال بدون كلمة مرور!
```

---

# 📝 الفصل التاسع: المحررات النصية

## 9.1 nano — الأسهل للمبتدئين

```bash
$ nano file.txt                     # فتح ملف
```

**اختصارات nano:**

| Shortcut | Action |
| --- | --- |
| `Ctrl + O` | Save file |
| `Ctrl + X` | Exit nano |
| `Ctrl + W` | Search |
| `Ctrl + K` | Cut current line |
| `Ctrl + U` | Paste |

## 9.2 vim — اللي بجد بقى

vim بيشتغل بـ modes:

- **Normal Mode** (الافتراضي) — للتنقل والأوامر
- **Insert Mode** — للكتابة
- **Visual Mode** — للتحديد
- **Command Mode** — للأوامر المتقدمة

```bash
$ vim file.txt                      # فتح ملف
```

**اختصارات vim الأساسية:**

```
# Enter Insert Mode:
i = Insert before cursor      |  a = Insert after cursor
I = Insert at line start      |  A = Insert at line end
o = New line below            |  O = New line above

# In Normal Mode:
h j k l = Left, Down, Up, Right
w = Next word                 |  b = Previous word
0 = Start of line             |  $ = End of line
gg = Start of file            |  G = End of file
dd = Delete line              |  yy = Copy (yank) line
p = Paste                     |  u = Undo

# Exit / Save:
:w   = Save
:q   = Quit
:wq  = Save and quit
:q!  = Quit without saving

# Search:
/word = Search forward        |  ?word = Search backward
n = Next match                |  N = Previous match

# Replace:
:%s/old/new/g = Replace all occurrences in the file
```

---

# 📋 الفصل العاشر: الـ Shell والسكريبتات

## 10.1 المتغيرات والأوامر

```bash
# متغيرات
$ NAME="اياد"
$ echo $NAME
$ echo "اهلا $NAME"
$ echo "المسار الحالي: $(pwd)"    # تنفيذ أمر داخل string

# المتغيرات الجاهزة
$ echo $HOME                       # مجلدك الشخصي
$ echo $USER                       # اسم المستخدم
$ echo $PATH                       # مسارات البحث عن الأوامر
$ echo $SHELL                      # الـ shell الحالي
$ echo $$                          # PID الـ shell الحالي
```

## 10.2 كتابة سكريبت بسيط

```bash
#!/bin/bash
# ده ملف bash script

NAME="اياد"
echo "مرحباً $NAME!"
echo "التاريخ: $(date)"
echo "المجلد: $(pwd)"

# شرط if
if [ -f "file.txt" ]; then
    echo "الملف موجود"
else
    echo "الملف مش موجود"
fi

# حلقة for
for i in 1 2 3 4 5; do
    echo "رقم: $i"
done

# حلقة while
count=1
while [ $count -le 5 ]; do
    echo "الكاونتر: $count"
    ((count++))
done
```

```bash
$ chmod +x script.sh               # إضافة صلاحية التنفيذ
$ ./script.sh                      # تشغيل السكريبت
$ bash script.sh                   # تشغيل بديل حتى لو من غير chmod +x ولكن ك bash
```

## 10.3 الـ .bashrc — إعدادات الـ Shell

```bash
$ nano ~/.bashrc                   # فتح ملف الإعدادات
```

**إضافات مفيدة للـ .bashrc:**

```bash
# Aliases (اختصارات)
alias ll='ls -la'
alias la='ls -la'
alias ..='cd ..'
alias ...='cd ../..'
alias c='clear'
alias grep='grep --color=auto'
alias update='sudo apt update && sudo apt upgrade -y'

# تحسين الـ Prompt
PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '

# متغيرات البيئة
export EDITOR=vim
export LANG=ar_EG.UTF-8
```

```bash
$ source ~/.bashrc                 # تطبيق التغييرات
```

---

# ⏰ الفصل الحادي عشر: المهام المجدولة (Cron)

```bash
$ crontab -e                       # تعديل مهامك المجدولة
$ crontab -l                       # عرض مهامك
$ sudo crontab -e                  # مهام الـ root
```

**صيغة Cron:**

```
Minute  Hour  Day_of_Month  Month  Day_of_Week  Command
  *       *         *         *          *       command

# Examples:
# 0 2 * * *      = Every day at 2:00 AM
# 30 8 * * 1     = Every Monday at 8:30 AM
# 0 0 1 * *      = First day of every month at midnight
# */5 * * * *    = Every 5 minutes
# @daily         = Run daily
# @weekly        = Run weekly
# @reboot        = Run at system startup

# Example: Clean /tmp daily
0 3 * * * rm -rf /tmp/*

# Example: Daily backup
30 2 * * * tar -czf /backup/home_$(date +%Y%m%d).tar.gz /home/eiad/ف
```

---

# 🔧 الفصل الثاني عشر: أوامر النظام والمراقبة

## 12.1 معلومات النظام

```bash
$ uname -a                         # معلومات الـ kernel
$ hostnamectl                      # معلومات الجهاز والنظام
$ lsb_release -a                   # توزيعة لينكس
$ cat /etc/os-release              # معلومات التوزيعة

# الـ Hardware
$ lscpu                            # معلومات المعالج
$ lsmem                            # معلومات الرام
$ lsblk                            # الأقراص والأجزاء
$ df -h                            # مساحة القرص
$ du -sh ~/                        # حجم مجلدك
$ du -sh */ | sort -rh             # ترتيب حسب الحجم

# الـ RAM
$ free -h                          # استخدام الذاكرة
$ cat /proc/meminfo                # تفاصيل

# الحرارة والـ Performance
$ sensors                          # حرارة المعالج (محتاج تنصيب)
$ iostat                           # إحصائيات القرص
$ vmstat                           # إحصائيات الذاكرة والـ CPU
```

## 12.2 الـ Logs

```bash
$ sudo journalctl                  # كل logs النظام (systemd)
$ sudo journalctl -f               # مباشر (real-time)
$ sudo journalctl -u ssh           # logs خدمة معينة
$ sudo journalctl --since "1 hour ago"  # من ساعة متعينة
$ sudo tail -f /var/log/syslog     # syslog مباشر
$ sudo tail -f /var/log/auth.log   # محاولات تسجيل الدخول
```

## 12.3 خدمات النظام (systemd)

```bash
$ systemctl status nginx           # حالة خدمة
$ sudo systemctl start nginx       # تشغيل خدمة
$ sudo systemctl stop nginx        # إيقاف خدمة
$ sudo systemctl restart nginx     # إعادة تشغيل
$ sudo systemctl reload nginx      # تحديث الإعدادات بدون إيقاف
$ sudo systemctl enable nginx      # تشغيل تلقائي عند الإقلاع
$ sudo systemctl disable nginx     # إلغاء التشغيل التلقائي
$ systemctl list-units --type=service  # كل الخدمات
```

---

# 🛡️ الفصل الثالث عشر: الأمن الأساسي

## 13.1 الـ Firewall مع UFW

```bash
$ sudo ufw status                  # حالة الـ firewall
$ sudo ufw enable                  # تفعيل
$ sudo ufw disable                 # تعطيل

$ sudo ufw allow 22                # السماح لـ SSH
$ sudo ufw allow 80                # السماح لـ HTTP
$ sudo ufw allow 443               # السماح لـ HTTPS
$ sudo ufw allow from 192.168.1.0/24  # السماح لـ network محلي فقط
$ sudo ufw deny 3306               # حجب MySQL Port

$ sudo ufw delete allow 80         # حذف قاعدة
$ sudo ufw status numbered         # عرض مع أرقام
$ sudo ufw delete 2                # حذف قاعدة برقمها
```

## 13.2 تأمين SSH

```bash
$ sudo nano /etc/ssh/sshd_config
```

**إعدادات مهمة:**

```bash
Port 2222                    # تغيير البورت من 22
PermitRootLogin no           # منع root من الاتصال مباشرة
PasswordAuthentication no    # الاتصال بـ keys فقط (بعد إعداد الـ keys)
MaxAuthTries 3               # 3 محاولات فقط
AllowUsers eiad ahmed        # السماح لمستخدمين معينين فقط
```

```bash
$ sudo systemctl restart ssh   # تطبيق الإعدادات
```

---

# اختصارات مهمة لازم تحفظها

## اختصارات الـ Terminal

| الاختصار | الفعل |
| --- | --- |
| `Ctrl+C` | إيقاف العملية الحالية |
| `Ctrl+Z` | إيقاف مؤقت |
| `Ctrl+D` | إغلاق الـ terminal / EOF |
| `Ctrl+L` | مسح الشاشة (زي clear) |
| `Ctrl+A` | روح لبداية السطر |
| `Ctrl+E` | روح لنهاية السطر |
| `Ctrl+R` | بحث في تاريخ الأوامر |
| `Ctrl+U` | امسح من الكرسر للبداية |
| `Ctrl+K` | امسح من الكرسر للنهاية |
| `Tab` | إكمال تلقائي |
| `Tab Tab` | عرض كل الاحتمالات |
| `↑ / ↓` | التنقل في التاريخ |
| `!!` | تكرار آخر أمر |
| `!ssh` | تكرار آخر أمر يبدأ بـ ssh |

---

# 📚 المصادر

## مصادر التعلم

- **Big Data بالعربي**
- **man pages** — الوثيقة الرسمية لكل أمر: `man ls`, `man chmod`
- **tldr** — شرح مبسط للأوامر: `sudo apt install tldr && tldr ls`
- **LinuxCommand.org**
- **OverTheWire Bandit**
- **Linux Journey**

1. **جرب كل الأوامر** — مفيش بديل للتطبيق
2. **نزل Ubuntu** على VMware أو VirtualBox أو WSL
3. **ابدأ بـ OverTheWire Bandit** — أفضل طريقة للتعلم
4. **تعلم Bash Scripting** — اللي بعد الأوامر الأساسية
5. **اتعلم Docker** — حاجة لازم كل مبرمج يعرفها
6. **شهادات موصى بيها:** LPIC-1, CompTIA Linux+

---

> 
> 
> 
> **"In real open source, you have the right to control your own destiny."** — Linus Torvalds
> 

Eiad Nouman

eiadnouman@gmail.com
