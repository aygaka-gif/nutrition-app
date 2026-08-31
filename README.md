[index.html](https://github.com/user-attachments/files/31628403/index.html)
<meta name='viewport' content='width=device-width, initial-scale=1'/><!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>عيادة التغذية العلاجية الشاملة | التصنيف اللوني الذكي للحالات الطبية</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@300;400;500;700;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #2e7d32;
            --dark: #1b5e20;
            --light: #f1f8e9;
            --card-border: #c8e6c9;
            --summary-bg: #f0f4c3;
            --summary-text: #33691e;
            --bg: #f8fafc;
            --card-bg: #ffffff;
            --text-main: #0f172a;
            --text-muted: #64748b;
            --border-color: #e2e8f0;
            --radius-lg: 20px;
            --radius-md: 14px;
            --radius-sm: 8px;
            --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.04);
            --shadow-md: 0 8px 20px rgba(0, 0, 0, 0.06);
        }

        body[data-theme="general"] { --primary: #2e7d32; --dark: #1b5e20; --light: #f1f8e9; --card-border: #c8e6c9; --summary-bg: #f0f4c3; --summary-text: #33691e; }
        body[data-theme="thinness"] { --primary: #1565c0; --dark: #0d47a1; --light: #e3f2fd; --card-border: #90caf9; --summary-bg: #bbdefb; --summary-text: #0d47a1; }
        body[data-theme="child-thinness"] { --primary: #00838f; --dark: #006064; --light: #e0f7fa; --card-border: #80deea; --summary-bg: #b2ebf2; --summary-text: #006064; }
        body[data-theme="child-obesity"] { --primary: #e65100; --dark: #bf360c; --light: #fff3e0; --card-border: #ffcc80; --summary-bg: #ffe0b2; --summary-text: #e65100; }

        * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Tajawal', sans-serif; -webkit-tap-highlight-color: transparent; }

        body {
            background-color: var(--bg);
            width: 100vw;
            height: 100vh;
            height: 100dvh;
            display: flex;
            flex-direction: column;
            overflow: hidden;
            color: var(--text-main);
        }

        .app-container {
            width: 100%;
            height: 100%;
            background: var(--bg);
            display: flex;
            flex-direction: column;
            overflow: hidden;
            padding-top: env(safe-area-inset-top);
            padding-bottom: env(safe-area-inset-bottom);
        }

        .app-header {
            padding: 12px 20px;
            background: rgba(255,255,255,0.95);
            backdrop-filter: blur(10px);
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid var(--border-color);
            z-index: 90;
        }

        .user-badge { display: flex; align-items: center; gap: 10px; }
        .avatar {
            width: 40px; height: 40px; border-radius: 50%;
            background: var(--light); color: var(--primary);
            display: flex; align-items: center; justify-content: center;
            font-size: 18px; font-weight: 700;
        }
        .user-info h4 { font-size: 15px; font-weight: 700; color: var(--dark); }
        .user-info p { font-size: 11px; color: var(--text-muted); }

        .app-content {
            flex: 1; overflow-y: auto; padding: 16px;
            padding-bottom: calc(90px + env(safe-area-inset-bottom)); 
            scroll-behavior: smooth;
        }

        .tabs-header {
            display: flex; gap: 8px; overflow-x: auto;
            padding-bottom: 8px; margin-bottom: 16px; scrollbar-width: none;
        }
        .tabs-header::-webkit-scrollbar { display: none; }

        .tab-btn {
            padding: 8px 14px; border-radius: 20px; background: var(--card-bg);
            border: 1px solid var(--border-color); white-space: nowrap;
            font-size: 12px; font-weight: 700; color: var(--text-muted); cursor: pointer;
            display: flex; align-items: center; gap: 6px; transition: 0.3s;
        }
        .tab-btn.active { color: white; box-shadow: 0 3px 8px rgba(0,0,0,0.15); border-color: transparent; }
        .tab-btn[data-mode="general"].active { background-color: #2e7d32; }
        .tab-btn[data-mode="thinness"].active { background-color: #1565c0; }
        .tab-btn[data-mode="child-thinness"].active { background-color: #00838f; }
        .tab-btn[data-mode="child-obesity"].active { background-color: #e65100; }

        .card-box {
            background: var(--card-bg); border-radius: var(--radius-lg);
            padding: 18px; margin-bottom: 16px; box-shadow: var(--shadow-sm);
            border: 1px solid var(--border-color);
        }
        .card-title {
            font-size: 14px; font-weight: 700; margin-bottom: 12px;
            display: flex; align-items: center; gap: 8px; color: var(--dark);
        }

        .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }
        .field-group { margin-bottom: 10px; }
        .field-group.full { grid-column: span 2; }
        label { font-size: 11px; font-weight: 700; color: var(--text-muted); margin-bottom: 4px; display: block; }
        input, select, textarea {
            width: 100%; padding: 12px; border-radius: var(--radius-md);
            border: 1px solid var(--border-color); background: #f8fafc;
            font-size: 14px; font-weight: 600; color: var(--text-main); outline: none;
            box-sizing: border-box;
        }
        textarea { resize: vertical; }

        .btn-submit {
            width: 100%; padding: 14px; border-radius: var(--radius-md);
            border: none; background: var(--primary); color: white;
            font-size: 14px; font-weight: 700; cursor: pointer;
            display: flex; align-items: center; justify-content: center; gap: 8px;
            transition: 0.3s; margin-top: 10px;
        }
        .btn-submit:hover { background-color: var(--dark); }

        .btn-whatsapp {
            background-color: #25d366; color: white; border: none; padding: 12px;
            border-radius: var(--radius-md); font-weight: bold; width: 100%;
            margin-top: 10px; cursor: pointer; display: flex; align-items: center; justify-content: center; gap: 8px;
        }
        .btn-whatsapp:hover { background-color: #128c7e; }

        .result-box {
            margin-top: 25px; padding: 16px; background-color: var(--light);
            border-right: 5px solid var(--primary); border-radius: var(--radius-md);
            display: none;
        }

        .grid-3 {
            display: grid; grid-template-columns: repeat(3, 1fr);
            gap: 8px; margin-top: 12px; text-align: center;
        }
        .card { background: white; padding: 10px 6px; border-radius: var(--radius-sm); border: 1px solid var(--card-border); }
        .card strong { font-size: 10px; color: var(--text-muted); display: block; }
        .card p { font-size: 13px; font-weight: 800; color: var(--dark); margin-top: 4px; }

        .day-card {
            background: white; border: 1px solid var(--card-border);
            border-radius: var(--radius-md); margin-top: 16px; padding: 14px;
        }
        .day-header {
            display: flex; justify-content: space-between; align-items: center;
            background-color: var(--primary); color: white; padding: 8px 12px;
            border-radius: var(--radius-sm); margin-bottom: 12px;
        }
        .day-title { font-weight: bold; font-size: 14px; }
        .cycle-badge { background: rgba(255,255,255,0.25); padding: 3px 8px; border-radius: 20px; font-size: 11px; }

        .meal-row {
            display: flex; flex-direction: column; gap: 5px;
            margin-bottom: 10px; padding-bottom: 8px; border-bottom: 1px dashed #e0e0e0;
        }
        .meal-name { font-weight: bold; color: var(--dark); font-size: 12px; }
        .meal-selects { display: flex; gap: 6px; flex-wrap: wrap; }
        .meal-selects select { flex: 1; min-width: 140px; background-color: #fafafa; font-size: 11px; padding: 8px; font-weight: 700; }

        /* الألوان الدلالية للخيارات بناءً على الحالة الطبية */
        .opt-green { color: #1b5e20; background-color: #e8f5e9; font-weight: bold; }
        .opt-blue { color: #0d47a1; background-color: #e3f2fd; }
        .opt-red { color: #b71c1c; background-color: #ffebee; text-decoration: line-through; }

        .color-legend {
            display: flex; gap: 15px; font-size: 11px; font-weight: 700; margin: 10px 0; justify-content: center; flex-wrap: wrap;
            background: white; padding: 8px; border-radius: var(--radius-sm); border: 1px solid var(--border-color);
        }
        .legend-item { display: flex; align-items: center; gap: 4px; }
        .dot { width: 10px; height: 10px; border-radius: 50%; display: inline-block; }
        .dot.green { background: #2e7d32; }
        .dot.blue { background: #1565c0; }
        .dot.red { background: #c62828; }

        .day-summary {
            background: var(--summary-bg); padding: 10px; border-radius: var(--radius-sm);
            margin-top: 12px; display: flex; justify-content: space-around;
            font-weight: bold; color: var(--summary-text); font-size: 11px; flex-wrap: wrap; gap: 5px;
        }

        .tips-box {
            background: #fffde7; border: 1px solid #fff59d; border-radius: var(--radius-md);
            padding: 12px; margin-top: 16px; font-size: 12px; line-height: 1.5;
        }
        .tips-box h5 { margin: 0 0 6px 0; color: #f57f17; font-size: 13px; }
        .tips-box ul { padding-right: 15px; }

        @media print {
            button, .btn-whatsapp, form, h2, .tabs-header, .color-legend { display: none !important; }
            body { background: white; padding: 0; height: auto; overflow: visible; }
            .app-container { height: auto; overflow: visible; }
            .result-box { display: block !important; border: none; padding: 0; background: white; }
            select { border: none; background: transparent; appearance: none; font-weight: bold; padding: 0; }
        }
    </style>
</head>
<body data-theme="general">

<div class="app-container">
    <div class="app-header">
        <div class="user-badge">
            <div class="avatar" id="avatarLetter">أ</div>
            <div class="user-info">
                <h4>صحتك حياتك</h4>
                <p>عيادة التغذية العلاجية</p>
            </div>
        </div>
    </div>

    <div class="app-content">
        <div class="tabs-header">
            <button class="tab-btn active" data-mode="general" onclick="switchMode('general')"><i class="fa-solid fa-stethoscope"></i> العامة والتدقيق</button>
            <button class="tab-btn" data-mode="thinness" onclick="switchMode('thinness')"><i class="fa-solid fa-dumbbell"></i> النحافة وزيادة الوزن</button>
            <button class="tab-btn" data-mode="child-thinness" onclick="switchMode('child-thinness')"><i class="fa-solid fa-child"></i> نحافة الأطفال</button>
            <button class="tab-btn" data-mode="child-obesity" onclick="switchMode('child-obesity')"><i class="fa-solid fa-child-reaching"></i> سمنة الأطفال</button>
        </div>

        <div class="card-box">
            <h3 id="pageTitle" style="font-size: 15px; margin-bottom: 12px; text-align: center;">استمارة التقييم والتصنيف اللوني الذكي 🩺</h3>

            <form id="nutritionForm">
                <div class="field-group full">
                    <label id="lbl-name">الاسم بالكامل:</label>
                    <input type="text" id="name" required placeholder="أدخل الاسم" value="أيمن كمال">
                </div>

                <div class="form-grid">
                    <div class="field-group">
                        <label id="lbl-age">السن:</label>
                        <input type="number" id="age" required min="1" max="120" value="28">
                    </div>
                    <div class="field-group">
                        <label>النوع:</label>
                        <select id="gender" required>
                            <option value="male">ذكر</option>
                            <option value="female">أنثى</option>
                        </select>
                    </div>
                </div>

                <div class="form-grid">
                    <div class="field-group">
                        <label>الوزن (كجم):</label>
                        <input type="number" id="weight" step="0.1" required min="3" max="300" value="72">
                    </div>
                    <div class="field-group">
                        <label>الطول (سم):</label>
                        <input type="number" id="height" required min="40" max="250" value="175">
                    </div>
                </div>

                <div class="field-group">
                    <label>مستوى النشاط البدني:</label>
                    <select id="activity">
                        <option value="1.2">خامل (مكتب ولا أمارس الرياضة)</option>
                        <option value="1.375">نشاط خفيف (تمارين 1-3 أيام/أسبوع)</option>
                        <option value="1.55" selected>نشاط متوسط (تمارين 3-5 أيام/أسبوع)</option>
                        <option value="1.725">نشاط عالي (تمارين شاقة يومياً)</option>
                    </select>
                </div>

                <div class="field-group" id="strategyGroup">
                    <label id="lbl-strategy">الهدف الرئيسي:</label>
                    <select id="strategyOptions"></select>
                </div>

                <div class="field-group">
                    <label>الحالات المرضية الخاصة والأمراض الصدرية:</label>
                    <select id="medicalCondition" onchange="applyMedicalAdjustments()">
                        <option value="none">حالة عادية / لا توجد أمراض مزمنة</option>
                        <option value="ba">الربو / حساسية الصدر (BA - Bronchial Asthma)</option>
                        <option value="copd">الانسداد الرئوي المزمن وتوسع القصبات (COPD [Emphysema - Bronchiectasis] - دهون عالية وسعرات)</option>
                        <option value="ild">التليف الرئوي وأمراض الخلالي الرئوي (ILD [Hypersensitivity pneumonitis - IPF - Fibrosis])</option>
                        <option value="pe">الانسداد الرئوي (Pulmonary Embolism - تحذير فيتامين K 🔴)</option>
                        <option value="tb">الدرن / السل (TB - Tuberculosis - طاقة وبروتين عالي)</option>
                        <option value="pneumonia">الالتهاب الرئوي الحاد (Pneumonia)</option>
                        <option value="sarcoidosis">الساركويد (Sarcoidosis - ضبط الكالسيوم)</option>
                        <option value="asbestosis">الأسبستوز (Asbestosis)</option>
                        <option value="corticosteroids">مرضى العلاج بالكورتيزون (Corticosteroid therapy - تحكم أملاح وسكر)</option>
                        <option value="celiac">حساسية الجلوتين المفرطة / السيلياك (Celiac)</option>
                        <option value="g6pd">أنيميا الفول (G6PD Deficiency - منع البقوليات)</option>
                        <option value="ckd">أمراض الكلى المزمنة (تعديل البروتين والتقييد)</option>
                        <option value="diabetes">مرض السكري (مؤشر جلايسيمي منخفض)</option>
                        <option value="hypertension">ارتفاع ضغط الدم (تقليل الصوديوم)</option>
                        <option value="hypothyroidism">قصور الغدة الدرقية</option>
                        <option value="cancer">دعم مرضى السرطان</option>
                    </select>
                </div>

                <div class="field-group">
                    <label>التاريخ الطبي / ملاحظات إضافية:</label>
                    <textarea id="medicalHistory" rows="2" placeholder="ملاحظات الهضم والتحذيرات الطبية..."></textarea>
                </div>

                <button type="button" class="btn-submit" onclick="generatePlan()">
                    <i class="fa-solid fa-wand-magic-sparkles"></i> حساب وإنشاء خطة التدوير مع التصنيف اللوني
                </button>
            </form>
        </div>

        <div class="result-box" id="resultBox">
            <h3 id="resultHeader" style="font-size: 14px; text-align: center; color: var(--dark); margin-bottom: 8px;">التقرير التغذوي وخطة الـ 6 أيام</h3>
            <p id="patientInfo" style="text-align: center; font-weight: bold; font-size: 12px;"></p>
            <p id="targetCalories" style="font-weight:bold; color:var(--dark); text-align:center; font-size: 12px; margin-top: 4px;"></p>

            <div class="color-legend">
                <span class="legend-item"><span class="dot green"></span> الأخضر: ضروري ومثالي</span>
                <span class="legend-item"><span class="dot blue"></span> الأزرق: مسموح ومناسب</span>
                <span class="legend-item"><span class="dot red"></span> الأحمر: ممنوع / محذور طبياً</span>
            </div>

            <div class="grid-3">
                <div class="card"><strong>متوسط البروتين</strong><p id="proteinVal">-</p></div>
                <div class="card"><strong>متوسط الكارب</strong><p id="carbVal">-</p></div>
                <div class="card"><strong>متوسط الدهون</strong><p id="fatVal">-</p></div>
            </div>

            <div class="tips-box" id="clinicalTips">
                <h5>⚠️ إرشادات السلامة الطبية وتوجيهات الحالات الخاصة:</h5>
                <ul id="tipsList">
                    <li>تم تلوين الأغذية بناءً على التوجيه الإكلينيكي للحالة المحددة (أخضر للضروري، أزرق للمسموح، أحمر للممنوع).</li>
                </ul>
            </div>

            <h4 style="margin-top: 20px; font-size: 13px; color: var(--dark);">جدول الوجبات والبدائل مع التدقيق اللحظي:</h4>
            <div id="sixDaysContainer"></div>

            <button type="button" style="margin-top:16px; width:100%; padding:12px; background:#424242; color:white; border:none; border-radius:var(--radius-md); font-weight:bold; cursor:pointer;" onclick="window.print()">
                <i class="fa-solid fa-print"></i> طباعة التقرير / حفظ PDF
            </button>
            <button type="button" class="btn-whatsapp" onclick="sendToWhatsApp()">
                <i class="fa-brands fa-whatsapp"></i> إرسال عبر واتساب العيادة
            </button>
        </div>
    </div>
</div>

<script>
const foodExchangesData = {
    starch: [
        ["❌ بدون (إلغاء النشويات)", 0, 0, 0, 0, "blue"],
        ["[جلوتين] 1/2 رغيف بلدي مصري", 80, 15, 3, 0, "blue"],
        ["[جلوتين] 1 رغيف بلدي مصري كامل", 160, 30, 6, 0, "blue"],
        ["[جلوتين] 1 شريحة توست أبيض", 80, 15, 3, 1, "blue"],
        ["[جلوتين] 1 خبز صامولي/فينو متوسط", 160, 30, 6, 2, "blue"],
        ["[جلوتين] 1 حبة سميط مصري صغير", 200, 38, 6, 3, "blue"],
        ["[جلوتين] 1 كوب مكرونة مطبوخة", 160, 30, 6, 0, "blue"],
        ["[جلوتين] 1 طبق مكرونة بالبشاميل (200جم)", 350, 32, 14, 18, "blue"],
        ["[جلوتين] 1 طبق كشري مصري متوسط (250جم)", 380, 65, 12, 8, "blue"],
        ["[خالي جلوتين][منخفض جلايسيمي] 1/2 كوب أرز مطبوخ", 80, 15, 3, 0, "green"],
        ["[خالي جلوتين][منخفض جلايسيمي] 1 كوب أرز بسمتي مطبوخ", 160, 30, 6, 0, "green"],
        ["[خالي جلوتين][منخفض جلايسيمي] 1/2 كوب كينوا مطبوخة", 110, 20, 4, 2, "green"],
        ["[خالي جلوتين] 1 ثمرة بطاطس مشوية (180جم)", 160, 30, 6, 0, "blue"],
        ["[خالي جلوتين] 1 ثمرة بطاطا حلوة كبيرة", 160, 30, 6, 0, "blue"],
        ["[خالي جلوتين][منخفض جلايسيمي] 1/2 كوب ذرة صفراء مسلوقة", 90, 19, 3, 1, "blue"],
        ["[منخفض جلايسيمي] 1/2 رغيف أسمر/سن", 80, 15, 3, 0, "green"],
        ["[منخفض جلايسيمي] 1 خبز شوفان متوسط", 90, 16, 4, 1, "green"],
        ["1 طبق محشي مشكل (حوالي 8-10 أصابع)", 320, 45, 7, 12, "blue"],
        ["[خالي جلوتين] 1 كوب قلقاس مطبوخ (150جم)", 115, 25, 2, 0, "blue"]
    ],
    legumes: [
        ["❌ بدون (إلغاء البقوليات)", 0, 0, 0, 0, "blue"],
        ["[عالي بوتاسيوم] 1/2 كوب فول مدمس بالزيت الخفيف", 120, 15, 7, 3, "blue"],
        ["[عالي بوتاسيوم] 1/2 كوب عدس أصفر/أخضر مطبوخ", 115, 20, 9, 0.5, "blue"],
        ["[عالي بوتاسيوم] 1/2 كوب حمص الشام مسلوق", 135, 22, 7, 2, "blue"],
        ["[عالي بوتاسيوم] 1/2 كوب فاصوليا بيضاء مطبوخة", 125, 22, 8, 0.5, "blue"],
        ["[عالي بوتاسيوم] 1/2 كوب لوبيا مطبوخة", 110, 19, 7, 0.5, "blue"],
        ["1/2 كوب ترمس مسلوق ومملح", 100, 8, 13, 3, "blue"],
        ["2 قرص طعمية / فلافل مشوية بالفرن", 140, 14, 5, 7, "blue"],
        ["2 قرص طعمية مقلية مصرية تقليدية", 210, 14, 5, 15, "blue"]
    ],
    protein: [
        ["❌ بدون (إلغاء البروتين)", 0, 0, 0, 0, "blue"],
        ["بياض بيضة واحدة", 17, 0, 3.6, 0.1, "blue"],
        ["30جم صدر دجاج مطبوخ", 55, 0, 7, 3, "blue"],
        ["90جم صدر دجاج مطبوخ", 165, 0, 21, 9, "green"],
        ["90جم لحم بقر كاندوز مشوي", 165, 0, 21, 9, "blue"],
        ["90جم لحم غزال مشوي (بروتين عالي ودعم تنفسي)", 175, 0, 24, 8, "green"],
        ["90جم لحم نعام مشوي (صحي وقليل الدهون)", 160, 0, 23, 7, "green"],
        ["90جم ديك رومي مطبوخ", 170, 0, 25, 6, "green"],
        ["90جم سمك بلطي / بوري مشوي", 165, 0, 21, 9, "blue"],
        ["1 بيضة مسلوقة كاملة", 75, 0, 7, 5, "blue"],
        ["100جم جبن قريش (بدون زيت - منخفض الفسفور)", 80, 3, 11, 2, "green"],
        ["100جم كبدة بقري مطبوخة [تحذير PE: غنية بفيتامين K]", 175, 1, 26, 7, "blue"],
        ["[تغطية بجلوتين] 1 قطعة بانيه فراخ مقلي (100جم)", 260, 12, 18, 15, "blue"],
        ["1 سمكة بلطي/بوري مقلية متوسطة (150جم)", 310, 5, 26, 20, "blue"],
        ["[عالي الصوديوم] 50جم لانشون بقري", 150, 1, 6, 13, "blue"],
        ["[عالي الصوديوم] 50جم لانشون فراخ", 130, 2, 7, 10, "blue"],
        ["[عالي الصوديوم] 50جم بسطرمة", 130, 0, 13, 8, "blue"],
        ["[معلبات] 1 علبة تونة مصفاة (185جم)", 190, 0, 42, 2.5, "green"]
    ],
    veg: [
        ["❌ بدون (إلغاء الخضار)", 0, 0, 0, 0, "blue"],
        ["1 كوب سلطة خضراء بملعقة زيت زيتون", 70, 5, 2, 5, "green"],
        ["1 كوب خيار وطماطم مقطعة", 25, 5, 1, 0, "blue"],
        ["[منخفض بوتاسيوم] 1/2 كوب كوسة مسلوقة", 25, 4, 1, 0, "green"],
        ["[عالي بوتاسيوم و فيتامين K] 1/2 كوب بروكلي مطبوخ", 25, 5, 2, "blue"],
        ["[عالي فيتامين K جداً] 1/2 كوب سبانخ مسلوقة", 20, 3, 2, 0, "blue"]
    ],
    fruit: [
        ["❌ بدون (إلغاء الفاكهة)", 0, 0, 0, 0, "blue"],
        ["[منخفض جلايسيمي] 1 ثمرة تفاح متوسطة", 60, 15, 0, 0, "green"],
        ["[عالي جلايسيمي/بوتاسيوم] 1 ثمرة موز متوسطة", 105, 27, 1, 0, "blue"],
        ["[عالي سكر] 3 حبات تمر جاف/رطب", 60, 15, 0, 0, "blue"]
    ],
    milk: [
        ["❌ بدون (إلغاء الحليب/الزبادي)", 0, 0, 0, 0, "blue"],
        ["[عالي الفسفور] 1 كوب حليب خالي الدسم", 90, 12, 8, 0, "blue"],
        ["[عالي الفسفور] 1 كوب حليب كامل الدسم", 150, 12, 8, 8, "blue"],
        ["[عالي الفسفور] 1 علبة زبادي كامل الدسم (170جم)", 140, 10, 7, 8, "blue"]
    ],
    fat: [
        ["❌ بدون (إلغاء الدهون المضافة)", 0, 0, 0, 0, "blue"],
        ["1 ملعقة صغيرة زيت زيتون (ضروري ومضاد للأكسدة)", 45, 0, 0, 5, "green"],
        ["1 ملعقة كبيرة زيت زيتون (ممتاز لمرضى COPD وILD)", 135, 0, 0, 15, "green"],
        ["30جم جبن رومي (تركية - عالية الصوديوم)", 115, 0, 7, 10, "blue"],
        ["30جم جبن ريكفور / أزرق", 105, 0.5, 6, 9, "blue"],
        ["2 قطعة جبنة مثلثات", 90, 1, 2, 8, "blue"]
    ],
    sweets: [
        ["❌ بدون (إلغاء الحلويات والبسكويت)", 0, 0, 0, 0, "blue"],
        ["قطعة بسبوسة شرقي (100جم)", 380, 55, 4, 16, "blue"],
        ["قطعة كنافة بالقشطة (100جم)", 400, 48, 6, 21, "blue"],
        ["قطعة جاتوه شوكولاتة غربي", 320, 42, 4, 15, "blue"],
        ["3 حبات بسكويت أوريو (Oreo)", 160, 25, 2, 7, "blue"],
        ["عبوة بسكويت سادة (تاو تاو / اولكر - 40جم)", 180, 26, 3, 7, "blue"],
        ["50جم بسكويت مالح", 240, 32, 4, 11, "blue"],
        ["كوب عصير مانجو طبيعي أو معلب (250 مل)", 140, 35, 1, 0, "blue"],
        ["علبة مياه غازية عادية (330 مل)", 140, 38, 0, 0, "blue"],
        ["عبوة مشروب طاقة (250 مل)", 115, 28, 1, 0, "blue"]
    ],
    smoothie: [
        ["❌ بدون (إلغاء السموذي)", 0, 0, 0, 0, "blue"],
        ["سموذي الطاقة المكثف (حليب + موز + شوفان + عسل)", 450, 60, 14, 18, "green"],
        ["سموذي التمر والمكسرات الفاخر (يصل إلى 700 سعر)", 700, 85, 18, 32, "green"],
        ["سموذي الشوكولاتة وزبدة الفول السوداني (يصل إلى 700 سعر)", 700, 78, 22, 35, "green"]
    ]
};

const cyclingPattern = [
    { day: 1, name: "High Carb / Normal Protein", carbFactor: 1.35, protFactor: 0.85 },
    { day: 2, name: "Moderate Carb / Moderate Protein", carbFactor: 1.0, protFactor: 1.0 },
    { day: 3, name: "Low Carb / High Protein", carbFactor: 0.65, protFactor: 1.25 },
    { day: 4, name: "Moderate Carb / Normal Protein", carbFactor: 1.0, protFactor: 1.0 },
    { day: 5, name: "High Carb / Normal Protein", carbFactor: 1.35, protFactor: 0.85 },
    { day: 6, name: "Low Carb / High Protein", carbFactor: 0.65, protFactor: 1.25 }
];

let currentMode = 'general';
let calculatedData = {};

const modeConfigs = {
    'general': {
        title: "استمارة التقييم والتصنيف اللوني الذكي للأمراض 🩺",
        btnText: "حساب الاحتياجات وإنشاء نظام 6 أيام",
        resultTitle: "التقرير التغذوي وخطة الـ 6 أيام",
        strategies: [
            { val: "lose", text: "خسارة وزن (-500 سعرة)" },
            { val: "maintain", text: "ثبات وزن" },
            { val: "gain", text: "زيادة وزن / عضلات (+400 سعرة)" }
        ],
        tips: [
            "<strong>اللون الأخضر:</strong> أطعمة ضرورية ومثالية للحالة (مثل الدهون النافعة والبروتين النظيف لمرضى الصدر).",
            "<strong>اللون الأزرق:</strong> أطعمة مسموحة ومحايدة.",
            "<strong>اللون الأحمر:</strong> أطعمة ممنوعة ومحظورة (تتم جدولتها باللون الأحمر المخصص)."
        ]
    },
    'thinness': {
        title: "برنامج علاج النحافة وزيادة الوزن وسموذي الـ 700 سعر 🏋️‍♂️💪",
        btnText: "حساب الاحتياجات وخطة التسمين المكثفة",
        resultTitle: "تقرير علاج النحافة وخطة الزيادة",
        strategies: [
            { val: "600", text: "زيادة مكثفة منظمة (+600 سعرة/يوم)" },
            { val: "800", text: "زيادة عالية السعرات (+800 سعرة/يوم)" }
        ],
        tips: [
            "<strong>سموذي الـ 700 سعر (أخضر):</strong> خيار مثالي ومكثف لرفع السعرات دون امتلاء المعدة.",
            "استخدم الوجبات الصغيرة المتكررة لضمان سهولة الهضم."
        ]
    },
    'child-thinness': {
        title: "برنامج علاج نحافة الأطفال والنمو التعويضي (Catch-up Growth) 🧒🥣",
        btnText: "حساب احتياجات الطفل وإنشاء نظام الـ 6 أيام",
        resultTitle: "تقرير التغذية وخطة علاج نحافة الطفل",
        strategies: [
            { val: "400", text: "زيادة منظمة للنمو التعويضي (+400 سعرة/يوم)" },
            { val: "600", text: "زيادة مكثفة لنحافة الطفل الشديدة (+600 سعرة/يوم)" }
        ],
        tips: [
            "تقديم العصائر والمشروبات المغذية عقب الوجبات لتفادي الشبع المبكر.",
            "التركيز على العناصر الخضراء الداعمة للنمو السليم."
        ]
    },
    'child-obesity': {
        title: "برنامج إدارة وزن الأطفال ودعم النمو (Pediatric Obesity) 👶🧒",
        btnText: "حساب احتياجات الطفل وإنشاء نظام الـ 6 أيام",
        resultTitle: "تقرير التغذية وخطة إدارة الوزن والنمو للطفل",
        strategies: [
            { val: "maintain", text: "ثبات الوزن وتعديل القوام مع الطول" },
            { val: "mild_loss", text: "نزول بطيء جداً وآمن (-250 سعرة/يوم)" }
        ],
        tips: [
            "تمت فلترة الخيارات عالية السعرات والحلويات لضمان الشبع بأقل سعرات.",
            "التركيز على الألياف والبروتينات الخفيفة لدعم النمو السليم."
        ]
    }
};

function applyMedicalAdjustments() {
    const condition = document.getElementById('medicalCondition').value;
    const medicalHistoryArea = document.getElementById('medicalHistory');
    let note = "";
    switch(condition) {
        case 'ba': note = "توجيه طبي (الربو / BA): تجنب الأغذية المهيجة، وتقليل الوجبات الكبيرة لتخفيف الضغط على الحجاب الحاجز."; break;
        case 'copd': note = "توجيه طبي (COPD): زيادة نسب الدهون (زيت الزيتون والسموذي العالي) وتقليل الكربوهيدرات البسيطة لتقليل ثاني أكسيد الكربون."; break;
        case 'ild': note = "توجيه طبي (التليف الرئوي / ILD): دعم عالي بالبروتين ومضادات الأكسدة وسعرات مركزة لتقليل الجهد التنفسي."; break;
        case 'pe': note = "تحذير طبي صارم (الانسداد الرئوي PE): يجب الحذر الشديد من أغذية فيتامين K (مثل السبانخ والبروكلي والكبدة) للمتعاطين لمضادات التخثر (تظهر بالأحمر/الأزرق المحذر)."; break;
        case 'tb': note = "توجيه طبي (الدرن / TB): نظام استهلاكي عالي السعرات والبروتين (بروتين عالي + سموذي 700 سعر) لتعويض الهدم."; break;
        case 'pneumonia': note = "توجيه طبي (الالتهاب الرئوي): سوائل كافية، طاقة عالية، ودعم مناعي بالبروتين."; break;
        case 'sarcoidosis': note = "توجيه طبي (الساركويد): تقييد نسب الكالسيوم وفيتامين D الزائد حسب التوجيه الطبي."; break;
        case 'asbestosis': note = "توجيه طبي (الأسبستوز): دعم تنفسي وتغذوي شامل لتقليل الجهد الأكسدي."; break;
        case 'corticosteroids': note = "توجيه طبي (مرضى الكورتيزون): تقليل الأملاح والصوديوم لمنع احتباس السوائل، التحكم بالكربوهيدرات، وزيادة الكالسيوم والبروتين."; break;
        case 'celiac': note = "تحذير طبي صارم (حساسية الجلوتين / السيلياك): تم وسم أطعمة الجلوتين باللون الأحمر الممنوع تلقائياً."; break;
        case 'g6pd': note = "تحذير طبي (أنيميا الفول): تم وسم البقوليات باللون الأحمر الممنوع."; break;
        case 'ckd': note = "اعتبار طبي (أمراض الكلى المزمنة): تقليل البروتين والبوتاسيوم والفسفور."; break;
        case 'diabetes': note = "اعتبار طبي (مرض السكري): تفعيل خيارات المؤشر الجلايسيمي المنخفض ووسم الحلويات والسكريات باللون الأحمر."; break;
        case 'hypertension': note = "اعتبار طبي (ارتفاع الضغط): يُشدد على تقليل الملح وتجنب الأغذية المملحة العالية الصوديوم."; break;
        case 'hypothyroidism': note = "اعتبار طبي (قصور الغدة الدرقية): الاعتماد على انتظام الدواء وتجنب التجويع."; break;
        case 'cancer': note = "اعتبار طبي (دعم السرطان): رفع نسبة البروتين والسعرات لمقاومة الهدم العضلي."; break;
        default: note = "";
    }
    medicalHistoryArea.value = note;
    // تحديث القوائم لتطبيق التصنيف اللوني الجديد فوراً
    if(document.getElementById('resultBox').style.display === 'block') {
        generatePlan();
    }
}

function switchMode(mode) {
    currentMode = mode;
    document.body.setAttribute('data-theme', mode);

    document.querySelectorAll('.tab-btn').forEach(btn => {
        btn.classList.toggle('active', btn.dataset.mode === mode);
    });

    const config = modeConfigs[mode];
    document.getElementById('pageTitle').innerText = config.title;
    document.querySelector('.btn-submit').innerHTML = `<i class="fa-solid fa-wand-magic-sparkles"></i> ${config.btnText}`;
    document.getElementById('resultHeader').innerText = config.resultTitle;

    const tipsContainer = document.getElementById('tipsList');
    tipsContainer.innerHTML = config.tips.map(t => `<li>${t}</li>`).join('');

    const ageInput = document.getElementById('age');
    if (mode.startsWith('child')) {
        document.getElementById('lbl-name').innerText = "اسم الطفل بالكامل:";
        document.getElementById('lbl-age').innerText = "العمر (من 3 إلى 18 سنة):";
        ageInput.min = 3; ageInput.max = 18; ageInput.value = 10;
    } else {
        document.getElementById('lbl-name').innerText = "الاسم بالكامل:";
        document.getElementById('lbl-age').innerText = "السن:";
        ageInput.min = 18; ageInput.max = 100; ageInput.value = 28;
    }

    const select = document.getElementById('strategyOptions');
    if (select) {
        select.innerHTML = config.strategies.map(s => `<option value="${s.val}">${s.text}</option>`).join('');
    }

    document.getElementById('resultBox').style.display = 'none';
}

function getMappedColor(itemText, originalColor, condition) {
    // تحديد اللون بناءً على الحالة المرضية المحددة ديناميكياً
    if (condition === 'celiac' && (itemText.includes('[جلوتين]') || itemText.includes('مكرونة بالبشاميل') || itemText.includes('كشري'))) {
        return 'red';
    }
    if (condition === 'g6pd' && (itemText.includes('فول') || itemText.includes('عدس') || itemText.includes('حمص') || itemText.includes('فاصوليا') || itemText.includes('لوبيا') || itemText.includes('ترمس'))) {
        return 'red';
    }
    if (condition === 'pe' && (itemText.includes('فيتامين K') || itemText.includes('سبانخ') || itemText.includes('بروكلي') || itemText.includes('كبدة'))) {
        return 'red';
    }
    if (condition === 'diabetes' && (itemText.includes('عصير مانجو') || itemText.includes('مياه غازية') || itemText.includes('بسبوسة') || itemText.includes('كنافة') || itemText.includes('شوكولاتة') || itemText.includes('تمر'))) {
        return 'red';
    }
    if (condition === 'ckd' && (itemText.includes('[عالي بوتاسيوم]') || itemText.includes('[عالي الفسفور]'))) {
        return 'red';
    }
    return originalColor; // 'green', 'blue', or 'red'
}

function buildDropdown(type, dayIndex, selectedIndex = 0) {
    let list = foodExchangesData[type] || [];
    const condition = document.getElementById('medicalCondition') ? document.getElementById('medicalCondition').value : 'none';

    let options = list.map((item, idx) => {
        const itemText = item[0];
        const originalColor = item[5] || 'blue';
        const mappedColor = getMappedColor(itemText, originalColor, condition);
        
        let prefixMark = "🔵 ";
        let cssClass = "opt-blue";
        if (mappedColor === 'green') {
            prefixMark = "🟢 ";
            cssClass = "opt-green";
        } else if (mappedColor === 'red') {
            prefixMark = "🔴 ";
            cssClass = "opt-red";
        }

        const text = item[1] === 0 ? itemText : `${prefixMark}${itemText} (${item[1]} كال | ${item[2]}ج ك | ${item[3]}ج ب | ${item[4]}ج د)`;
        return `<option value="${item[1]},${item[2]},${item[3]},${item[4]}" class="${cssClass}" ${idx === selectedIndex ? 'selected' : ''}>${text}</option>`;
    }).join('');
    
    return `<select class="food-select day-${dayIndex}" data-type="${type}" onchange="recalculateDay(${dayIndex})">${options}</select>`;
}

function getDayTotals(dayIndex) {
    const selects = document.querySelectorAll(`.food-select.day-${dayIndex}`);
    let calories = 0, carbs = 0, protein = 0, fat = 0;
    selects.forEach(select => {
        const values = select.value.split(',').map(Number);
        calories += values[0]; carbs += values[1]; protein += values[2]; fat += values[3];
    });
    return { calories, carbs, protein, fat };
}

function recalculateDay(dayIndex) {
    const totals = getDayTotals(dayIndex);
    document.getElementById(`day-${dayIndex}-cal`).innerText = Math.round(totals.calories);
    document.getElementById(`day-${dayIndex}-carb`).innerText = Math.round(totals.carbs * 10) / 10;
    document.getElementById(`day-${dayIndex}-prot`).innerText = Math.round(totals.protein * 10) / 10;
    document.getElementById(`day-${dayIndex}-fat`).innerText = Math.round(totals.fat * 10) / 10;
}

function autoAdjustSelections(baseTargetCal, baseProteinGrams, baseCarbGrams, baseFatGrams) {
    for (let d = 1; d <= 6; d++) {
        const cycle = cyclingPattern[d - 1];
        const targetDayCarb = Math.round(baseCarbGrams * cycle.carbFactor);
        const targetDayProt = Math.round(baseProteinGrams * cycle.protFactor);
        const targetDayCal = Math.round((targetDayCarb * 4) + (targetDayProt * 4) + (baseFatGrams * 9));
        smartFoodDistribution(targetDayCal, targetDayProt, targetDayCarb, baseFatGrams, d);
    }
}

function smartFoodDistribution(targetCal, targetProt, targetCarb, targetFat, dayIndex) {
    const selects = Array.from(document.querySelectorAll(`.food-select.day-${dayIndex}`));
    selects.forEach(s => s.selectedIndex = 0);
    
    const getCurrentTotals = () => {
        let cal = 0, carb = 0, prot = 0, fat = 0;
        selects.forEach(s => {
            const vals = s.value.split(',').map(Number);
            cal += vals[0]; carb += vals[1]; prot += vals[2]; fat += vals[3];
        });
        return { cal, carb, prot, fat };
    };

    const typePriority = { 'protein': 1, 'starch': 2, 'fat': 3, 'sweets': 4, 'legumes': 5, 'milk': 6, 'fruit': 7, 'veg': 8, 'smoothie': 9 };
    const prioritySelects = selects.sort((a, b) => typePriority[a.dataset.type] - typePriority[b.dataset.type]);
    const condition = document.getElementById('medicalCondition').value;
    let current = getCurrentTotals();
    
    prioritySelects.forEach(select => {
        let bestIndex = 0, minPenalty = Infinity;
        for (let i = 0; i < select.options.length; i++) {
            const optElem = select.options[i];
            // تجنب اختيار الأطعمة الحمراء (الممنوعة) تماماً أثناء التوزيع التلقائي الذكي
            if (optElem.classList.contains('opt-red')) continue;

            const vals = optElem.value.split(',').map(Number);
            const itemCal = vals[0], itemCarb = vals[1], itemProt = vals[2], itemFat = vals[3];
            if ((current.cal + itemCal) <= targetCal) {
                const diffProt = Math.max(0, targetProt - (current.prot + itemProt));
                const diffCarb = Math.max(0, targetCarb - (current.carb + itemCarb));
                const diffFat = Math.max(0, targetFat - (current.fat + itemFat));
                let penalty = (diffProt * 4) + (diffCarb * 4) + (diffFat * 9);
                
                // تفضيل العناصر الخضراء (الضرورية والمثالية) في حالات الصدر أو التسمين
                if (optElem.classList.contains('opt-green')) {
                    penalty -= 50; 
                }

                if (penalty < minPenalty) { minPenalty = penalty; bestIndex = i; }
            }
        }
        select.selectedIndex = bestIndex;
        current = getCurrentTotals(); 
    });
}

function generatePlan() {
    const name = document.getElementById('name').value;
    const age = parseFloat(document.getElementById('age').value);
    const gender = document.getElementById('gender').value;
    const weight = parseFloat(document.getElementById('weight').value);
    const height = parseFloat(document.getElementById('height').value);
    const activity = parseFloat(document.getElementById('activity').value);
    const strategyVal = document.getElementById('strategyOptions').value;
    const condition = document.getElementById('medicalCondition').value;
    const medical = document.getElementById('medicalHistory').value || "لا يوجد";

    if(!name || !age || !weight || !height) {
        alert("يرجى ملء جميع البيانات الأساسية بشكل صحيح");
        return;
    }

    let bmr = 0, target = 0, proteinGrams = 0, fatGrams = 0, carbGrams = 0;
    const bmi = (weight / ((height/100) ** 2)).toFixed(1);

    if (currentMode === 'general') {
        bmr = (10 * weight) + (6.25 * height) - (5 * age);
        bmr = (gender === 'male') ? bmr + 5 : bmr - 161;
        target = bmr * activity;
        if (strategyVal === 'lose') target -= 500;
        if (strategyVal === 'gain') target += 400;
        proteinGrams = Math.round(weight * 1.8);
        fatGrams = Math.round((target * 0.25) / 9);
    } else if (currentMode === 'thinness') {
        bmr = (10 * weight) + (6.25 * height) - (5 * age);
        bmr = (gender === 'male') ? bmr + 5 : bmr - 161;
        let calculatedTarget = (bmr * activity) + parseFloat(strategyVal);
        target = Math.max(calculatedTarget, 2200);
        proteinGrams = Math.round(weight * 2.0);
        fatGrams = Math.round((target * 0.30) / 9);
    } else if (currentMode === 'child-thinness') {
        bmr = (age <= 10) ? ((gender === 'male') ? (22.7 * weight) + 495 : (22.5 * weight) + 499) : ((gender === 'male') ? (17.5 * weight) + 651 : (12.2 * weight) + 746);
        let totalEnergy = (bmr * activity) + parseFloat(strategyVal);
        let catchUpCalories = weight * 120; 
        target = Math.max(totalEnergy, catchUpCalories, 1350);
        proteinGrams = Math.round(weight * 2.0);
        fatGrams = Math.round((target * 0.35) / 9);
    } else if (currentMode === 'child-obesity') {
        bmr = (age <= 10) ? ((gender === 'male') ? (22.7 * weight) + 495 : (22.5 * weight) + 499) : ((gender === 'male') ? (17.5 * weight) + 651 : (12.2 * weight) + 746);
        target = bmr * activity;
        if (strategyVal === 'mild_loss') target -= 250;
        proteinGrams = Math.round(weight * 1.3);
        fatGrams = Math.round((target * 0.28) / 9);
    }

    if (condition === 'hypothyroidism') target = Math.max(target, 1200);
    else if (condition === 'ckd') proteinGrams = Math.round(weight * 0.8);
    else if (condition === 'cancer' || condition === 'tb' || condition === 'copd') { proteinGrams = Math.round(weight * 2.2); target += 300; }

    target = Math.round(target);
    carbGrams = Math.max(0, Math.round((target - (proteinGrams * 4) - (fatGrams * 9)) / 4));
    calculatedData = { name, target, proteinGrams, carbGrams, fatGrams, medical };

    document.getElementById('patientInfo').innerText = `الاسم: ${name} | السن: ${age} | الوزن: ${weight}كجم | الطول: ${height}سم | BMI: ${bmi}`;
    document.getElementById('targetCalories').innerText = `متوسط السعرات المستهدفة: ${target} سعرة/يوم`;
    document.getElementById('proteinVal').innerText = `${proteinGrams} جم`;
    document.getElementById('carbVal').innerText = `${carbGrams} جم`;
    document.getElementById('fatVal').innerText = `${fatGrams} جم`;

    let daysHTML = "";
    for(let d = 1; d <= 6; d++) {
        const isThinnessMode = currentMode.includes('thinness');
        const cycle = cyclingPattern[d - 1];
        
        daysHTML += `
            <div class="day-card">
                <div class="day-header">
                    <span class="day-title">اليوم ${d}</span>
                    <span class="cycle-badge">🔄 ${cycle.name}</span>
                </div>
                
                <div class="meal-row">
                    <div class="meal-name">🍳 الإفطار:</div>
                    <div class="meal-selects">
                        ${buildDropdown('starch', d, 1)}
                        ${buildDropdown('protein', d, 1)}
                        ${buildDropdown('milk', d, 1)}
                    </div>
                </div>

                <div class="meal-row">
                    <div class="meal-name">🥤 سناك 1:</div>
                    <div class="meal-selects">
                        ${isThinnessMode ? buildDropdown('smoothie', d, 1) : buildDropdown('fruit', d, 1)}
                        ${buildDropdown('sweets', d, 0)}
                    </div>
                </div>

                <div class="meal-row">
                    <div class="meal-name">🍲 الغداء:</div>
                    <div class="meal-selects">
                        ${buildDropdown('starch', d, 2)}
                        ${buildDropdown('protein', d, 2)}
                        ${buildDropdown('legumes', d, 0)}
                        ${buildDropdown('veg', d, 1)}
                    </div>
                </div>

                <div class="meal-row">
                    <div class="meal-name">🥛 سناك 2:</div>
                    <div class="meal-selects">
                        ${buildDropdown('milk', d, 1)}
                        ${buildDropdown('sweets', d, 1)}
                    </div>
                </div>

                <div class="meal-row">
                    <div class="meal-name">🥗 العشاء:</div>
                    <div class="meal-selects">
                        ${buildDropdown('protein', d, 1)}
                        ${buildDropdown('starch', d, 1)}
                        ${buildDropdown('veg', d, 1)}
                    </div>
                </div>

                ${isThinnessMode ? `
                <div class="meal-row">
                    <div class="meal-name">🌙 سناك 3 (قبل النوم - سموذي مكثف):</div>
                    <div class="meal-selects">
                        ${buildDropdown('smoothie', d, 2)}
                    </div>
                </div>
                ` : ''}

                <div class="day-summary">
                    <span>الإجمالي: <span id="day-${d}-cal">0</span> كال</span>
                    <span>كارب: <span id="day-${d}-carb">0</span>ج</span>
                    <span>بروتين: <span id="day-${d}-prot">0</span>ج</span>
                    <span>دهون: <span id="day-${d}-fat">0</span>ج</span>
                </div>
            </div>
        `;
    }

    document.getElementById('sixDaysContainer').innerHTML = daysHTML;
    document.getElementById('resultBox').style.display = 'block';

    autoAdjustSelections(target, proteinGrams, carbGrams, fatGrams);
    for(let d = 1; d <= 6; d++) recalculateDay(d);
}

function sendToWhatsApp() {
    const phone = "201000000000";
    const text = `*تقرير التغذية والبدائل العلاجية الذكية*%0A` +
        `الاسم: ${calculatedData.name}%0A` +
        `متوسط السعرات المستهدفة: ${calculatedData.target} سعرة%0A` +
        `الماكروز: بروتين ${calculatedData.proteinGrams}ج | كارب ${calculatedData.carbGrams}ج | دهون ${calculatedData.fatGrams}ج%0A` +
        `الحالة الطبية: ${calculatedData.medical}`;
    window.open(`https://wa.me/${phone}?text=${text}`, '_blank');
}

document.addEventListener("DOMContentLoaded", function() {
    switchMode('general');
});
</script>

</body>
</html>
