<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>أكاديمية اللغة الإنجليزية للأطفال</title>
    <style>
        :root {
            --bg-color: #e0f7fa; /* لون افتراضي (الربيع) */
            --btn-color: #ff9800;
        }

        body {
            margin: 0;
            font-family: 'Cairo', sans-serif;
            background-color: var(--bg-color);
            transition: all 1s ease;
            overflow-x: hidden;
            text-align: center;
        }

        /* تأثير السحب المتحركة */
        .clouds {
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: url('https://www.transparenttextures.com');
            animation: moveClouds 60s linear infinite;
            z-index: -1;
            opacity: 0.5;
        }

        @keyframes moveClouds {
            from { background-position: 0 0; }
            to { background-position: 1000px 0; }
        }

        /* الأيقونات العائمة */
        .floating-container {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            padding: 50px;
        }

        .icon-btn {
            width: 150px;
            height: 150px;
            background: var(--btn-color);
            border-radius: 40% 60% 70% 30% / 40% 50% 60% 50%; /* شكل غير منتظم */
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
            transition: transform 0.3s;
            animation: float 3s ease-in-out infinite;
            color: white;
            font-weight: bold;
            text-decoration: none;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-20px) rotate(5deg); }
        }

        /* تأثيرات الفصول */
        .winter { background-color: #bbdefb !important; }
        .winter .icon-btn { animation: shiver 0.2s infinite; } /* ارتعاش */
        
        .summer { background-color: #fff9c4 !important; }
        
        @keyframes shiver {
            0% { transform: translate(1px, 1px) rotate(0deg); }
            50% { transform: translate(-1px, -1px) rotate(-1deg); }
        }

        .header { padding: 20px; background: white; box-shadow: 0 5px 15px rgba(0,0,0,0.1); }
    </style>
</head>
<body id="mainBody">

    <div class="clouds"></div>

    <div class="header">
        <h1>مرحباً بك في عالم الإنجليزية الممتع! 🌟</h1>
        <p>اختر فصلاً لتبدأ: 
            <button onclick="changeSeason('spring')">الربيع 🌸</button>
            <button onclick="changeSeason('winter')">الشتاء ❄️</button>
            <button onclick="changeSeason('summer')">الصيف ☀️</button>
            <button onclick="changeSeason('autumn')">الخريف 🍂</button>
        </p>
    </div>

    <div class="floating-container">
        <a href="#grammar" class="icon-btn">قواعد اللغة (بالعربي)</a>
        <a href="#vocab" class="icon-btn" style="background: #4caf50;">كلمات رابعة ابتدائي</a>
        <a href="#sentence" class="icon-btn" style="background: #2196f3;">تكوين الجمل</a>
        <a href="#letter" class="icon-btn" style="background: #e91e63;">كتابة الخطاب</a>
    </div>

    <script>
        function changeSeason(season) {
            const body = document.getElementById('mainBody');
            body.className = season;
            if(season === 'winter') alert("الجو بارد جداً! الأيقونات ترتعش ❄️");
            if(season === 'summer') alert("الشمس ساطعة! الأيقونات تشعر بالحر ☀️");
        }
    </script>
</body>
</html>
