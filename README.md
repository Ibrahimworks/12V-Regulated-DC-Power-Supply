<div align="center">

# 🔌 12V Regulated DC Power Supply

<a href="#arabic">
  <img src="https://img.shields.io/badge/🇩🇿-العربية-green?style=for-the-badge" alt="العربية"/>
</a>
&nbsp;&nbsp;
<a href="#english">
  <img src="https://img.shields.io/badge/🇬🇧-English-blue?style=for-the-badge" alt="English"/>
</a>

</div>

---

<div dir="rtl">

<h2 id="arabic">🇩🇿 باللغة العربية (الدارجة الجزائرية)</h2>

### المخطط الكهربائي

![Schematic](schematic.png)

### كيفاش يخدم الـ Circuit؟

| المرحلة | المكونات | الوظيفة |
|---|---|---|
| Transformer | 5H_SP (10:1) | يخلي الـ 230V تنزل لـ 23V |
| Rectifier | D1–D4 (1N4007) | يقلب الـ AC لـ DC |
| Filter | C2 (4700µF), C1 (100nF) | يستبليزي الـ voltage |
| Régulateur | U1 (LM7812CT) | يثبت الـ voltage على 12V |
| Filtre sortie | C3 (100nF), C4 (10µF) | يزيد يستبليزي الـ output |
| Protection | D5 (1N4007) | يحمي من الـ court-circuit |

### شرح خطوة بخطوة

1. **V1** تعطي 230Vrms / 50Hz AC — نفس الـ prise ديالنا.
2. **الـ Transformer (5H_SP)** بنسبة 10:1 يخليها تنزل لـ ~23Vrms (~32.5V peak).
3. **الـ Bridge Rectifier** (D1–D4) يقلبها لـ DC متقطع (~31V).
4. **C2 (4700µF)** يستبليزي الـ voltage الكبير؛ **C1 (100nF)** يزيد يفلتر.
5. **LM7812CT** يثبت الـ output على **12V**.
6. **C3 (100nF)** و **C4 (10µF)** يزيدوا يستبليزيوا بعد الـ régulateur.
7. **D5** تحمي من ما ترجعش الـ voltage للـ system.

### المكونات

| المرجع | القطعة | القيمة / ملاحظات |
|---|---|---|
| V1 | مصدر AC | 230Vrms, 50Hz |
| 5H_SP | Transformer | 5H, نسبة 10:1 |
| D1–D4 | Diodes | 1N4007 (1A, 1000V) |
| C2 | Condensateur كبير | 4700µF electrolytic |
| C1 | Condensateur bypass | 100nF ceramic |
| U1 | Régulateur | LM7812CT (+12V, 1.5A) |
| C3 | Filtre output | 100nF ceramic |
| C4 | Filtre output | 10µF electrolytic |
| D5 | Diode protection | 1N4007 |

### المواصفات الكهربائية

| الخاصية | القيمة |
|---|---|
| Tension d'entrée | 230Vrms / 50Hz |
| Tension de sortie | +12V DC |
| Max courant | 1.5A |
| Max puissance | ~18W |

### Simulation

هذا الـ circuit صمم على **NI Multisim 13**.

### شرح الفيديو

https://github.com/user-attachments/assets/demo_ar.mp4

<a href="powersupply.ms13" download>
  <img src="https://img.shields.io/badge/⬇️%20تحميل-powersupply.ms13-green?style=for-the-badge" alt="تحميل"/>
</a>

#### Screenshots

| إعدادات الـ Simulation | خيارات التحليل | إعدادات SPICE |
|---|---|---|
| ![](sim-settings-1.png) | ![](sim-settings-2.png) | ![](sim-settings-3.png) |

#### كيفاش تسيملي

1. حل `powersupply.ms13` في Multisim 13 أو أحدث.
2. دوز على **F5** أو **Simulate → Run**.
3. حط **Multimeter** أو **Oscilloscope** بين `out+` و `out−` باش تشوف الـ voltage.

</div>

---

<h2 id="english">🇬🇧 English</h2>

A classic linear regulated power supply designed in **NI Multisim 13**, converting **230Vrms / 50Hz** mains AC down to a stable **+12V DC** output using the LM7812CT voltage regulator.

### Schematic

![Schematic](schematic.png)

### How It Works

| Stage | Components | Function |
|---|---|---|
| Transformer | 5H_SP (10:1) | Steps 230Vrms down to ~23Vrms |
| Rectifier | D1–D4 (1N4007) | Full-wave bridge rectification |
| Filter | C2 (4700µF), C1 (100nF) | Smooths rectified DC; bulk + HF bypass |
| Regulator | U1 (LM7812CT) | Regulates to +12V DC |
| Output filter | C3 (100nF), C4 (10µF) | Stabilises regulator output |
| Protection | D5 (1N4007) | Reverse-polarity output protection |

### Step-by-step signal flow

1. **V1** provides 230Vrms / 50Hz AC — same as a standard wall outlet.
2. The **10:1 transformer (5H_SP)** reduces this to ~23Vrms (~32.5V peak).
3. The **bridge rectifier** (D1–D4) converts AC to pulsating DC (~31V after diode drops).
4. **C2 (4700µF)** smooths the bulk ripple; **C1 (100nF)** bypasses high-frequency noise.
5. The **LM7812CT** clamps the output to a steady **+12V**.
6. **C3 (100nF)** and **C4 (10µF)** filter the regulated output for stability.
7. **D5** blocks reverse current from flowing back into the system.

### Components

| Reference | Part | Value / Notes |
|---|---|---|
| V1 | AC Source | 230Vrms, 50Hz |
| 5H_SP | Transformer | 5H primary, 10:1 ratio |
| D1–D4 | Rectifier diodes | 1N4007 (1A, 1000V) |
| C2 | Bulk capacitor | 4700µF electrolytic |
| C1 | Bypass capacitor | 100nF ceramic |
| U1 | Voltage regulator | LM7812CT (+12V, 1.5A) |
| C3 | Output bypass | 100nF ceramic |
| C4 | Output filter | 10µF electrolytic |
| D5 | Protection diode | 1N4007 |

### Electrical Specifications

| Parameter | Value |
|---|---|
| Input voltage | 230Vrms / 50Hz |
| Output voltage | +12V DC (regulated) |
| Max output current | 1.5A (LM7812CT limit) |
| Max output power | ~18W |
| Dropout voltage | ~2V (LM7812CT) |

### Simulation

This circuit was designed in **NI Multisim 13**.

### Video Walkthrough

https://github.com/user-attachments/assets/demo_en.mp4

<a href="powersupply.ms13" download>
  <img src="https://img.shields.io/badge/⬇️%20Download-powersupply.ms13-blue?style=for-the-badge" alt="Download Multisim Project"/>
</a>

#### Screenshots

| Interactive Simulation Settings | Analysis Options | Custom SPICE Options |
|---|---|---|
| ![](sim-settings-1.png) | ![](sim-settings-2.png) | ![](sim-settings-3.png) |

#### Running the simulation

1. Open `powersupply.ms13` in Multisim 13 or later.
2. Press **F5** (or go to **Simulate → Run**) to start interactive simulation.
3. Place a **Multimeter** or **Oscilloscope** (from Instruments menu) between `out+` and `out−` to measure the output voltage.

#### Simulation settings (already configured in the file)

| Setting | Value |
|---|---|
| SPICE options | Use custom settings |
| Max simulation speed | Limited to real time |
| Grapher data | Discard data to save memory |
| Max number of points | 128,000 |
| ABSTOL | 1e-9 A |
| VNTOL | 0.0001 V |
| RELTOL | 0.01 |
| RSHUNT | 1e+12 Ω |
| Convergence assistance (CONVLIMIT) | Enabled |

---

## License

This project is released under the [MIT License](LICENSE).
