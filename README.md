<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Arise System | White Room — Evaluation Zone</title>
    
    <!-- أيقونة المتصفح (favicon) حرف A أبيض -->
    <link rel="icon" type="image/svg+xml" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Crect width='100' height='100' fill='%239c27b0' rx='20'/%3E%3Ctext x='50' y='70' font-size='70' font-family='Arial, sans-serif' font-weight='bold' fill='white' text-anchor='middle'%3EA%3C/text%3E%3C/svg%3E">
    
    <!-- تحسينات لمشاركة الرابط (WhatsApp, Telegram, Facebook...) -->
    <meta property="og:title" content="Arise System | White Room">
    <meta property="og:description" content="انضم إلى غرفة التقييم – سجل بياناتك واختر قطاعك">
    <meta property="og:image" content="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 500 500'%3E%3Crect width='500' height='500' fill='%239c27b0'/%3E%3Ctext x='250' y='340' font-size='280' font-family='Arial, sans-serif' font-weight='bold' fill='white' text-anchor='middle'%3EA%3C/text%3E%3C/svg%3E">
    <meta property="og:image:width" content="500">
    <meta property="og:image:height" content="500">
    <meta property="og:type" content="website">
    <meta name="twitter:card" content="summary_large_image">
    <meta name="twitter:title" content="Arise System | White Room">
    <meta name="twitter:description" content="بوابة التسجيل في Arise - حدد هويتك وانضم للقطاع المناسب">
    <meta name="twitter:image" content="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 500 500'%3E%3Crect width='500' height='500' fill='%239c27b0'/%3E%3Ctext x='250' y='340' font-size='280' font-family='Arial, sans-serif' font-weight='bold' fill='white' text-anchor='middle'%3EA%3C/text%3E%3C/svg%3E">
    
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;600&family=Tajawal:wght@300;500;800&display=swap" rel="stylesheet">
    <style>
        :root {
            --bg-black: #050505;
            --card-bg: #111111;
            --accent-purple: #9c27b0;
            --deep-purple: #4a148c;
            --text-white: #e0e0e0;
            --glow: 0 0 15px rgba(156, 39, 176, 0.4);
        }

        * { box-sizing: border-box; -webkit-tap-highlight-color: transparent; }

        body {
            margin: 0;
            background-color: var(--bg-black);
            color: var(--text-white);
            font-family: 'Tajawal', sans-serif;
            display: flex;
            justify-content: center;
            min-height: 100vh;
        }

        .main-container {
            width: 100%;
            max-width: 600px;
            background: var(--bg-black);
            display: flex;
            flex-direction: column;
            border-left: 1px solid #222;
            border-right: 1px solid #222;
            box-shadow: 0 0 50px rgba(0,0,0,1);
        }

        .header-image {
            width: 100%;
            height: 40vh; 
            min-height: 250px;
            background-color: #000;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }
        .header-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            object-position: center;
            display: block;
        }
        .header-image::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            height: 80px;
            background: linear-gradient(to top, var(--bg-black), transparent);
            pointer-events: none;
        }

        .content-area {
            padding: clamp(15px, 5vw, 30px);
            flex-grow: 1;
        }

        .step-indicator {
            font-family: 'Montserrat', sans-serif;
            font-size: 0.75rem;
            color: var(--accent-purple);
            margin-bottom: 10px;
            letter-spacing: 2px;
            opacity: 0.8;
            display: flex;
            justify-content: space-between;
        }
        .progress-track {
            width: 100%;
            height: 3px;
            background: #222;
            border-radius: 10px;
            margin: 8px 0 15px 0;
            overflow: hidden;
        }
        .progress-fill {
            width: 0%;
            height: 100%;
            background: var(--accent-purple);
            transition: width 0.3s ease;
            box-shadow: var(--glow);
        }

        .question-card {
            display: none;
            animation: fadeIn 0.6s cubic-bezier(0.4, 0, 0.2, 1) forwards;
        }

        .question-card.active { display: block; }

        .question-text {
            font-size: clamp(1.1rem, 4vw, 1.4rem);
            font-weight: 700;
            margin-bottom: 25px;
            line-height: 1.5;
        }

        input[type="text"] {
            width: 100%;
            background: var(--card-bg);
            border: 1px solid #333;
            padding: 18px;
            color: #fff;
            border-radius: 12px;
            font-size: 1rem;
            outline: none;
            transition: 0.3s;
        }

        input[type="text"]:focus { border-color: var(--accent-purple); box-shadow: var(--glow); }

        .option-wrapper {
            margin-bottom: 10px;
        }
        .option-item {
            background: var(--card-bg);
            border: 1px solid #222;
            padding: clamp(12px, 3vw, 18px);
            border-radius: 12px;
            cursor: pointer;
            transition: all 0.3s ease;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        .option-item:hover { transform: translateY(-2px); border-color: var(--accent-purple); }
        .option-item.selected { 
            background: var(--deep-purple); 
            border-color: var(--accent-purple);
            box-shadow: var(--glow);
        }
        .info-trigger {
            background: rgba(156, 39, 176, 0.2);
            color: var(--accent-purple);
            width: 30px;
            height: 30px;
            border-radius: 50%;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            cursor: pointer;
            margin-right: 12px;
            transition: 0.2s;
            font-size: 0.9rem;
        }
        .info-trigger:hover {
            background: var(--accent-purple);
            color: white;
            box-shadow: var(--glow);
        }
        .desc-panel {
            max-height: 0;
            overflow: hidden;
            transition: max-height 0.4s ease-out;
            background: #0d0d0d;
            border-radius: 0 0 12px 12px;
            margin-top: 0px;
            margin-bottom: 0px;
        }
        .desc-panel.open {
            max-height: 180px;
            padding: 15px;
            border: 1px solid var(--accent-purple);
            border-top: none;
            border-radius: 0 0 12px 12px;
            font-size: 0.85rem;
            line-height: 1.5;
            color: #ccc;
        }

        .review-panel {
            background: rgba(0,0,0,0.6);
            border-radius: 20px;
            padding: 20px;
            margin: 15px 0;
            border: 1px solid var(--accent-purple);
            backdrop-filter: blur(4px);
            display: none;
        }
        .review-panel h3 {
            margin: 0 0 15px 0;
            font-family: 'Montserrat', sans-serif;
            color: var(--accent-purple);
        }
        .review-row {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px dashed #333;
            font-size: 0.95rem;
        }
        .review-row span:first-child { font-weight: 300; opacity: 0.8; }
        .review-row span:last-child { font-weight: 700; color: #fff; word-break: break-word; text-align: left; max-width: 60%; }
        .edit-data-btn {
            background: none;
            border: none;
            color: var(--accent-purple);
            cursor: pointer;
            font-size: 0.8rem;
            margin-top: 12px;
            font-family: 'Tajawal', sans-serif;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }
        .nav-buttons {
            margin-top: 40px;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }
        button {
            padding: 18px;
            border-radius: 12px;
            border: none;
            cursor: pointer;
            font-weight: 800;
            transition: 0.4s;
            font-family: 'Tajawal', sans-serif;
            text-transform: uppercase;
        }
        .btn-next { background: var(--accent-purple); color: white; width: 100%; }
        .btn-next:disabled { background: #222; color: #555; cursor: not-allowed; }
        .btn-arise {
            background: #fff;
            color: #000;
            width: 100%;
            font-family: 'Montserrat', sans-serif;
            letter-spacing: 4px;
            font-size: 1.2rem;
            display: none;
            box-shadow: 0 0 25px rgba(255,255,255,0.4);
        }
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .toast-msg {
            position: fixed;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%) scale(0.9);
            background: var(--deep-purple);
            color: white;
            padding: 12px 20px;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: bold;
            z-index: 999;
            opacity: 0;
            transition: 0.2s;
            pointer-events: none;
            white-space: nowrap;
            font-family: 'Tajawal', sans-serif;
            box-shadow: var(--glow);
        }
    </style>
</head>
<body>

<div class="main-container">
    <div class="header-image">
        <img src="87730.png" alt="White Room | Evaluation Zone" onerror="this.onerror=null; this.src='https://placehold.co/600x300/1a1a2e/9c27b0?text=WHITE+ROOM+Evaluation+Zone'">
    </div>

    <div class="content-area">
        <div class="step-indicator">
            <span id="step-info-text">SYSTEM // INITIALIZING_PHASE</span>
            <span id="step-counter">1/4</span>
        </div>
        <div class="progress-track"><div class="progress-fill" id="progress-fill"></div></div>
        
        <div class="question-card active" id="q1">
            <div class="question-text">ما هو المسمى الذي تود أن تُسجل به في قاعدة بيانات Arise؟</div>
            <input type="text" id="input-name" placeholder="اسمك المستعار..." autocomplete="off">
        </div>

        <div class="question-card" id="q2">
            <div class="question-text">من هو العميل الذي قام بتوجيهك إلى هذه البوابة؟</div>
            <input type="text" id="input-source" placeholder="اكتب المصدر هنا..." autocomplete="off">
        </div>

        <div class="question-card" id="q3">
            <div class="question-text">حدد رتبتك البرمجية الحالية:</div>
            <div id="level-group"></div>
        </div>

        <div class="question-card" id="q4">
            <div class="question-text">اختر القطاع المستهدف:</div>
            <div id="sector-group"></div>
        </div>

        <div id="review-panel" class="review-panel">
            <h3><i>📋 وثيقة الأهلية النهائية</i></h3>
            <div id="review-content"></div>
            <button id="edit-review-btn" class="edit-data-btn">✏️ تعديل البيانات</button>
        </div>

        <div class="nav-buttons">
            <button id="next-btn" class="btn-next" disabled>التالي</button>
            <button id="arise-btn" class="btn-arise">ARISE</button>
        </div>
    </div>
</div>
<div id="toastMsg" class="toast-msg"></div>

<script>
    (function() {
        const levelDescriptions = {
            "مبتدئ (Novice)": "🌱 المستوى المبتدئ: أساسيات البرمجة، فهم بسيط للأنظمة، يتطلب إشراف وتدريب في بيئة Arise.",
            "متوسط (Scholar)": "📘 المستوى المتوسط: يمتلك معرفة جيدة، قادر على تنفيذ مهام مستقلة، يشارك في مشاريع الفريق.",
            "محترف (Elite)": "⚡ المستوى المحترف: خبير في مجاله، يقود مشاريع، يساهم في تطوير البنية التحتية للنظام."
        };
        
        const sectorDescriptions = {
            "Security Center": "🛡️ مركز الأمن: حماية الأنظمة، اختبار الاختراق الأخلاقي، مراقبة الثغرات، تأمين البنية التحتية.",
            "Visual Arcane": "👁️ السحر البصري: تطوير واجهات المستخدم، تجربة المستخدم، تصميم الجرافيك، تفاعلات بصرية إبداعية.",
            "Logic Lab": "🧠 مختبر المنطق: خوارزميات، ذكاء اصطناعي، معالجة بيانات، بناء أنظمة ذكية وحل المشكلات المعقدة.",
            "Development Core": "📦 نواة التطوير: هندسة البرمجيات، تطوير الواجهات الخلفية والأمامية، بناء التطبيقات والخدمات.",
            "Strategy Room": "♟️ غرفة الاستراتيجية: تخطيط المشاريع، تحليل المخاطر، صنع القرار، إدارة الفرق والموارد."
        };
        
        const availableSectors = [
            "Security Center", "Visual Arcane", "Logic Lab", 
            "Development Core", "Strategy Room"
        ];
        
        let userData = { name: '', source: '', level: '', sector: '' };
        let currentStep = 1;
        let isReviewMode = false;
        
        const q1 = document.getElementById('q1');
        const q2 = document.getElementById('q2');
        const q3 = document.getElementById('q3');
        const q4 = document.getElementById('q4');
        const nextBtn = document.getElementById('next-btn');
        const ariseBtn = document.getElementById('arise-btn');
        const stepInfoSpan = document.getElementById('step-info-text');
        const stepCounterSpan = document.getElementById('step-counter');
        const progressFill = document.getElementById('progress-fill');
        const reviewPanel = document.getElementById('review-panel');
        const reviewContent = document.getElementById('review-content');
        const editReviewBtn = document.getElementById('edit-review-btn');
        const levelGroup = document.getElementById('level-group');
        const sectorGroup = document.getElementById('sector-group');
        
        function showToast(msg, isError = false) {
            const toast = document.getElementById('toastMsg');
            toast.style.backgroundColor = isError ? '#b00020' : '#4a148c';
            toast.innerText = msg;
            toast.style.opacity = '1';
            toast.style.transform = 'translateX(-50%) scale(1)';
            setTimeout(() => {
                toast.style.opacity = '0';
                toast.style.transform = 'translateX(-50%) scale(0.9)';
            }, 2500);
        }
        
        function updateProgressAndStep() {
            if (!isReviewMode) {
                let phaseText = '';
                if (currentStep === 1) phaseText = 'SYSTEM // PHASE_01 : الهوية';
                else if (currentStep === 2) phaseText = 'SYSTEM // PHASE_02 : المصدر';
                else if (currentStep === 3) phaseText = 'SYSTEM // PHASE_03 : الرتبة';
                else if (currentStep === 4) phaseText = 'SYSTEM // PHASE_04 : القطاع';
                stepInfoSpan.innerText = phaseText;
                stepCounterSpan.innerText = `${currentStep}/4`;
                const percent = ((currentStep - 1) / 3) * 100;
                progressFill.style.width = `${percent}%`;
            } else {
                stepInfoSpan.innerText = 'SYSTEM // READY FOR DEPLOY';
                stepCounterSpan.innerText = '✔️ تم';
                progressFill.style.width = '100%';
            }
        }
        
        function validateCurrentStep() {
            if (isReviewMode) {
                nextBtn.disabled = true;
                return;
            }
            if (currentStep === 1) nextBtn.disabled = userData.name.trim().length < 2;
            else if (currentStep === 2) nextBtn.disabled = userData.source.trim().length < 2;
            else if (currentStep === 3) nextBtn.disabled = !userData.level;
            else if (currentStep === 4) nextBtn.disabled = !userData.sector;
        }
        
        function showStep(step) {
            if (isReviewMode) return;
            q1.classList.remove('active');
            q2.classList.remove('active');
            q3.classList.remove('active');
            q4.classList.remove('active');
            if (step === 1) q1.classList.add('active');
            else if (step === 2) q2.classList.add('active');
            else if (step === 3) q3.classList.add('active');
            else if (step === 4) q4.classList.add('active');
            updateProgressAndStep();
            validateCurrentStep();
        }
        
        function buildLevelOptions() {
            const levels = ["مبتدئ (Novice)", "متوسط (Scholar)", "محترف (Elite)"];
            levelGroup.innerHTML = '';
            levels.forEach(level => {
                const wrapper = document.createElement('div');
                wrapper.className = 'option-wrapper';
                const optionDiv = document.createElement('div');
                optionDiv.className = 'option-item';
                optionDiv.setAttribute('data-level', level);
                const textSpan = document.createElement('span');
                textSpan.innerText = level;
                const infoBtn = document.createElement('span');
                infoBtn.className = 'info-trigger';
                infoBtn.innerHTML = 'ℹ️';
                infoBtn.title = 'شرح الرتبة';
                optionDiv.appendChild(textSpan);
                optionDiv.appendChild(infoBtn);
                const descPanel = document.createElement('div');
                descPanel.className = 'desc-panel';
                descPanel.innerHTML = `<div>${levelDescriptions[level] || 'لا يوجد وصف مفصل.'}</div>`;
                wrapper.appendChild(optionDiv);
                wrapper.appendChild(descPanel);
                levelGroup.appendChild(wrapper);
                
                optionDiv.addEventListener('click', (e) => {
                    if (e.target === infoBtn) return;
                    userData.level = level;
                    document.querySelectorAll('#level-group .option-item').forEach(opt => opt.classList.remove('selected'));
                    optionDiv.classList.add('selected');
                    validateCurrentStep();
                });
                infoBtn.addEventListener('click', (e) => {
                    e.stopPropagation();
                    document.querySelectorAll('#level-group .desc-panel').forEach(panel => {
                        if (panel !== descPanel) panel.classList.remove('open');
                    });
                    descPanel.classList.toggle('open');
                });
            });
        }
        
        function buildSectorOptions() {
            sectorGroup.innerHTML = '';
            availableSectors.forEach(sector => {
                const wrapper = document.createElement('div');
                wrapper.className = 'option-wrapper';
                const optionDiv = document.createElement('div');
                optionDiv.className = 'option-item';
                optionDiv.setAttribute('data-sector', sector);
                const textSpan = document.createElement('span');
                textSpan.innerText = sector;
                const infoBtn = document.createElement('span');
                infoBtn.className = 'info-trigger';
                infoBtn.innerHTML = 'ℹ️';
                infoBtn.title = 'شرح القطاع';
                optionDiv.appendChild(textSpan);
                optionDiv.appendChild(infoBtn);
                const descPanel = document.createElement('div');
                descPanel.className = 'desc-panel';
                descPanel.innerHTML = `<div>${sectorDescriptions[sector] || 'وصف القطاع غير متوفر حالياً.'}</div>`;
                wrapper.appendChild(optionDiv);
                wrapper.appendChild(descPanel);
                sectorGroup.appendChild(wrapper);
                
                optionDiv.addEventListener('click', (e) => {
                    if (e.target === infoBtn) return;
                    userData.sector = sector;
                    document.querySelectorAll('#sector-group .option-item').forEach(opt => opt.classList.remove('selected'));
                    optionDiv.classList.add('selected');
                    validateCurrentStep();
                });
                infoBtn.addEventListener('click', (e) => {
                    e.stopPropagation();
                    document.querySelectorAll('#sector-group .desc-panel').forEach(panel => {
                        if (panel !== descPanel) panel.classList.remove('open');
                    });
                    descPanel.classList.toggle('open');
                });
            });
        }
        
        function bindTextFields() {
            const nameField = document.getElementById('input-name');
            const sourceField = document.getElementById('input-source');
            nameField.addEventListener('input', (e) => {
                userData.name = e.target.value;
                validateCurrentStep();
            });
            sourceField.addEventListener('input', (e) => {
                userData.source = e.target.value;
                validateCurrentStep();
            });
        }
        
        function enterReviewMode() {
            isReviewMode = true;
            q1.classList.remove('active');
            q2.classList.remove('active');
            q3.classList.remove('active');
            q4.classList.remove('active');
            reviewPanel.style.display = 'block';
            nextBtn.style.display = 'none';
            ariseBtn.style.display = 'block';
            updateReviewContent();
            updateProgressAndStep();
        }
        
        function updateReviewContent() {
            reviewContent.innerHTML = `
                <div class="review-row"><span>📛 الاسم المستعار:</span><span>${escapeHtml(userData.name) || '—'}</span></div>
                <div class="review-row"><span>🔗 عميل الإحالة:</span><span>${escapeHtml(userData.source) || '—'}</span></div>
                <div class="review-row"><span>🏅 الرتبة البرمجية:</span><span>${escapeHtml(userData.level) || '—'}</span></div>
                <div class="review-row"><span>🎯 القطاع المستهدف:</span><span>${escapeHtml(userData.sector) || '—'}</span></div>
            `;
        }
        
        function escapeHtml(str) {
            if (!str) return '—';
            return str.replace(/[&<>]/g, function(m) {
                if (m === '&') return '&amp;';
                if (m === '<') return '&lt;';
                if (m === '>') return '&gt;';
                return m;
            });
        }
        
        function exitReviewMode() {
            isReviewMode = false;
            reviewPanel.style.display = 'none';
            nextBtn.style.display = 'block';
            ariseBtn.style.display = 'none';
            currentStep = 1;
            showStep(1);
            document.getElementById('input-name').value = userData.name;
            document.getElementById('input-source').value = userData.source;
            document.querySelectorAll('#level-group .option-item').forEach(opt => {
                if (opt.getAttribute('data-level') === userData.level) opt.classList.add('selected');
                else opt.classList.remove('selected');
            });
            document.querySelectorAll('#sector-group .option-item').forEach(opt => {
                if (opt.getAttribute('data-sector') === userData.sector) opt.classList.add('selected');
                else opt.classList.remove('selected');
            });
            validateCurrentStep();
        }
        
        function handleNext() {
            if (isReviewMode) return;
            if (currentStep === 1) {
                if (!userData.name.trim()) return;
                currentStep = 2;
                showStep(2);
            } else if (currentStep === 2) {
                if (!userData.source.trim()) return;
                currentStep = 3;
                showStep(3);
            } else if (currentStep === 3) {
                if (!userData.level) {
                    showToast("⚠️ يرجى اختيار الرتبة البرمجية", true);
                    return;
                }
                currentStep = 4;
                showStep(4);
            } else if (currentStep === 4) {
                if (!userData.sector) {
                    showToast("⚠️ يرجى اختيار القطاع المستهدف", true);
                    return;
                }
                enterReviewMode();
            }
        }
        
        async function sendToWhatsApp() {
            if (!userData.name || !userData.source || !userData.level || !userData.sector) {
                showToast("❌ البيانات غير مكتملة", true);
                return;
            }
            const message = `ـ وثـيـقـة الأهلية ╎ 𝐄𝐋𝐈𝐆𝐈𝐁𝐈𝐋𝐈𝐓𝐘📑\n` +
                            `• الـاسـم: [ ${userData.name} ]\n` +
                            `• الـمـستوي: [ ${userData.level} ]\n` +
                            `• الـقطاع: [ ${userData.sector} ]\n` +
                            `• الـمصدر: [ ${userData.source} ]\n` +
                            `━━━━━━━━━━\nArise.`;
            try {
                await navigator.clipboard.writeText(message);
                showToast("✅ تم نسخ الوثيقة تلقائياً! جارٍ التوجيه");
            } catch (err) {
                showToast("📋 تم التوجيه (تعذر النسخ)");
            }
            const waUrl = `https://chat.whatsapp.com/DC1XDyXPQHZ0CGkxX0X5Vu?text=${encodeURIComponent(message)}`;
            window.open(waUrl, '_blank');
        }
        
        function addEnterBehavior() {
            const inputs = [document.getElementById('input-name'), document.getElementById('input-source')];
            inputs.forEach(inp => {
                inp.addEventListener('keypress', (e) => {
                    if (e.key === 'Enter' && !nextBtn.disabled && !isReviewMode && (currentStep === 1 || currentStep === 2)) {
                        e.preventDefault();
                        handleNext();
                    }
                });
            });
        }
        
        function init() {
            buildLevelOptions();
            buildSectorOptions();
            bindTextFields();
            addEnterBehavior();
            nextBtn.addEventListener('click', handleNext);
            ariseBtn.addEventListener('click', sendToWhatsApp);
            editReviewBtn.addEventListener('click', exitReviewMode);
            validateCurrentStep();
            updateProgressAndStep();
            document.getElementById('input-name').value = userData.name;
            document.getElementById('input-source').value = userData.source;
        }
        
        init();
    })();
</script>
</body>
</html>
