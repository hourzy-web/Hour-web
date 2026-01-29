<!DOCTYPE html>
<html lang="km">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HOUR ZY - Glass Design</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=SF+Pro+Display:wght@300;400;500;600;700&family=Battambang:wght@400;700&family=Bayon&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', 'Battambang', 'Segoe UI', 'Helvetica Neue', sans-serif;
            background: linear-gradient(135deg, #0f2947 0%, #1a4d6d 25%, #3d7fa3 50%, #4a9db5 75%, #0f2947 100%);
            background-size: 400% 400%;
            background-attachment: fixed;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 40px 20px;
            position: relative;
            overflow-x: hidden;
        }

        /* Animated background elements */
        body::before {
            content: '';
            position: fixed;
            width: 600px;
            height: 600px;
            background: radial-gradient(circle, rgba(100, 200, 255, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            top: -200px;
            right: -200px;
            filter: blur(50px);
            animation: float 12s ease-in-out infinite;
            z-index: 0;
        }

        body::after {
            content: '';
            position: fixed;
            width: 500px;
            height: 500px;
            background: radial-gradient(circle, rgba(150, 100, 200, 0.08) 0%, transparent 70%);
            border-radius: 50%;
            bottom: -150px;
            left: -150px;
            filter: blur(50px);
            animation: float 15s ease-in-out infinite reverse;
            z-index: 0;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) translateX(0px); }
            50% { transform: translateY(40px) translateX(30px); }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .container {
            max-width: 700px;
            width: 100%;
            position: relative;
            z-index: 10;
        }

        .page {
            display: none;
            animation: fadeInUp 0.8s ease-out;
        }

        .page.active {
            display: block;
        }

        /* PAGE 1 STYLES */
        .header {
            text-align: center;
            margin-bottom: 80px;
            animation: fadeInUp 0.8s ease-out;
        }

        .welcome {
            font-size: 17px;
            color: rgba(255, 255, 255, 0.8);
            letter-spacing: 1.2px;
            margin-bottom: 15px;
            font-weight: 500;
            text-transform: uppercase;
        }

        .title {
            font-size: 64px;
            font-weight: 700;
            color: #ffffff;
            letter-spacing: -2px;
            text-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
            margin-bottom: 10px;
            line-height: 1.2;
            font-family: 'Bayon', 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        .subtitle {
            font-size: 20px;
            color: rgba(255, 255, 255, 0.85);
            font-weight: 400;
            letter-spacing: 0.5px;
            line-height: 1.8;
            font-family: 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        .cards-container {
            display: grid;
            gap: 24px;
            margin-bottom: 40px;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(40px);
            -webkit-backdrop-filter: blur(40px);
            border-radius: 28px;
            padding: 40px 35px;
            border: 1px solid rgba(255, 255, 255, 0.25);
            box-shadow: 
                0 8px 32px rgba(0, 0, 0, 0.15),
                inset 0 1px 0 rgba(255, 255, 255, 0.4),
                inset 0 -1px 0 rgba(0, 0, 0, 0.1);
            position: relative;
            overflow: hidden;
            animation: fadeInUp 0.8s ease-out;
            animation-fill-mode: both;
        }

        .glass-card::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(
                135deg,
                rgba(255, 255, 255, 0.1) 0%,
                transparent 60%
            );
            animation: shimmer 3s ease-in-out infinite;
            pointer-events: none;
        }

        @keyframes shimmer {
            0% { transform: translate(0, 0) rotate(0deg); }
            50% { transform: translate(20px, 20px) rotate(5deg); }
            100% { transform: translate(0, 0) rotate(0deg); }
        }

        .glass-card > * {
            position: relative;
            z-index: 2;
        }

        .card-icon {
            font-size: 48px;
            margin-bottom: 15px;
            display: inline-block;
            animation: bounce 2s ease-in-out infinite;
        }

        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        .card-title {
            font-size: 26px;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 12px;
            letter-spacing: -0.5px;
            line-height: 1.5;
            font-family: 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        .card-description {
            font-size: 16px;
            color: rgba(255, 255, 255, 0.8);
            line-height: 1.9;
            margin-bottom: 20px;
            font-weight: 400;
            letter-spacing: 0.2px;
            font-family: 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        .card-quote {
            font-style: italic;
            color: rgba(255, 255, 255, 0.75);
            line-height: 1.8;
            font-family: 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
            font-size: 15px;
            margin: 15px 0 0 0;
            padding-left: 15px;
            border-left: 3px solid rgba(255, 255, 255, 0.3);
        }

        .card-link {
            display: inline-block;
            padding: 12px 24px;
            background: rgba(255, 255, 255, 0.15);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 16px;
            color: #ffffff;
            text-decoration: none;
            font-size: 15px;
            font-weight: 600;
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            letter-spacing: 0.2px;
            margin-top: 15px;
            border: none;
        }

        .card-link:hover {
            background: rgba(255, 255, 255, 0.25);
            border: 1px solid rgba(255, 255, 255, 0.4);
            transform: translateY(-3px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .card-link:active {
            transform: translateY(-1px);
        }

        /* PAGE 2 STYLES */
        .header-page2 {
            display: flex;
            align-items: center;
            justify-content: space-between;
            margin-bottom: 40px;
            animation: fadeInUp 0.8s ease-out;
        }

        .back-btn {
            background: rgba(255, 255, 255, 0.12);
            backdrop-filter: blur(30px);
            -webkit-backdrop-filter: blur(30px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 16px;
            color: #ffffff;
            font-size: 18px;
            width: 45px;
            height: 45px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            text-decoration: none;
            border: none;
        }

        .back-btn:hover {
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.4);
            transform: translateX(-5px);
        }

        .page-title {
            font-size: 32px;
            font-weight: 700;
            color: #ffffff;
            letter-spacing: -0.8px;
            line-height: 1.4;
            font-family: 'Bayon', 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
            flex: 1;
            text-align: center;
        }

        .note-input {
            width: 100%;
            min-height: 200px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.08);
            border: 1px solid rgba(255, 255, 255, 0.25);
            border-radius: 16px;
            color: #ffffff;
            font-family: 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
            font-size: 16px;
            line-height: 1.8;
            resize: vertical;
            transition: all 0.4s ease;
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            margin-top: 20px;
            margin-bottom: 20px;
        }

        .note-input::placeholder {
            color: rgba(255, 255, 255, 0.5);
        }

        .note-input:focus {
            outline: none;
            background: rgba(255, 255, 255, 0.12);
            border: 1px solid rgba(255, 255, 255, 0.4);
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.1);
        }

        .button-container {
            display: grid;
            grid-template-columns: 1fr 1fr 1fr;
            gap: 12px;
            margin-bottom: 20px;
        }

        .action-btn {
            padding: 12px 16px;
            background: rgba(255, 255, 255, 0.12);
            backdrop-filter: blur(20px);
            -webkit-backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 12px;
            color: #ffffff;
            font-size: 14px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            font-family: 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        .action-btn:hover {
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.4);
            transform: translateY(-2px);
        }

        .action-btn:active {
            transform: translateY(0);
        }

        .save-btn:hover {
            box-shadow: 0 8px 20px rgba(76, 175, 80, 0.3);
        }

        .clear-btn:hover {
            box-shadow: 0 8px 20px rgba(255, 165, 0, 0.3);
        }

        .delete-btn:hover {
            box-shadow: 0 8px 20px rgba(255, 0, 0, 0.3);
        }

        .saved-notes {
            margin-top: 30px;
        }

        .note-item {
            background: rgba(255, 255, 255, 0.08);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 12px;
            padding: 15px;
            margin-bottom: 12px;
            color: rgba(255, 255, 255, 0.9);
            line-height: 1.8;
            font-family: 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
            font-size: 15px;
            animation: fadeInUp 0.4s ease-out;
        }

        .note-time {
            font-size: 12px;
            color: rgba(255, 255, 255, 0.5);
            margin-top: 8px;
            font-weight: 400;
        }

        .divider {
            height: 1px;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            margin: 30px 0;
        }

        .contact-section {
            background: rgba(255, 255, 255, 0.08);
            backdrop-filter: blur(40px);
            -webkit-backdrop-filter: blur(40px);
            border-radius: 28px;
            padding: 50px 40px;
            border: 1px solid rgba(255, 255, 255, 0.25);
            box-shadow: 
                0 8px 32px rgba(0, 0, 0, 0.15),
                inset 0 1px 0 rgba(255, 255, 255, 0.4);
            margin-bottom: 40px;
            animation: fadeInUp 0.8s ease-out 0.8s both;
        }

        .section-title {
            font-size: 32px;
            font-weight: 700;
            color: #ffffff;
            margin-bottom: 30px;
            text-align: center;
            letter-spacing: -0.8px;
            line-height: 1.4;
            font-family: 'Bayon', 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
        }

        .button-group {
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }

        .contact-btn {
            padding: 18px 30px;
            background: rgba(255, 255, 255, 0.12);
            backdrop-filter: blur(30px);
            -webkit-backdrop-filter: blur(30px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 18px;
            color: #ffffff;
            font-size: 17px;
            font-weight: 600;
            text-decoration: none;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            transition: all 0.4s cubic-bezier(0.34, 1.56, 0.64, 1);
            box-shadow: 
                0 4px 15px rgba(0, 0, 0, 0.1),
                inset 0 1px 0 rgba(255, 255, 255, 0.2);
            position: relative;
            overflow: hidden;
            letter-spacing: 0.3px;
        }

        .contact-btn:hover {
            background: rgba(255, 255, 255, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.4);
            transform: translateY(-4px);
            box-shadow: 
                0 12px 35px rgba(0, 0, 0, 0.2),
                inset 0 1px 0 rgba(255, 255, 255, 0.3);
        }

        .contact-btn:active {
            transform: translateY(-1px);
        }

        .btn-icon {
            font-size: 20px;
        }

        .footer-text {
            text-align: center;
            color: rgba(255, 255, 255, 0.65);
            font-size: 14px;
            letter-spacing: 0.3px;
            font-weight: 400;
            font-family: 'Battambang', -apple-system, BlinkMacSystemFont, sans-serif;
            line-height: 1.8;
        }

        @media (max-width: 768px) {
            .title {
                font-size: 42px;
            }

            .glass-card {
                padding: 30px 25px;
            }

            .button-container {
                grid-template-columns: 1fr;
            }

            .contact-btn {
                font-size: 15px;
            }
        }

        @media (max-width: 480px) {
            .title {
                font-size: 36px;
            }

            .glass-card {
                padding: 25px 20px;
                border-radius: 20px;
            }

            .note-input {
                min-height: 150px;
                font-size: 15px;
            }

            .action-btn {
                font-size: 13px;
            }

            .contact-btn {
                font-size: 14px;
                padding: 14px 20px;
            }
        }

        @media (prefers-reduced-motion: reduce) {
            * {
                animation: none !important;
                transition: none !important;
            }
        }
    </style>
</head>
<body>
    <!-- PAGE 1: HOME PAGE -->
    <div id="page1" class="page active">
        <div class="container">
            <div class="header">
                <div class="welcome">Welcome!</div>
                <h1 class="title">HOUR ZY!</h1>
                <p class="subtitle">ពិសេសអ្វីដែលយើងផ្តល់ជូនអ្នក</p>
            </div>

            <div class="cards-container">
                <div class="glass-card">
                    <div class="card-icon">📚</div>
                    <h2 class="card-title">Content Creation</h2>
                    <p class="card-description">តែងសេចក្ដី</p>
                    <p class="card-quote">ប្រធាន «សេរីភាព គឺជាបំណងប្រាថ្នារបស់មនុស្ស»</p>
                    <button class="card-link" onclick="goToPage2()">អាន</button>
                </div>
            </div>

            <div class="contact-section">
                <h2 class="section-title">ទំនាក់ទំនងយើងខ្ញុំ</h2>
                
                <div class="button-group">
                    <a href="https://t.me/Hour_zoa" target="_blank" class="contact-btn">
                        <span>Telegram</span>
                    </a>
                    <a href="https://youtube.com/@hour_zy" target="_blank" class="contact-btn">
                        <span>YouTube</span>
                    </a>
                    <a href="tel:+855972471969" class="contact-btn">
                        <span>Call</span>
                    </a>
                </div>

                <div class="divider"></div>

                <p class="footer-text">
                    ការឆ្លើយតប ២៤ម៉ោង អគុណសម្រាប់ការគាំទ្រ 🙏
                </p>
            </div>
        </div>
    </div>

    <!-- PAGE 2: NOTES PAGE -->
    <div id="page2" class="page">
        <div class="container">
            <div class="header-page2">
                <button class="back-btn" onclick="goToPage1()">←</button>
                <h1 class="page-title">Content Creation</h1>
                <div style="width: 45px;"></div>
            </div>

            <div class="glass-card">
                <div class="card-icon">📝</div>
                
                <h2 class="card-title">តែងសេចក្ដី</h2>
                
                <p class="card-quote" style="margin-top: 15px; margin-bottom: 30px;">
                    ប្រធាន «សេរីភាព គឺជាបំណងប្រាថ្នារបស់មនុស្ស»
                </p>

                <p class="card-description" style="margin-top: 20px;">
                    សូមស្វាគមន៍មក HOUR ZY ដែលជាកន្លែងដែលយើងបង្កើតលក្ខណៈ original content ដែលពិតប្រាកដ ប្រកបដោយការច្នៃប្រឌិត និងគុណភាពខ្ពស់។ យើងចូលចិត្តក្នុងការផ្ដល់ជូនលោកអ្នកនូវលក្ខណៈដែលមានន័យ និងចម្រើន។
                </p>

                <p class="card-description">
                    ខ្ញុំសូមបង្កើតលក្ខណៈទាក់ទងដូចឧទាហរណ៍មួយ ដែលក្នុងលោកខ្ញុំវា គឺបង្កើតលក្ខណៈដែលពិតប្រាកដ ប្រកបដោយការច្នៃប្រឌិត និងគុណភាព។ យើងគឺជាក្រុមដែលម្នាក់ក្នុងមួយក្នុងការបង្កើតលក្ខណៈដែលមានលក្ខណៈពិសេស និងសម្បូរក្នុង។
                </p>

                <div class="divider"></div>

                <p class="card-description">
                    យើងច្រើនលើក បាននិយាយថា សេរីភាព គឺជាចំណុចសំខាន់បំផុត។ ដូច្នេះ យើងនឹងតែងតែផ្តល់ឱ្យលោកអ្នកនូវលក្ខណៈដែលមានលក្ខណៈសម្បូរក្នុង ហើយឱ្យលោកអ្នកមានសេរីភាពក្នុងការកំណត់មតិលើលក្ខណៈរបស់យើង។
                </p>
            </div>
        </div>
    </div>

    <script>
        // Page Navigation
        function goToPage1() {
            document.getElementById('page1').classList.add('active');
            document.getElementById('page2').classList.remove('active');
        }

        function goToPage2() {
            document.getElementById('page1').classList.remove('active');
            document.getElementById('page2').classList.add('active');
        }
    </script>
</body>
</html>
