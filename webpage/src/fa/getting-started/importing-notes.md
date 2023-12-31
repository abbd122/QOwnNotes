# وارد کردن یادداشت ها

## اورنوت

کادر گفتگوی ورودی اورنوت در دسترس قرار دارد تا بتوانید به فهرست `یادداشت / ورود` دسترسی داشته باشید.

## جاپلین

کادر گفتگوی ورودی جاپلین در دسترس قرار دارد تا بتوانید به فهرست `یادداشت / ورود` دسترسی داشته باشید.

## تام بوی

با استفاده از اسکریپتی به نام [ترومبون](https://github.com/samba/trombone) می توانید یادداشت های تام بوی خود را وارد کنید.

با نصب python2 می توانید اسکریپت را به کار بیندازید. این قابلیت یادداشت های تام بوی شما را به یک پرونده `.enex` اورنوت تبدیل کرده که به دنبال آن شما قادر به ورود به QOwnNotes خواهید بود.

برای هر کسی که قصد انجام این کار را دارد، نخست مطمئن شوید که Python2 را نصب کرده اید. همچنین می توانید `python-is-python2` را نصب کنید (بعداً می توانید آن را حذف کنید):

```bash
 python2 python-is-python2 ،sudo apt را نصب می کند 
```

پرونده ترومبون را از گیت هاب بارگیری، استخراج و به آن پوشه پرش دهید:

```bash
cd ~/Downloads/trombone-master

sudo make
sudo make install
```

سپس به پوشه ای که یادداشت های تام بوی شما در آن قرار دارد cd کنید:

```bash
 cd ~/.local/share/tomboy/
```

سپس این را اجرا کنید:

```bash
find ./ -type f -name '*.note' -print0 | xargs -0 trombone > EXPORT.enex
```

درصورتی که خطاهای یونیکد در مورد یادداشت های معین دریافت می کنید، فقط هر یادداشت را حذف کنید و تا زمانی که آن پیامی مبنی بر ` ذخیره گذاری...` را صادر کند، تبدیل را دوباره اجرا کنید. پرونده ای به نام `EXPORT.enex` در اختیار خواهید داشت که در این صورت می تواند به QOwnNotes وارد شود.

طی ورود به QOwnNotes، می توانید علامت همه مشخصه ها (احتمالاً بجز تاریخ ایجاد و تغییر) را برای ورود بردارید، زیرا تام بوی فاقد آن ویژگی هاست.
