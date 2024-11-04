# آزمایش 1 

## گزارش کار

هدف راه اندازی دو LED چشمک زن می باشد به طوری که یکی روشن و دیگری خاموش باشد و خلاف یکدیگر چشمک بزنند.

---

### کد برنامه 
این کد دو تا LED رو به صورت متناوب روشن و خاموش می‌کنه.

1. دو متغیر led1 و led2 برای پایه‌های ۱۳ و ۷ تعریف شده‌اند.
2. توی فانکشن setup، هر دو پایه به عنوان خروجی تنظیم می‌شن.
3. توی فانکشن loop، یکی از LEDها روشن و دیگری خاموش می‌شه و بعد از یک ثانیه، جاشون عوض می‌شه. این روند همواره تکرار می‌شه.

پس LEDها یکی درمیون هر یک ثانیه روشن و خاموش می‌شن.

```cpp
int led1 = 13;
int led2 = 7;

void setup() {
pinMode(led1, OUTPUT);
pinMode(led2, OUTPUT);
}

void loop() {
digitalWrite(led1, HIGH);   
digitalWrite(led2, LOW);
delay(1000);
digitalWrite(led1, LOW);
digitalWrite(led2, HIGH);   
delay(1000);
}
```

---

### عکس مدار


![micro and circuit](/pic/microprocessor_2.jpg)

---

### شماتیک مدار

![schematic](/pic/schematic_1.jpg)
