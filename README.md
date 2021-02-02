

<p align="center" style="text-align:center" >
  <img src="https://cdn.iconscout.com/icon/free/png-512/redis-3-1175053.png" alt="Redis image"/>
</p>


 <div align="center">
  تهیه کنندگان : زینب احیایی - نرگس جاوید - آتنا ساقی 
</div>
 
<div dir="rtl">

##  مقدمه 


Redis که کوتاه‌ شده‌ی Remote Dictionary Server می باشد؛ یک نوع پایگاه داده‌ی ‌ in-memory (به این معنای که از memory برای ذخیره سازی استفاده می‌کند) و توزیع شده‌است که داده‌ها به صورت دوتایی key-value ذخیره می‌شوند. 
Redis از انواع مختلف ساختارهای داده  ، مانند رشته ها ، لیست ها ،maps ، مجموعه ها ، مجموعه های مرتب شده ، HyperLogLogs ، bitmaps ،  streams spatial indexes پشتیبانی می کند.
این پروژه توسط تیم اصلی پروژه توسعه و نگهداری و از سال 2015 توسط آزمایشگاه های Redis حمایت مالی می شود. 

## تاریخچه 
پروژه Redis از آنجا شروع شد که Salvatore Sanfilippo ، ملقب به antirez ، توسعه دهنده اصلی Redis ، در تلاش بود مقیاس پذیری استارتاپ ایتالیایی خود را بهبود بخشد ، و یک تحلیلگر real-time  سیستم وب ایجاد کند. Sanfilippo پس از مواجهه با مشکلات قابل توجه در مقیاس بندی برخی از انواع بارهای کاری با استفاده از سیستم های پایگاه داده سنتی ، شروع به ساخت نمونه اولیه اولین نسخه مفهوم Redis در Tcl کرد. مدتی بعد Sanfilippo آن نمونه اولیه را به زبان C ترجمه كرد و لیست را پیاده سازی كرد. بعد از چند هفته استفاده موفقیت آمیز از پروژه ، سان فیلیپو آن را open-source کرد . این پروژه مورد توجه قرار گرفت ، بیشتر در بین جامعه Ruby ، با GitHub و اینستاگرام از جمله اولین شرکت هایی بودند که آن را به کار گرفتند. 

Sanfilippo در مارس 2010 توسط VMware استخدام شد.

در ماه مه 2013 ، Redis توسط نرم افزار Pivotal (یک بخش تبلیغاتی VMware) حمایت مالی شد.

در ژوئن 2015 ، توسعه توسط آزمایشگاه های Redis حمایت مالی شد.

در اکتبر 2018 Redis 5.0 با معرفی Redis Stream - ساختار داده ای جدیدی که امکان ذخیره چندین زمینه و مقادیر رشته را با توالی خودکار و مبتنی بر زمان در یک کلید فراهم می کند ، منتشر شد. 


## محبوبیت 


با توجه به رتبه بندی DB-engines اغلب Redis به عنوان محبوب‌ترین پایگاه داده‌ی key-value قرار دارد. هم چنین در بین پایگاه‌ داده‌های NoSQL رتبه چهارم را در رضایت مشتری و حضور در مارکت را بر اساس نظرات کاربران به خود اختصاص داده است و به عنوان محبوب‌ترین پایگاه داده‌ی NoSQl در container ها انتخاب شده‌است.
طبق آمارهای سایت Stackoverflow نیز ، Redis مورد علاقه ترین پایگاه داده  برنامه نویسان در سال‌های ۲۰۱۷ تا ۲۰۲۰ بوده‌است.


##  تفاوت Redis با سایر سیستم‌های پایگاه داده‌ 

Redis ایده سیستمی را رایج کرد که می تواند همزمان یک محل ذخیره‌سازی و یک حافظه پنهان باشد ، با استفاده از طرحی که در آن داده ها در حافظه اصلی رایانه اصلاح می شوند و از آن خوانده میشوند ، اما همچنین بر روی دیسک با قالبی که برای دسترسی تصادفی به داده مناسب نیست ذخیره میشوند ، اما فقط پس از راه اندازی مجدد سیستم ، داده ها را دوباره در حافظه بازسازی می کنیم.
 در همان زمان ، Redis یک مدل داده را ارائه می دهد که در مقایسه با سیستم مدیریت پایگاه داده رابطه ای (RDBMS) بسیار غیر معمول است. دستورات کاربر به صورت کوئری که باید توسط موتور پایگاه داده اجرا شود توصیف نمی شوند بلکه به شکل عملیات خاصی که بر روی داده های abstract انجام می شود ، توصیف می کنند. از این رو ، داده ها باید به روشی ذخیره شوند که بعداً برای بازیابی سریع مناسب باشد  بدون کمک از سیستم پایگاه داده به صورت ایندکس های ثانویه ، تجمع یا سایر ویژگی های مشترک RDBMS قدیمی. 
در پیاده سازی Redis از فراخوان سیستمی fork استفاده زیادی می شود ، تا پردازه ای که داده‌ها را  نگهداری می‌کند کپی کند و پردازه والد همچنان به سرویس دهی به client ادامه دهد ، در حالی که فرآیند فرزند نسخه ای از داده ها را بر روی دیسک ایجاد می کند.


## زبان‌های پشتیبانی شده
از نسخه 2.6 ،   Redis از امکان اسکریپت نویسی سمت سرور به زبان Lua برخوردار است.
بسیاری از زبان‌های برنامه نویسی دارای Redis language bindings در سمت کلاینت خود می‌باشند. زبان‌هایی که برای آن‌ها کتابخانه کلاینت ردیس وجود دارد عباتند از:
اکشن‌اسکریپت، سی، سی++، سی شارپ، کلوژر، لیسپ معمولی، دارت، ارلنگ، گو، هسکل، هکس، آی‌او، جاوا، جاوااسکریپت، لوا، آبجکتیو-سی، پرل، پی‌اچ‌پی، پیور داتا، پایتون، آر، روبی، اسکالا، اسمال‌تاک، تی‌سی‌ال. چندین برنامه نرم افزاری کلاینت در این زبانها وجود دارد.

## انواع داده‌ها
redis نگاشتی از کلیدها به مقدارها است. تفاوت مهم بین Redis و سایر سیستم های ذخیره سازی ساختاری این است که Redis نه تنها از رشته ها (Strings) ، بلکه از انواع داده های انتزاعی (abstract) نیز پشتیبانی می کند.
 نوع داده مقدار عملیات ممکن بر روی هر کلید را مشخص می‌کند. ردیس از انواع داده زیر پشتیبانی می‌کند:
رشته: رشته‌ها می‌توانند هر نوع داده‌ای، مثلاً تصویر باینری، را نگهداری کنند. یک رشته باید حداکثر ۵۱۲ مگابایت طول داشته باشد.
لیست: لیست‌ها لیست‌های از رشته‌ها هستند که به ترتیب درج مرتب شده‌اند. می‌توان به سر یا ته یک لیست یک عنصر جدید افزود.
مجموعه: مجموعه‌ها کلکسیون بدون ترتیبی از رشته‌ها هستند. می‌توان به یک مجموعه رشته جدید افزود، حذف کرد، یا وجود یک رشته را در مجموعه امتحان کرد.
درهم‌سازی(Hash): درهم‌سازی‌های ردیس نگاشتی بین کلیدهای از نوع رشته به مقادیر از نوع رشته‌است.
مجموعه مرتب: مشابه مجموعه‌ها هستند، با این تفاوت که به هر عنصر مجموعه مرتب یک امتیاز تخصیص می‌یابد، و اعضای مجموعه مرتب از بیشترین امتیاز به کمترین امتیاز مرتب می‌شوند.

## ماندگاری داده‌ها
redis چندین مدل مختلف برای ماندگاری داده‌ها ارائه می‌دهد:
* ذخیره‌کردن یک نسخه از داده بر روی دیسک در بازه‌های منظم طبق قواعدی که توسط کاربر مشخص شده‌است.
* ثبت در شرح وقایع (log) پس از دریافت هر درخواست نوشتن، که این شرح وقایع را در اجرای دوباره بعدی سرور می‌توان مجدد اجرا کرد.
* غیرفعال کردن ماندگاری
* ترکیبی از دو حالت اول
در حالت دوم، یعنی ثبت رخدادها در شرح وقایع (log)، چندین گزینه وجود دارد:
* هماهنگ‌کردن حالت فایل با حالت فیزیکی دیسک به محض عمل نوشتن (امن‌ترین گزینه، ولی کندترین)
* هماهنگ‌کردن حالت فایل با حالت فیزیکی دیسک در هر یک ثانیه (امکان از دست دادن حداکثر یک ثانیه داده)
* محول کردن هماهنگ‌کردن حالت فایل با حالت فیزیکی دیسک به سیستم‌عامل (تندترین گزینه، ولی ناامن‌ترین)


## آموزش نصب 

در این قسمت آموزش نصب Redis 5.0.x بر روی سیستم‌ عامل Ubuntu 20.04 را بررسی می‌کنیم.

برای نصب دستورات زیر را وارد می‌کنیم:



<div dir="ltr">

```
sudo apt update
sudo apt install redis-server
```

</div>




پس از پایان نصب ، سرویس Redis به طور خودکار آغاز می‌شود. برای مشاهده وضعیت سرویس از دستور زیر استفاده می‌کنیم:


<div dir="ltr">

```
sudo systemctl status redis-server
```

</div>



خروجی مانند زیر باید باشد:



<div dir="ltr">

```
redis-server.service - Advanced key-value store
     Loaded: loaded (/lib/systemd/system/redis-server.service; enabled; vendor preset: enabled)
     Active: active (running) since Sat 2020-06-06 20:03:08 UTC; 10s ago
...
```

</div>


اکنون Redis برای سیستم عامل نصب می‌باشد. ولی به طور خودکار Redis اتصالات remote را نمی‌پذیرد و تنها از localhost ( جایی که Redis اجرا میشود) می‌توان به آن متصل شد بنابراین برای اینکه بتوان به صورت remote هم متصل شد باید آن را تنظیم کنیم:

ابتدا فایل configure را با دستور زیر باز کنید:


<div dir="ltr">

```
sudo nano /etc/redis/redis.conf
```

</div>

خطی که با bind 127.0.0.1 ::1 شروع میشود را پیدا کرده و کامنت کنید. 


 
<div dir="ltr">

```
#bind 127.0.0.1 ::1
```

</div>

توجه : در صورتی که client ای که به پایگاه داده متصل میشود روی همان سیستمی که host قرار دارند، نباید این کار را انجام دهید!

سپس فایل را ذخیره کرده و با دستور زیر سرویس Redis را آپدیت کنید.



<div dir="ltr">

```
sudo systemctl restart redis-server
```

</div>

سپس با دستور زیر می‌توان مطمئن شد که Redis بر روی تمام interface  های پورت مورد نظر(در اینجا 6379) در حال listen است:


<div dir="ltr">

```
ss -an | grep 6379
```

</div>


خروجی دستور مشابه زیر هست که در آن 0.0.0.0 بیانگر آدرس‌های IPv4 هست.



<div dir="ltr">

```
tcp  LISTEN 0   511   0.0.0.0:6379   0.0.0.0:*
tcp  LISTEN 0   511      [::]:6379      [::]:* 
```

</div>

 در قدم بعدی باید تنظیمات firewall خود را به گونه قرار دهید که ترافیک‌های TCP در پورت 6379 را فعال کند.
 (مطمئن شید که firewall شما اتصالات معتبر و بدون خطری رو قبول کند)
معمولا میخوایم که IP address های خاصی اجازه دسترسی به سرور Redis داشته باشند، مثلا اگر بخواهیم فقط اتصالاتی که از زیرشبکه‌ی 192.168.121.0/24 هستند دسترسی داشته باشند ، دستور زیر را اجرا میکنیم:


<div dir="ltr">

```
sudo ufw allow proto tcp from 192.168.121.0/24 to any port 6379
```

</div>
 
 
 الان شما می‌توانید یک اتصال TCP روی پورت 6379 به Redis از remote connections داشته باشید.
 
اگر خواستید مطمئن بشید که همه چی به درستی تنظیم شده کافی است  سرور Redis در ماشین remote را با دستور زیر ping کنید:

<div dir="ltr">

```
redis-cli -h <REDIS_IP_ADDRESS> ping
```

</div>


دستور باید خروجی زیر را نشان دهد:

 


<div dir="ltr">

```
PONG
```

</div>



 
</div>

<div dir="rtl">
  
## کاربردها 

برخی از رایج ترین موارد استفاده Redis عبارت از:
*  حافظه نهان نشست (Session Cache)

یکی از کاربرد‌های مهم redis استفاده از آن به عنوان حافظه نهان نشست (session cache) می‌باشد. مزیت استفاده از redis نسبت به دیگر ابزارهای ذخیره نشست، ماندگاری آن است. همچنین دسترسی به اسناد مربوط به چگونگی استفاده از Redis برای این منظور بسیار آسان است.
*  کش کامل صفحه (Full Page Cache (FPC))

Redis یک پلت فرم FPC ارائه می‌دهد که کار کردن با آن بسیار آسان است. بازگشت به سازگاری (consistency) ، حتی در زمان شروع مجدد  Redis instanceها، به همراه ماندگاری دیسک ، باعث می‌شود کاربران شما متوجه هیچ کاهش سرعتی در زمان بارگذاری صفحه خود نشوند.
* صف‌ها (Queues)

استفاده از Redis در موتور ذخیره سازی حافظه (memory storage engine) برای انجام عملیات مربوط به لیست‌ها و مجموعه‌ها (set) ، آن را به یک بستر شگفت انگیز برای استفاده در صف پیام (message queue) تبدیل می کند. تعامل با Redis به عنوان یک صف ، برای هر کسی که عادت به استفاده از عملیات push / pop لیست ها در زبان های برنامه نویسی مانند پایتون دارد، آسان می‌باشد.
* شمارش و تابلو‌ها (Leaderboards/Counting)

به دلیل in-memory بودن redis ، عملیات increment و decrement به وسیله آن به سادگی و به شکل کارایی صورت می‌گیرد. همچنین ساختمان داده‌های مجموعه و مجموعه مرتب را نیز پشتیبانی می‌کند که ساختمان داده‌های پرکاربردی هستند.
* استفاده از فیچر Pub/Sub

از این این فیچر ردیس در ارتباطات شبکه های اجتماعی، راه اندازی اسکریپت های مبتنی بر رویدادهای Pub / Sub و سیستم های چت استفاده می‌شود .


## برخی دستورات  پرکاربرد

در این قسمت برخی دستورات پرکاربرد redis را بررسی می کنیم.

برای ذخیره مقادیر درون کلید ها از دستور* set استفاده می شود:

<div dir="ltr">

```
set num 2
```

</div>

این دستور مقدار ۲ را در کلید num ذخیره می‌کند.

برای برگرداندن مقدار درون کلید مورد نظر از دستور* get استفاده می شود:

<div dir="ltr">

```
get num
```

</div>

و خروجی مقدار ۲ را برمی گرداند.

برای تست وجود کلید از دستور* EXISTS استفاده می شود:

<div dir="ltr">

```
EXISTS num     => 1
EXISTS blabla  => 0
```

</div>

برای اضافه کردن مقدار عددی درون یک کلید می توان از دستور* INCR و یا INCRBY استفاده کرد:

<div dir="ltr">

```
INCR num
```

</div>

پس از این دستور مقدار درون کلید num به صورت اتمیک ۳ می شود.

<div dir="ltr">

```
INCRBY num 100 
```

</div>
 و پس از دستور بالا مقدار num به ۱۰۳ تغییر خواهد کرد.
 
* همانند این دو دستور برای کم کردن مقادیر مورد نظر نیز وجود دارد:
 
 <div dir="ltr">

```
DECR   num      => 102
DECRBY num 100  => 2
```

</div>

همچنین این دستورات نیز مانند تمامی دستورات ردیس اتمیک عمل میکنند.

برای حذف کلید و مقدار کلید مورد نظر از دیتابیس از دستور* DEL میتوان استفاده کرد:

<div dir="ltr">

```
DEL num
```

</div>

##عملکرد 

در شرایطی که مانایی داده‌ها نیاز نباش، ویژگی in-memory بودن redis باعث می‌شود کارایی و performance بالاتری نسبت به دیتابیس هایی که هر تغییر را در حافظه اعمال نموده، داشته باشد. ردیس تنها روی یک پردازه عمل میکند و بر روی فایل های append-only روی دو پردازه عمل میکند. در نتیجه یک واحد ردیس نمی تواند عملیات‌ها را به صورت موازی اجرا کند.

##خوشه بندی 

ردیس خوشه بندی را در اوریل ۲۰۱۵با انتشار ورژن 3.0 معرفی کرد. مشخصه خوشه، مجموعه‌ای از دستورات ردیس را \یاده سازی می‌کند: تمام دستورات تک کلیدی قابل دسترس هستند، دستورات چند کلیدی(دستورات مربوط به اجتماع‌ها و اشتراک‌ها) محدود به کلید‌های متعلق به نود‌های یکسان می‌باشند و دستورات مربوط به عملیات selection دیتابیس در دسترسنمی باشند. یک خوشه ردیس می‌تواند تا ۱۰۰۰ گره، ایمنی نوشتاری قابل قبول داشته باشد و در صورت خرابی برخی از گره‌ها  عملیات را ادامه دهد. 

##موارد استفاده

با توجه به ماهیت طراحی دیتابیس، موارد استفاده معمولا عبارتند از ذخیره session، حافظه پنهان، صف های پیغام و سایر موارد. شرکت‌های بزرگی مانند توییتر از ردیس استفاده می‌کنند. سرویس وب آمازون و مایکروسافت و Alibabaاستفاده از ردیس را در مجموعه‌های خود پیشنهاد می‌کنند.

</div>
