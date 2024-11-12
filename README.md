# راهنمای نصب و پیکربندی Cassandra DSE 6.0.2

## پیش‌نیازها
1. نصب Ubuntu 18.04.6
2. غیرفعال کردن swap
3. تنظیم timezone و NTP
4. نصب JDK 8
5. نصب Python
6. نصب libaio

## نصب Cassandra DSE

### افزودن مخزن DataStax
```bash
echo "deb https://debian.datastax.com/enterprise/ stable main" | sudo tee -a /etc/apt/sources.list.d/datastax.sources.list
curl -L https://debian.datastax.com/debian/repo_key | sudo apt-key add
sudo apt-get update
```

### نصب پکیج‌های DSE
```bash
sudo apt-get install \
    dse=6.0.2-1 \
    dse-full=6.0.2-1 \
    dse-libcassandra=6.0.2-1 \
    dse-libgraph=6.0.2-1 \
    dse-libhadoop-native-client=2 \
    dse-libhadoop-client=2 \
    dse-liblog4j=4 \
    dse-libsolr=6.0.2-1 \
    dse-libspark=6.0.2-1 \
    dse-libtomcat=6.0.2-1
```

## پیکربندی نودهای جدید
### آدرس‌های IP نودهای جدید:
- 172.17.0.66
- 172.17.0.92
- 172.17.0.95

### فایل‌های پیکربندی مورد نیاز:
1. dse.yml
2. cassandra.yml
3. cassandra-rackdc.properties

## اضافه کردن نود به کلاستر
1. وارد داشبورد شوید
2. گزینه "add automatic" را انتخاب کنید
3. سیستم به صورت خودکار نود جدید را به کلاستر اضافه می‌کند

## دسترسی به داشبورد
```bash
ssh -L 8888:127.0.0.1:8081 ut@172.17.0.100
```

## بکاپ‌گیری
- آدرس VM بکاپ: 172.17.20.19
- برای شروع بکاپ‌گیری، کامند نهایی را در screen اجرا کنید
