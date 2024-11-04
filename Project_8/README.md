## آزمایش8

### گزارش کار

در این آزمایش، هدف ما نمایش گرافیکی داده‌های خروجی است. برنامه به طور مداوم مقادیر سینوس و کسینوس را محاسبه کرده و روی Serial Plotter به صورت نمودار نمایش می‌دهد.
---

### کد برنامه
این کد برای نمایش گرافیکی مقادیر سینوس و کسینوس بر روی Serial Plotter استفاده می‌شه:

1. کتابخانه math.h برای دسترسی به توابع ریاضی مثل سینوس و کسینوس اضافه می‌شه.
2. ثابت‌ها: numPoints تعداد نقاط (۳۶۰)، amplitude دامنه (۱۰۰)، offset جابه‌جایی (۵۱۲) تعیین می‌شن.
3. تابع setup: ارتباط سریال با نرخ ۹۶۰۰ بیت در ثانیه آغاز می‌شه.
4. تابع loop: 
    - برای هر نقطه از ۰ تا ۳۶۰:
        - زاویه به رادیان تبدیل می‌شه.
        - مقدار سینوس و کسینوس محاسبه شده و با مقدار جابه‌جایی جمع می‌شن.
        - مقادیر سینوس و کسینوس به صورت متن به خروجی سریال فرستاده می‌شن، تا روی Serial Plotter نمایش داده بشن.
        - برنامه به مدت ۱۰ میلی‌ثانیه متوقف می‌شه.

به این ترتیب، یک نمودار سینوسی و کسینوسی بر روی Serial Plotter نمایش داده می‌شه.

```cpp
#include <math.h>   
const int numPoints = 360;  
const float amplitude = 100;
const float offset = 512;

void setup() {
  Serial.begin(9600);
}

void loop() {
  for (int i = 0; i < numPoints; i++) {    
    float radians = i * (PI / 180);     
    float sineValue = amplitude * sin(radians) + offset;    
    float cosValue = amplitude * cos(radians) + offset;    
    Serial.print(sineValue);
    Serial.print(",");  
    Serial.println(cosValue);
    delay(10);  
    }
}
```
