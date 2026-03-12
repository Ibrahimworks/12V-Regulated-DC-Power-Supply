<div align="center">

# 🔌 12V Regulated Linear Power Supply  
### مزود طاقة خطي منظّم 12 فولت

![Simulator](https://img.shields.io/badge/Simulator-NI%20Multisim%2013-blue)
![Output](https://img.shields.io/badge/Output-12V%20DC-orange)
![License](https://img.shields.io/badge/License-MIT-green)

</div>

---

## 🌐 Language / اللغة

- 🇬🇧 [English](#-english)
- 🇩🇿 [العربية](#-العربية)

---

# 🇬🇧 English

## Overview

A classic **linear regulated power supply** designed in **NI Multisim 13**, converting  
**230 Vrms / 50 Hz AC mains** into a stable **+12 V DC output** using the **LM7812CT** voltage regulator.

---

## Circuit Schematic

![Schematic](assets/schematic.png)

---

## How It Works

| Stage | Components | Function |
|---|---|---|
| Transformer | 5H_SP (10:1) | Steps 230 Vrms down to ~23 Vrms |
| Rectifier | D1–D4 (1N4007) | Full-wave bridge rectification |
| Filter | C2 (4700µF), C1 (100nF) | Smooths rectified DC |
| Regulator | U1 (LM7812CT) | Regulates to +12 V DC |
| Output filter | C3 (100nF), C4 (10µF) | Stabilizes regulator output |
| Protection | D5 (1N4007) | Reverse-current protection |

---

## Signal Flow

1. **V1** provides 230 Vrms / 50 Hz AC — equivalent to a household outlet.
2. The **10:1 transformer** reduces the voltage to ~23 Vrms (~32.5 V peak).
3. The **bridge rectifier** converts AC to pulsating DC (~31 V after diode drops).
4. **C2 (4700 µF)** smooths the ripple while **C1 (100 nF)** filters high-frequency noise.
5. The **LM7812CT** regulates the voltage to **+12 V DC**.
6. **C3** and **C4** stabilize the output.
7. **D5** prevents reverse current from flowing back into the regulator.

---

## Components

| Reference | Part | Value / Notes |
|---|---|---|
| V1 | AC Source | 230 Vrms / 50 Hz |
| 5H_SP | Transformer | 5H primary, 10:1 ratio |
| D1–D4 | Rectifier diodes | 1N4007 |
| C2 | Bulk capacitor | 4700 µF |
| C1 | Bypass capacitor | 100 nF |
| U1 | Voltage regulator | LM7812CT |
| C3 | Output bypass | 100 nF |
| C4 | Output filter | 10 µF |
| D5 | Protection diode | 1N4007 |

---

## Electrical Specifications

| Parameter | Value |
|---|---|
| Input voltage | 230 Vrms / 50 Hz |
| Output voltage | +12 V DC |
| Max output current | 1.5 A |
| Max output power | ~18 W |
| Dropout voltage | ~2 V |

---

## Simulation

This circuit was designed and simulated in **NI Multisim 13**.

<a href="assets/powersupply.ms13" download>
<img src="https://img.shields.io/badge/⬇️%20Download%20Multisim%20Project-blue?style=for-the-badge">
</a>

---

## Video Walkthrough

https://github.com/user-attachments/assets/fe318b0b-636f-46ce-af26-970246c491c9

---

## Screenshots

| Interactive Simulation | Analysis Options | SPICE Settings |
|---|---|---|
| ![](assets/sim-settings-1.png) | ![](assets/sim-settings-2.png) | ![](assets/sim-settings-3.png) |

---

## Running the Simulation

1. Open `powersupply.ms13` in **NI Multisim 13**.
2. Press **F5** or go to **Simulate → Run**.
3. Connect a **Multimeter** or **Oscilloscope** between `out+` and `out−`.

---

# 🇩🇿 العربية

<div dir="rtl">

## نظرة عامة

مزود طاقة خطي منظّم صُمم باستخدام **NI Multisim 13** لتحويل  
تيار متردد بجهد **230 فولت / 50 هرتز** إلى تيار مستمر ثابت بجهد **12 فولت**  
باستخدام منظم الجهد **LM7812CT**.

---

## المخطط الكهربائي

![المخطط الكهربائي](assets/schematic.png)

---

## طريقة عمل الدائرة

| المرحلة | المكونات | الوظيفة |
|---|---|---|
| المحول | 5H_SP (10:1) | خفض الجهد من 230 فولت إلى حوالي 23 فولت |
| المقوم | D1–D4 (1N4007) | تحويل التيار المتردد إلى تيار مستمر |
| المرشح | C2 ، C1 | تنعيم الجهد وإزالة الضوضاء |
| المنظم | LM7812CT | تثبيت الجهد عند 12 فولت |
| مرشح الخرج | C3 ، C4 | تحسين استقرار الجهد |
| الحماية | D5 | منع رجوع التيار |

---

## تدفق الإشارة

1. المصدر **V1** يوفر تيارًا مترددًا بجهد **230 فولت / 50 هرتز**.
2. **المحول بنسبة 10:1** يخفض الجهد إلى حوالي **23 فولت**.
3. **المقوم الجسري** يحول التيار المتردد إلى تيار مستمر نابض.
4. المكثف **C2** يقلل التموج بينما **C1** يزيل الضوضاء عالية التردد.
5. المنظم **LM7812CT** يثبت الجهد عند **12 فولت**.
6. المكثفان **C3 و C4** يحسنان استقرار الخرج.
7. الصمام **D5** يمنع رجوع التيار إلى الدائرة.

---

## المكونات

| المرجع | القطعة | القيمة |
|---|---|---|
| V1 | مصدر AC | 230 فولت / 50 هرتز |
| 5H_SP | محول | نسبة 10:1 |
| D1–D4 | صمامات تقويم | 1N4007 |
| C2 | مكثف رئيسي | 4700µF |
| C1 | مكثف تجاوز | 100nF |
| U1 | منظم جهد | LM7812CT |
| C3 | مكثف خرج | 100nF |
| C4 | مكثف خرج | 10µF |
| D5 | صمام حماية | 1N4007 |

---

## المواصفات الكهربائية

| المعامل | القيمة |
|---|---|
| جهد الدخل | 230 فولت |
| جهد الخرج | 12 فولت DC |
| أقصى تيار خرج | 1.5 أمبير |
| أقصى قدرة | ~18 واط |
| جهد السقوط | ~2 فولت |

---

## المحاكاة

تم تصميم ومحاكاة هذه الدائرة باستخدام **NI Multisim 13**.

<a href="assets/powersupply.ms13" download>
<img src="https://img.shields.io/badge/⬇️%20تحميل%20ملف%20المشروع-green?style=for-the-badge">
</a>

---

## فيديو الشرح

https://github.com/user-attachments/assets/68a5b7d8-426b-4bd2-81d5-98c172c6e117

</div>

---

## ⚠️ Safety Notice

This project involves **230V mains electricity**.  
Improper handling can cause **serious injury or death**.

Only build this circuit if you are familiar with proper electrical safety practices.

---

## License

This project is released under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.
