<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Весёлая кибербезопасность</title>
    <style>
        :root {
            --primary: #6c5ce7;
            --secondary: #00cec9;
            --danger: #ff7675;
            --success: #55efc4;
            --dark: #2d3436;
            --light: #f5f6fa;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Comic Sans MS', cursive, sans-serif;
        }
        
        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            padding: 1rem 0;
            text-align: center;
            border-bottom: 5px dotted var(--success);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        
        nav {
            margin-top: 1rem;
            width: 100%;
        }
        
        .nav-menu {
            display: flex;
            justify-content: center;
            list-style: none;
            flex-wrap: wrap;
            gap: 1rem;
            padding: 0.5rem 0;
        }
        
        .nav-menu li a {
            color: white;
            text-decoration: none;
            font-weight: bold;
            padding: 0.5rem 1rem;
            border-radius: 50px;
            transition: all 0.3s;
        }
        
        .nav-menu li a:hover {
            background: rgba(255, 255, 255, 0.2);
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            text-shadow: 3px 3px 0 rgba(0,0,0,0.1);
        }
        
        h2 {
            color: var(--primary);
            margin: 2rem 0 1rem;
            font-size: 2rem;
        }
        
        h3 {
            color: var(--primary);
            margin-bottom: 1rem;
        }
        
        .subtitle {
            font-size: 1.5rem;
            opacity: 0.9;
        }
        
        .hero-img {
            max-width: 300px;
            margin: 2rem auto;
            display: block;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-20px); }
        }
        
        section {
            padding: 3rem 0;
            border-bottom: 2px dashed var(--secondary);
        }
        
        .card {
            background: white;
            border-radius: 15px;
            padding: 2rem;
            margin: 1rem 0;
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        
        .card:hover {
            transform: translateY(-10px);
        }
        
        .tips-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 20px;
            margin-top: 2rem;
        }
        
        .tip-card {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            border-top: 5px solid var(--primary);
        }
        
        .games-container {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            justify-content: center;
            margin-top: 2rem;
        }
        
        .game-card {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            width: 300px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            cursor: pointer;
            transition: all 0.3s;
        }
        
        .game-card:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }
        
        .game-card img {
            width: 100px;
            height: 100px;
            margin-bottom: 1rem;
        }
        
        .btn {
            display: inline-block;
            background: var(--primary);
            color: white;
            padding: 12px 24px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: bold;
            margin-top: 1rem;
            transition: all 0.3s;
            border: none;
            cursor: pointer;
        }
        
        .btn:hover {
            background: var(--secondary);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
            z-index: 1000;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background: white;
            padding: 2rem;
            border-radius: 15px;
            max-width: 600px;
            width: 90%;
            max-height: 80vh;
            overflow-y: auto;
            position: relative;
        }
        
        .close-modal {
            position: absolute;
            top: 15px;
            right: 15px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--danger);
        }
        
        .password-meter {
            height: 10px;
            background: #eee;
            border-radius: 5px;
            margin-top: 10px;
            overflow: hidden;
        }
        
        .meter-bar {
            height: 100%;
            width: 0;
            background: var(--danger);
            transition: all 0.3s;
        }
        
        .game-area {
            margin: 1rem 0;
            padding: 1rem;
            background: #f5f6fa;
            border-radius: 10px;
        }
        
        .game-task {
            margin-bottom: 1rem;
            font-weight: bold;
        }
        
        .game-options {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        
        .game-option {
            padding: 10px;
            background: white;
            border-radius: 5px;
            cursor: pointer;
            transition: all 0.2s;
        }
        
        .game-option:hover {
            background: #e0f2f1;
        }
        
        .correct {
            background: #a5d6a7 !important;
        }
        
        .incorrect {
            background: #ef9a9a !important;
        }
        
        footer {
            background: var(--dark);
            color: white;
            text-align: center;
            padding: 2rem 0;
            margin-top: 2rem;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 2rem;
        }
        
        .stat-card {
            background: white;
            border-radius: 15px;
            padding: 1.5rem;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .stat-card h3 {
            color: var(--secondary);
            margin-bottom: 0.5rem;
        }
        
        .stat-card p:first-of-type {
            font-size: 1.8rem;
            font-weight: bold;
            color: var(--primary);
            margin-bottom: 0.5rem;
        }
        
        .stat-card p:last-of-type {
            font-size: 0.9rem;
            color: var(--dark);
        }
        
        .term-link {
            color: var(--primary);
            text-decoration: underline;
            cursor: pointer;
            font-weight: bold;
        }
        
        .term-link:hover {
            color: var(--secondary);
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            .subtitle {
                font-size: 1.2rem;
            }
            
            .nav-menu {
                flex-direction: column;
                align-items: center;
                gap: 0.5rem;
            }
            
            .stat-card p:first-of-type {
                font-size: 1.5rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <h1>Весёлая кибербезопасность</h1>
            <p class="subtitle">Учимся защищаться в интернете с улыбкой!</p>
            
            <nav>
                <ul class="nav-menu">
                    <li><a href="#about">О проекте</a></li>
                    <li><a href="#tips">Советы</a></li>
                    <li><a href="#games">Игры</a></li>
                    <li><a href="#stats">Статистика</a></li>
                    <li><a href="#quiz">Тест</a></li>
                    <li><a href="#contacts">Контакты</a></li>
                </ul>
            </nav>
        </div>
    </header>
    
    <section id="about">
        <div class="container">
            <div class="card">
                <h2>Почему это важно?</h2>
                <p>Каждый день мы сталкиваемся с киберугрозами: вирусы, хакеры, мошенники. Но защита может быть интересной! На нашем сайте вы узнаете:</p>
                <ul style="margin-top: 1rem; padding-left: 2rem;">
                    <li>Как создать надёжный пароль, который не взломать</li>
                    <li>Как защитить компьютер от вирусов</li>
                    <li>Как распознать фейки и мошенников в интернете</li>
                    <li>И многое другое в игровой форме!</li>
                </ul>
                
                <h3 style="margin-top: 2rem;">Кому будет полезен этот сайт?</h3>
                <p>Наш ресурс создан для всех, кто пользуется интернетом: от школьников до пенсионеров. Особенно полезен он будет:</p>
                <ul style="margin-top: 1rem; padding-left: 2rem;">
                    <li>Детям и подросткам, которые активно общаются в соцсетях</li>
                    <li>Родителям, которые хотят защитить своих детей в сети</li>
                    <li>Пенсионерам, осваивающим цифровые технологии</li>
                    <li>Всем, кто хочет безопасно пользоваться онлайн-банкингом</li>
                </ul>
            </div>
        </div>
    </section>
    
    <section id="stats">
        <div class="container">
            <h2>Цифры говорят сами за себя</h2>
            <p>Статистика киберпреступлений показывает, насколько важна безопасность в интернете</p>
            
            <div class="stats-grid">
                <div class="stat-card">
                    <h3>Атак в день</h3>
                    <p>30,000+</p>
                    <p>Ежедневно хакеры атакуют сайты по всему миру</p>
                </div>
                
                <div class="stat-card">
                    <h3>Украдено за 3 года</h3>
                    <p>350+ млрд ₽</p>
                    <p>Общий ущерб от киберпреступлений</p>
                </div>
                
                <div class="stat-card">
                    <h3>Фишинговых сайтов</h3>
                    <p>1.5 млн</p>
                    <p>Обнаружено и заблокировано за последний год</p>
                </div>
                
                <div class="stat-card">
                    <h3>Слабых паролей</h3>
                    <p>23%</p>
                    <p>Пользователей используют "123456" или "password"</p>
                </div>
            </div>
        </div>
    </section>
    
    <section id="tips">
        <div class="container">
            <h2>Полезные советы</h2>
            <p>Основы кибербезопасности в простых правилах</p>
            
            <div class="tips-grid">
                <div class="tip-card">
                    <h3>Надёжные пароли</h3>
                    <p>Используйте длинные пароли (12+ символов) с буквами, цифрами и <span class="term-link" onclick="openTermModal('special-chars')">спецсимволами</span>. Не используйте личную информацию!</p>
                    <button class="btn" onclick="openPasswordGenerator()">Генератор паролей</button>
                </div>
                
                <div class="tip-card">
                    <h3>Защита от вирусов</h3>
                    <p>Установите антивирус, не открывайте подозрительные файлы, обновляйте программы. Будьте осторожны с USB-флешками!</p>
                </div>
                
                <div class="tip-card">
                    <h3>Распознавание фейков</h3>
                    <p>Проверяйте <span class="term-link" onclick="openTermModal('url')">URL сайтов</span>, ищите контакты, читайте отзывы. Если предложение слишком хорошее - скорее всего, это обман!</p>
                </div>
                
                <div class="tip-card">
                    <h3>Безопасный Wi-Fi</h3>
                    <p>Не используйте публичные Wi-Fi сети для банковских операций. Если необходимо - используйте VPN.</p>
                </div>
                
                <div class="tip-card">
                    <h3>Двухфакторная аутентификация</h3>
                    <p>Включайте <span class="term-link" onclick="openTermModal('2fa')">2FA</span> везде, где возможно. Это добавит дополнительный уровень защиты вашим аккаунтам.</p>
                </div>
                
                <div class="tip-card">
                    <h3>Осторожно с письмами</h3>
                    <p>Не переходите по ссылкам в подозрительных письмах, даже если они якобы от банка или знакомых.</p>
                </div>
            </div>
        </div>
    </section>
    
    <section id="games">
        <div class="container">
            <h2>Игровые тесты и симуляции</h2>
            <p>Проверьте свои знания в увлекательных играх!</p>
            
            <div class="games-container">
                <div class="game-card" onclick="openGame('hacker')">
                    <img src="img/1.png" alt="Поймай хакера">
                    <h3>Поймай хакера</h3>
                    <p>Найдите подозрительные действия в <span class="term-link" onclick="openTermModal('logs')">логах</span> и остановите злоумышленника!</p>
                    <button class="btn">Играть</button>
                </div>
                
                <div class="game-card" onclick="openGame('virus')">
                    <img src="img/2.png" alt="Спаси компьютер">
                    <h3>Спаси компьютер от вируса</h3>
                    <p>Очистите систему от вредоносных программ и защитите данные!</p>
                    <button class="btn">Играть</button>
                </div>
                
                <div class="game-card" onclick="openGame('phishing')">
                    <img src="img/3.png" alt="Найди фейк">
                    <h3>Найди фейк</h3>
                    <p>Определите признаки <span class="term-link" onclick="openTermModal('phishing')">фишинга</span> в сайтах и письмах!</p>
                    <button class="btn">Играть</button>
                </div>
            </div>
        </div>
    </section>
    
    <section id="quiz">
        <div class="container">
            <div class="card">
                <h2>Быстрая проверка знаний</h2>
                <p>Ответьте на несколько вопросов, чтобы оценить свою киберграмотность</p>
                
                <div id="quiz-container" style="margin-top: 2rem;">
                    <div id="quiz-question" style="margin-bottom: 1rem; font-weight: bold;"></div>
                    <div id="quiz-options" style="display: flex; flex-direction: column; gap: 10px;"></div>
                    <button id="quiz-next" class="btn" style="margin-top: 1rem; display: none;">Следующий вопрос</button>
                    <div id="quiz-result" style="margin-top: 1rem; font-weight: bold; display: none;"></div>
                </div>
                
                <button id="start-quiz" class="btn" style="margin-top: 1rem;">Начать тест</button>
            </div>
        </div>
    </section>
    
    <section id="contacts">
        <div class="container">
            <div class="card">
                <h2>Остались вопросы?</h2>
                <p>Свяжитесь с нами, и мы поможем разобраться в вопросах кибербезопасности</p>
                
                <div style="margin-top: 2rem; display: flex; flex-wrap: wrap; gap: 2rem;">
                    <div style="flex: 1; min-width: 250px;">
                        <h3>Контакты</h3>
                        <p><strong>Email:</strong> dariastrashnikova@yandex.ru</p>
                        <p><strong>Телефон:</strong> +7 (926) 483-45-08</p>
                        <p><strong>Адрес:</strong> г. Москва, ул. Кибербезопасности, 1</p>
                    </div>
                    
                    <div style="flex: 1; min-width: 250px;">
                        <h3>Подписаться на новости</h3>
                        <form style="margin-top: 1rem;">
                            <input type="text" placeholder="Ваше имя" style="width: 100%; padding: 10px; margin-bottom: 10px; border-radius: 5px; border: 1px solid #ddd;">
                            <input type="email" placeholder="Ваш email" style="width: 100%; padding: 10px; margin-bottom: 10px; border-radius: 5px; border: 1px solid #ddd;">
                            <button type="submit" class="btn">Подписаться</button>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <footer>
        <div class="container">
            <p>© 2025 Весёлая кибербезопасность</p>
            <p>Учимся защищаться с удовольствием!</p>
            <div style="margin-top: 1rem;">
                <a href="#contacts" style="color: var(--secondary); margin: 0 10px;">Контакты</a>
                <a href="#" style="color: var(--secondary); margin: 0 10px;"></a>
                <a href="#" style="color: var(--secondary); margin: 0 10px;"></a>
            </div>
        </div>
    </footer>
    
    <!-- Модальные окна -->
    <div id="password-modal" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('password-modal')">&times;</span>
            <h2>Генератор надёжных паролей</h2>
            <div style="margin: 1rem 0;">
                <label for="password-length">Длина пароля (8-20 символов):</label>
                <input type="range" id="password-length" min="8" max="20" value="12" style="width: 100%;">
                <div style="display: flex; justify-content: space-between; margin-top: 5px;">
                    <span>8</span>
                    <span id="length-value">12</span>
                    <span>20</span>
                </div>
            </div>
            
            <div style="margin: 1rem 0;">
                <label><input type="checkbox" id="use-uppercase" checked> Заглавные буквы (A-Z)</label><br>
                <label><input type="checkbox" id="use-lowercase" checked> Строчные буквы (a-z)</label><br>
                <label><input type="checkbox" id="use-numbers" checked> Цифры (0-9)</label><br>
                <label><input type="checkbox" id="use-symbols" checked> Спецсимволы (!@#$%^&*)</label>
            </div>
            
            <button class="btn" onclick="generatePassword()">Сгенерировать пароль</button>
            
            <div style="margin: 1rem 0;">
                <input type="text" id="generated-password" style="width: 100%; padding: 10px; border: 2px solid var(--primary); border-radius: 5px; font-size: 1.2rem;" readonly>
                <div class="password-meter">
                    <div id="meter-bar" class="meter-bar"></div>
                </div>
                <p id="password-strength" style="margin-top: 5px; font-size: 0.9rem;"></p>
            </div>
            
            <div style="margin-top: 1rem; padding: 1rem; background: #f0f0f0; border-radius: 5px;">
                <h3>Советы по паролям:</h3>
                <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                    <li>Не используйте один пароль для всех аккаунтов</li>
                    <li>Меняйте пароли каждые 3-6 месяцев</li>
                    <li>Не записывайте пароли в открытом виде</li>
                    <li>Используйте менеджер паролей для хранения</li>
                </ul>
            </div>
        </div>
    </div>
    
    <div id="game-modal" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('game-modal')">&times;</span>
            <h2 id="game-title">Игра</h2>
            <div id="game-content" style="margin: 1rem 0;">
                <!-- Контент игры будет загружаться здесь -->
            </div>
        </div>
    </div>
    
    <!-- Модальные окна для терминов -->
    <div id="term-modal" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="closeModal('term-modal')">&times;</span>
            <h2 id="term-title">Термин</h2>
            <div id="term-content" style="margin: 1rem 0;">
                <!-- Контент термина будет загружаться здесь -->
            </div>
        </div>
    </div>
    
    <script>
        // Генератор паролей
        function openPasswordGenerator() {
            document.getElementById('password-modal').style.display = 'flex';
        }
        
        function closeModal(modalId) {
            document.getElementById(modalId).style.display = 'none';
        }
        
        document.getElementById('password-length').addEventListener('input', function() {
            document.getElementById('length-value').textContent = this.value;
        });
        
        function generatePassword() {
            const length = parseInt(document.getElementById('password-length').value);
            const useUppercase = document.getElementById('use-uppercase').checked;
            const useLowercase = document.getElementById('use-lowercase').checked;
            const useNumbers = document.getElementById('use-numbers').checked;
            const useSymbols = document.getElementById('use-symbols').checked;
            
            let charset = '';
            if (useUppercase) charset += 'ABCDEFGHIJKLMNOPQRSTUVWXYZ';
            if (useLowercase) charset += 'abcdefghijklmnopqrstuvwxyz';
            if (useNumbers) charset += '0123456789';
            if (useSymbols) charset += '!@#$%^&*()_+-=[]{}|;:,.<>?';
            
            if (charset === '') {
                alert('Выберите хотя бы один набор символов!');
                return;
            }
            
            let password = '';
            for (let i = 0; i < length; i++) {
                const randomIndex = Math.floor(Math.random() * charset.length);
                password += charset[randomIndex];
            }
            
            document.getElementById('generated-password').value = password;
            checkPasswordStrength(password);
        }
        
        function checkPasswordStrength(password) {
            let strength = 0;
            const length = password.length;
            
            // Проверка длины
            if (length >= 8) strength += 1;
            if (length >= 12) strength += 1;
            if (length >= 16) strength += 1;
            
            // Проверка на наличие разных типов символов
            if (/[a-z]/.test(password)) strength += 1;
            if (/[A-Z]/.test(password)) strength += 1;
            if (/[0-9]/.test(password)) strength += 1;
            if (/[^a-zA-Z0-9]/.test(password)) strength += 2;
            
            // Проверка на повторяющиеся символы
            if (!/(.)\1{2,}/.test(password)) strength += 1;
            
            // Оценка сложности
            let strengthText, strengthPercent, barColor;
            if (strength < 4) {
                strengthText = "Слабый";
                strengthPercent = 33;
                barColor = "#ff7675";
            } else if (strength < 7) {
                strengthText = "Средний";
                strengthPercent = 66;
                barColor = "#fdcb6e";
            } else {
                strengthText = "Сильный";
                strengthPercent = 100;
                barColor = "#00b894";
            }
            
            document.getElementById('meter-bar').style.width = strengthPercent + '%';
            document.getElementById('meter-bar').style.background = barColor;
            document.getElementById('password-strength').textContent = "Надёжность: " + strengthText;
            document.getElementById('password-strength').style.color = barColor;
        }
        
        // Модальные окна для терминов
        function openTermModal(term) {
            const modal = document.getElementById('term-modal');
            const title = document.getElementById('term-title');
            const content = document.getElementById('term-content');
            
            switch(term) {
                case 'special-chars':
                    title.textContent = "Спецсимволы";
                    content.innerHTML = `
                        <p><strong>Спецсимволы</strong> - это символы, не являющиеся буквами или цифрами, которые используются для усиления сложности паролей.</p>
                        <p>Примеры спецсимволов: <code>! @ # $ % ^ & * ( ) _ + - =</code></p>
                        <p>Использование спецсимволов в паролях делает их более устойчивыми к взлому методом перебора (брутфорс).</p>
                        <div style="margin-top: 1rem; padding: 1rem; background: #f0f0f0; border-radius: 5px;">
                            <h3>Советы:</h3>
                            <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                                <li>Используйте хотя бы 2-3 спецсимвола в пароле</li>
                                <li>Не заменяйте буквы на похожие спецсимволы (например, "a" на "@") - это предсказуемо</li>
                                <li>Комбинируйте разные типы спецсимволов</li>
                            </ul>
                        </div>
                    `;
                    break;
                    
                case 'url':
                    title.textContent = "URL сайта";
                    content.innerHTML = `
                        <p><strong>URL (Uniform Resource Locator)</strong> - это адрес веб-страницы в интернете.</p>
                        <p>Пример URL: <code>https://www.example.com/path?query=123</code></p>
                        <p>При проверке URL обращайте внимание на:</p>
                        <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                            <li><strong>Домен</strong> (example.com) - должен соответствовать официальному сайту</li>
                            <li><strong>Протокол</strong> (https://) - защищенное соединение</li>
                            <li><strong>Орфографические ошибки</strong> - мошенники часто используют похожие домены (examp1e.com)</li>
                        </ul>
                        <div style="margin-top: 1rem; padding: 1rem; background: #f0f0f0; border-radius: 5px;">
                            <h3>Как проверить URL:</h3>
                            <ol style="margin-top: 0.5rem; padding-left: 1.5rem;">
                                <li>Наведите курсор на ссылку (не кликайте!), чтобы увидеть настоящий URL</li>
                                <li>Проверьте домен на соответствие официальному сайту</li>
                                <li>Ищите HTTPS в начале адреса</li>
                                <li>Остерегайтесь длинных и сложных URL с множеством поддоменов</li>
                            </ol>
                        </div>
                    `;
                    break;
                    
                case '2fa':
                    title.textContent = "Двухфакторная аутентификация (2FA)";
                    content.innerHTML = `
                        <p><strong>2FA (Two-Factor Authentication)</strong> - это метод защиты аккаунта, требующий два разных способа подтверждения личности.</p>
                        <p>Обычно это комбинация:</p>
                        <ol style="margin-top: 0.5rem; padding-left: 1.5rem;">
                            <li>Что-то, что вы знаете (пароль)</li>
                            <li>Что-то, что у вас есть (код из SMS или приложения)</li>
                        </ol>
                        <p>Примеры 2FA:</p>
                        <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                            <li>Код из SMS</li>
                            <li>Приложение Google Authenticator</li>
                            <li>Аппаратные токены (YubiKey)</li>
                            <li>Биометрия (отпечаток пальца, Face ID)</li>
                        </ul>
                        <div style="margin-top: 1rem; padding: 1rem; background: #f0f0f0; border-radius: 5px;">
                            <h3>Почему это важно?</h3>
                            <p>Даже если злоумышленник узнает ваш пароль, без второго фактора он не сможет войти в аккаунт.</p>
                            <p>2FA снижает риск взлома на 99%!</p>
                        </div>
                    `;
                    break;
                    
                case 'logs':
                    title.textContent = "Логи (журналы событий)";
                    content.innerHTML = `
                        <p><strong>Логи</strong> - это записи о событиях, происходящих в системе, приложении или сети.</p>
                        <p>Пример записи в логе:</p>
                        <div style="background: #f8f8f8; padding: 10px; border-radius: 5px; font-family: monospace;">
                            <p>192.168.1.1 - GET /home</p>
                            <p>192.168.1.2 - GET /about</p>
                            <p>45.33.12.184 - GET /admin</p>
                            <p>192.168.1.3 - GET /contact</p>
                        </div>
                        <p style="margin-top: 1rem;">Логи помогают:</p>
                        <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                            <li>Отслеживать активность пользователей</li>
                            <li>Выявлять подозрительные действия</li>
                            <li>Расследовать инциденты безопасности</li>
                            <li>Находить ошибки в работе системы</li>
                        </ul>
                        <div style="margin-top: 1rem; padding: 1rem; background: #f0f0f0; border-radius: 5px;">
                            <h3>Что искать в логах?</h3>
                            <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                                <li>Необычные IP-адреса</li>
                                <li>Множественные попытки входа</li>
                                <li>Доступ к защищенным разделам</li>
                                <li>Необычное время активности</li>
                            </ul>
                        </div>
                    `;
                    break;
                    
                case 'phishing':
                    title.textContent = "Фишинг";
                    content.innerHTML = `
                        <p><strong>Фишинг</strong> - это вид интернет-мошенничества, целью которого является получение конфиденциальных данных (логинов, паролей, банковских реквизитов).</p>
                        <p>Фишинг обычно осуществляется через:</p>
                        <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                            <li>Поддельные письма (якобы от банков, соцсетей, сервисов)</li>
                            <li>Фейковые сайты, имитирующие официальные</li>
                            <li>Сообщения в мессенджерах и соцсетях</li>
                        </ul>
                        <div style="margin-top: 1rem; padding: 1rem; background: #f0f0f0; border-radius: 5px;">
                            <h3>Как распознать фишинг:</h3>
                            <ul style="margin-top: 0.5rem; padding-left: 1.5rem;">
                                <li>Проверяйте URL сайта перед вводом данных</li>
                                <li>Обращайте внимание на орфографические ошибки</li>
                                <li>Не переходите по подозрительным ссылкам в письмах</li>
                                <li>Официальные организации никогда не просят данные по email/SMS</li>
                                <li>Если предложение слишком хорошее - скорее всего, это обман</li>
                            </ul>
                        </div>
                        <div style="margin-top: 1rem; padding: 1rem; background: #ffebee; border-radius: 5px;">
                            <h3>Пример фишингового письма:</h3>
                            <p>"Уважаемый клиент! Ваш аккаунт будет заблокирован. Срочно перейдите по ссылке и введите свои данные для подтверждения."</p>
                            <p>Такие письма всегда должны вызывать подозрения!</p>
                        </div>
                    `;
                    break;
            }
            
            modal.style.display = 'flex';
        }
        
        // Игры
        function openGame(gameType) {
            const modal = document.getElementById('game-modal');
            const title = document.getElementById('game-title');
            const content = document.getElementById('game-content');
            
            switch(gameType) {
                case 'hacker':
                    title.textContent = "Поймай хакера";
                    content.innerHTML = `
                        <div style="text-align: center;">
                            <img src="img/1.png" alt="Хакер" width="100">
                            <h3 style="margin: 1rem 0;">Найдите подозрительную активность в сети!</h3>
                            <p>В этой игре вам нужно будет анализировать <span class="term-link" onclick="openTermModal('logs')">логи</span> сетевой активности и находить аномалии, которые указывают на действия хакера.</p>
                            
                            <div class="game-area">
                                <div class="game-task">Задание 1: В логах ниже найдите подозрительный IP-адрес</div>
                                <div style="text-align: left; background: white; padding: 1rem; border-radius: 5px; font-family: monospace; margin: 1rem 0;">
                                    <p>192.168.1.1 - GET /home</p>
                                    <p>192.168.1.2 - GET /about</p>
                                    <p>45.33.12.184 - GET /admin</p>
                                    <p>192.168.1.3 - GET /contact</p>
                                </div>
                                <div class="game-options">
                                    <div class="game-option" onclick="checkGameAnswer(this, 'hacker1', '192.168.1.1')">192.168.1.1</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'hacker1', '192.168.1.2')">192.168.1.2</div>
                                    <div class="game-option correct-answer" onclick="checkGameAnswer(this, 'hacker1', '45.33.12.184')">45.33.12.184</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'hacker1', '192.168.1.3')">192.168.1.3</div>
                                </div>
                            </div>
                            
                            <div class="game-area">
                                <div class="game-task">Задание 2: Какое из этих действий выглядит подозрительно?</div>
                                <div class="game-options">
                                    <div class="game-option" onclick="checkGameAnswer(this, 'hacker2', 'Просмотр главной страницы')">Просмотр главной страницы</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'hacker2', 'Скачивание файла robots.txt')">Скачивание файла robots.txt</div>
                                    <div class="game-option correct-answer" onclick="checkGameAnswer(this, 'hacker2', 'Множественные попытки входа в админку')">Множественные попытки входа в админку</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'hacker2', 'Чтение новостей')">Чтение новостей</div>
                                </div>
                            </div>
                            
                            <p style="margin-top: 1rem;">Игра поможет вам развить навыки анализа сетевой активности и обнаружения вторжений.</p>
                        </div>
                    `;
                    break;
                    
                case 'virus':
                    title.textContent = "Спаси компьютер от вируса";
                    content.innerHTML = `
                        <div style="text-align: center;">
                            <img src="img/2.png" alt="Вирус" width="100">
                            <h3 style="margin: 1rem 0;">Очистите систему от вредоносных программ!</h3>
                            <p>В этой игре вам предстоит найти и удалить вирусы из компьютерной системы.</p>
                            
                            <div class="game-area">
                                <div class="game-task">Задание 1: Какое из этих действий НЕ поможет защититься от вирусов?</div>
                                <div class="game-options">
                                    <div class="game-option" onclick="checkGameAnswer(this, 'virus1', 'Установить антивирус')">Установить антивирус</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'virus1', 'Обновлять программы')">Обновлять программы</div>
                                    <div class="game-option correct-answer" onclick="checkGameAnswer(this, 'virus1', 'Открывать вложения из неизвестных писем')">Открывать вложения из неизвестных писем</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'virus1', 'Не загружать пиратский софт')">Не загружать пиратский софт</div>
                                </div>
                            </div>
                            
                            <div class="game-area">
                                <div class="game-task">Задание 2: Ваш компьютер заражен. Что делать в первую очередь?</div>
                                <div class="game-options">
                                    <div class="game-option" onclick="checkGameAnswer(this, 'virus2', 'Продолжать работу как обычно')">Продолжать работу как обычно</div>
                                    <div class="game-option correct-answer" onclick="checkGameAnswer(this, 'virus2', 'Отключить интернет и запустить антивирус')">Отключить интернет и запустить антивирус</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'virus2', 'Перезагрузить компьютер')">Перезагрузить компьютер</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'virus2', 'Удалить все программы')">Удалить все программы</div>
                                </div>
                            </div>
                            
                            <p style="margin-top: 1rem;">Игра научит вас основным принципам защиты от вредоносных программ.</p>
                        </div>
                    `;
                    break;
                    
                case 'phishing':
                    title.textContent = "Найди фейк";
                    content.innerHTML = `
                        <div style="text-align: center;">
                            <img src="img/3.png" alt="Фишинг" width="100">
                            <h3 style="margin: 1rem 0;">Определите признаки <span class="term-link" onclick="openTermModal('phishing')">фишинга</span>!</h3>
                            <p>В этой игре вам нужно будет анализировать сайты и письма на признаки мошенничества.</p>
                            
                            <div class="game-area">
                                <div class="game-task">Задание 1: Какое из этих писем скорее всего фишинговое?</div>
                                <div class="game-options">
                                    <div class="game-option" onclick="checkGameAnswer(this, 'phish1', 'Ваш заказ #12345 был отправлен (от support@realstore.com)')">"Ваш заказ #12345 был отправлен" (от support@realstore.com)</div>
                                    <div class="game-option correct-answer" onclick="checkGameAnswer(this, 'phish1', 'Срочно! Ваш банковский аккаунт заблокирован! (от no-reply@bank-security.ru)')">"Срочно! Ваш банковский аккаунт заблокирован!" (от no-reply@bank-security.ru)</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'phish1', 'Подтвердите ваш email (от hello@trusted-service.com)')">"Подтвердите ваш email" (от hello@trusted-service.com)</div>
                                </div>
                            </div>
                            
                            <div class="game-area">
                                <div class="game-task">Задание 2: Какой из этих URL выглядит подозрительно?</div>
                                <div class="game-options">
                                    <div class="game-option" onclick="checkGameAnswer(this, 'phish2', 'http://www.sberbank.ru')">http://www.sberbank.ru</div>
                                    <div class="game-option correct-answer" onclick="checkGameAnswer(this, 'phish2', 'https://sberbank.security-update.com')">https://sberbank.security-update.com</div>
                                    <div class="game-option" onclick="checkGameAnswer(this, 'phish2', 'https://www.sberbank.ru/support')">https://www.sberbank.ru/support</div>
                                </div>
                            </div>
                            
                            <p style="margin-top: 1rem;">Игра поможет вам научиться распознавать мошеннические сайты и письма.</p>
                        </div>
                    `;
                    break;
            }
            
            modal.style.display = 'flex';
        }
        
        function checkGameAnswer(element, questionId, answer) {
            const correct = element.classList.contains('correct-answer');
            
            // Отметить все варианты как неактивные
            const options = element.parentElement.querySelectorAll('.game-option');
            options.forEach(opt => {
                opt.onclick = null;
                if (opt.classList.contains('correct-answer')) {
                    opt.classList.add('correct');
                } else {
                    opt.classList.add('incorrect');
                }
            });
            
            // Показать сообщение
            if (correct) {
                alert('Правильно! ' + getGameFeedback(questionId, true));
            } else {
                alert('Неправильно! ' + getGameFeedback(questionId, false));
            }
        }
        
        function getGameFeedback(questionId, isCorrect) {
            const feedback = {
                'hacker1': {
                    true: 'IP 45.33.12.184 пытался получить доступ к админке, что подозрительно для внутренней сети.',
                    false: 'Правильный ответ: IP 45.33.12.184. Доступ к админке с внешнего IP - подозрительное действие.'
                },
                'hacker2': {
                    true: 'Верно! Множественные попытки входа в админку - явный признак атаки.',
                    false: 'Правильный ответ: Множественные попытки входа в админку. Это брутфорс-атака.'
                },
                'virus1': {
                    true: 'Верно! Открытие вложений из неизвестных писем - основной способ заражения.',
                    false: 'Правильный ответ: Открытие вложений из неизвестных писем. Это опасно!'
                },
                'virus2': {
                    true: 'Правильно! Отключение интернет предотвратит утечку данных и распространение вируса.',
                    false: 'Правильный ответ: Отключить интернет и запустить антивирус. Это изолирует угрозу.'
                },
                'phish1': {
                    true: 'Верно! Банки никогда не просят данные по почте. Это явный фишинг.',
                    false: 'Правильный ответ: Письмо от банка с требованием срочных действий - это фишинг.'
                },
                'phish2': {
                    true: 'Правильно! Домен security-update.com не принадлежит Сбербанк - это подделка.',
                    false: 'Правильный ответ: sberbank.security-update.com - это поддельный домен, имитирующий Сбербанк.'
                }
            };
            
            return feedback[questionId][isCorrect];
        }
        
        // Викторина
        const quizQuestions = [
            {
                question: "Какой пароль самый надежный?",
                options: [
                    "123456",
                    "qwerty",
                    "M@k7$9vRlP!2",
                    "password"
                ],
                correct: 2,
                explanation: "Пароль 'M@k7$9vRlP!2' самый надежный, так как он длинный, содержит разные типы символов и не имеет личной информации."
            },
            {
                question: "Что нужно сделать, если вам пришло подозрительное письмо от банка?",
                options: [
                    "Перейти по ссылке в письме и проверить",
                    "Позвонить в банк по официальному номеру с их сайта",
                    "Ответить на письмо и уточнить информацию",
                    "Ничего не делать, это точно банк"
                ],
                correct: 1,
                explanation: "Нужно позвонить в банк по официальному номеру (не из письма!). Банки никогда не просят данные по email."
            },
            {
                question: "Как часто нужно обновлять программное обеспечение?",
                options: [
                    "Только когда перестанет работать",
                    "Раз в 5 лет",
                    "Как только выходят обновления безопасности",
                    "Никогда, это бесполезно"
                ],
                correct: 2,
                explanation: "Обновления безопасности нужно устанавливать сразу, так как они закрывают уязвимости, которыми могут воспользоваться хакеры."
            },
            {
                question: "Что из этого НЕ является признаком фишингового сайта?",
                options: [
                    "URL начинается с https://",
                    "Опечатки и ошибки в тексте",
                    "Требуют срочных действий",
                    "Запрос личных данных"
                ],
                correct: 0,
                explanation: "HTTPS - это стандартный защищенный протокол, а не признак фишинга. Хотя мошенники тоже могут использовать HTTPS."
            },
            {
                question: "Какой из этих Wi-Fi опаснее всего?",
                options: [
                    "Домашний Wi-Fi с паролем",
                    "Публичный Wi-Fi в кафе без пароля",
                    "Офисный Wi-Fi с авторизацией",
                    "Гостевой Wi-Fi у друга"
                ],
                correct: 1,
                explanation: "Публичный Wi-Fi без пароля наиболее опасен, так как злоумышленники могут перехватывать данные."
            }
        ];
        
        let currentQuestion = 0;
        let score = 0;
        
        document.getElementById('start-quiz').addEventListener('click', startQuiz);
        document.getElementById('quiz-next').addEventListener('click', nextQuestion);
        
        function startQuiz() {
            currentQuestion = 0;
            score = 0;
            document.getElementById('start-quiz').style.display = 'none';
            document.getElementById('quiz-result').style.display = 'none';
            showQuestion();
        }
        
        function showQuestion() {
            const questionElement = document.getElementById('quiz-question');
            const optionsElement = document.getElementById('quiz-options');
            const nextButton = document.getElementById('quiz-next');
            
            if (currentQuestion >= quizQuestions.length) {
                showResults();
                return;
            }
            
            const question = quizQuestions[currentQuestion];
            questionElement.textContent = (currentQuestion + 1) + ". " + question.question;
            
            optionsElement.innerHTML = '';
            question.options.forEach((option, index) => {
                const button = document.createElement('button');
                button.className = 'btn';
                button.style.background = '#6c5ce7';
                button.style.textAlign = 'left';
                button.textContent = option;
                button.onclick = () => selectAnswer(index);
                optionsElement.appendChild(button);
            });
            
            nextButton.style.display = 'none';
        }
        
        function selectAnswer(index) {
            const question = quizQuestions[currentQuestion];
            const options = document.querySelectorAll('#quiz-options button');
            
            // Отключить все кнопки
            options.forEach(btn => {
                btn.disabled = true;
                btn.style.background = '#6c5ce7';
            });
            
            // Показать правильный ответ
            if (index === question.correct) {
                options[index].style.background = '#00b894';
                score++;
            } else {
                options[index].style.background = '#ff7675';
                options[question.correct].style.background = '#00b894';
            }
            
            // Показать объяснение
            document.getElementById('quiz-question').textContent += `\n\n${question.explanation}`;
            
            document.getElementById('quiz-next').style.display = 'inline-block';
        }
        
        function nextQuestion() {
            currentQuestion++;
            showQuestion();
        }
        
        function showResults() {
            const resultElement = document.getElementById('quiz-result');
            const percentage = Math.round((score / quizQuestions.length) * 100);
            
            let message = '';
            if (percentage >= 80) {
                message = `Отлично! Вы набрали ${score} из ${quizQuestions.length} (${percentage}%). Вы настоящий эксперт по кибербезопасности!`;
            } else if (percentage >= 50) {
                message = `Неплохо! Вы набрали ${score} из ${quizQuestions.length} (${percentage}%). Но есть куда расти!`;
            } else {
                message = `Пока слабовато... Вы набрали ${score} из ${quizQuestions.length} (${percentage}%). Рекомендуем изучить материалы нашего сайта!`;
            }
            
            resultElement.textContent = message;
            resultElement.style.display = 'block';
            document.getElementById('start-quiz').style.display = 'inline-block';
            document.getElementById('start-quiz').textContent = 'Попробовать ещё раз';
        }
        
        // Плавная прокрутка для меню
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
    </script>
</body>
</html>
