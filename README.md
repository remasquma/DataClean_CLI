# ل استخدام الاداة ثبت المتطلبات 
pip install -r requirements.txt
او
python -m pip install -r requirements.txt

# امر التحويل و التنظيف "Recipe"
- الصيغة الاصلية للتحويل فقط 
python cli.py convert -i <مسار_الملف_المدخل> -o <مسار_الملف_المخرج> -f <الصيغة_المطلوبة>

# اضافه اوامر التنظيف للملف المخرج
- --drop-duplicates :	حذف الصفوف المكررة بالكامل
- --drop-empty : حذف الصفوف والاعمدة الفارغة
- --trim-whitespace : مسح المسافات الزائدة من بداية ونهاية النصوص الأعمدة
- --standardize-dates : توحيد صيغ التواريخ 
- --recipe : تفعيل ملف إعدادات جاهز صيغته .yaml أو .json لتطبيق شروط تنظيف محددة مسبقاً
- --summary : عرض جدول تقرير نهائي للبيانات قبل حفظ الملف المخرج 
- --encoding : تحديد ترميز الملف يدويا (مثل utf-8 أو latin-1) اذا ظهرت مشاكل باللغة

# الامر الكامل للتحويل والتنظيف 
python cli.py convert -i input.csv -o output.json -f json --drop-duplicates --drop-empty --standardize-dates --summary

# امر الفحص السريع "Profiling"
python cli.py profile -i filename
يظهر : عدد الصفوف، القيم المفقودة، نوع البيانات

# الملف recipes.py لاختصار تكرار الامر كامل كل مره 
بدل كتابه :
python cli.py convert -i input.csv -o output.json -f json --drop-duplicates --drop-empty --standardize-dates --summary
يكتب :
python cli.py convert -i inputfile -o outputfile -f format --recipe my_clean_recipe.yaml

# الملف input.csv للتجربة فقط
devloped by :
Remas 
Ali 
