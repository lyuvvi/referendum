<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ЭАС "Местный референдум"</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f5f5f5;
            color: #333;
        }
        header {
            background-color: #1e5f8c;
            color: rgb(197, 23, 23);
            padding: 20px;
            text-align: center;
        }
        nav {
            background-color: #2a7bb6;
            padding: 10px;
        }
        nav ul {
            list-style-type: none;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: space-around;
        }
        nav li {
            display: inline;
        }
        nav a {
            color: white;
            text-decoration: none;
            padding: 10px 15px;
        }
        nav a:hover {
            background-color: #1e5f8c;
            border-radius: 5px;
        }
        .container {
            max-width: 1200px;
            margin: 20px auto;
            padding: 20px;
            background-color: white;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        .section {
            margin-bottom: 30px;
            padding: 20px;
            border-bottom: 1px solid #eee;
        }
        .section:last-child {
            border-bottom: none;
        }
        h1, h2, h3 {
            color: #1e5f8c;
        }
        
        h4 {
            color: #ffffff;
            font-size: 26px;
        }
        .btn {
            display: inline-block;
            background-color: #1e5f8c;
            color: white;
            padding: 10px 20px;
            text-decoration: none;
            border-radius: 5px;
            margin: 10px 0;
        }
        .btn:hover {
            background-color: #2a7bb6;
        }
        .login-form {
            max-width: 500px;
            margin: 0 auto;
            padding: 20px;
            background-color: #f9f9f9;
            border-radius: 5px;
        }
        .form-group {
            margin-bottom: 15px;
        }
        .form-group label {
            display: block;
            margin-bottom: 5px;
            font-weight: bold;
        }
        .form-group input, .form-group select, .form-group textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        .form-group textarea {
            height: 100px;
        }
        .file-upload {
            border: 1px dashed #ddd;
            padding: 20px;
            text-align: center;
            margin-bottom: 15px;
        }
        .ballot {
            border: 1px solid #ddd;
            padding: 20px;
            margin-bottom: 20px;
        }
        .ballot-option {
            margin: 15px 0;
            padding: 10px;
            border: 1px solid #eee;
            cursor: pointer;
        }
        .ballot-option:hover {
            background-color: #f5f5f5;
        }
        .selected {
            background-color: #e1f5fe;
            border-color: #1e5f8c;
        }
        footer {
            background-color: #1e5f8c;
            color: white;
            text-align: center;
            padding: 20px;
            
            margin-top: 20px;
        }
        .tab-content {
            display: none;
        }
        .tab-content.active {
            display: block;
        }
        .progress-bar {
            height: 20px;
            background-color: #e0e0e0;
            border-radius: 10px;
            margin: 10px 0;
        }
        .progress {
            height: 100%;
            background-color: #1e5f8c;
            border-radius: 10px;
            width: 0%;
            transition: width 0.3s;
        }
    </style>
</head>
<body>
    <header>
        <h4>Электронная автоматизированная система "Местный референдум"</h4>
    </header>
    
    <nav>
        <ul>
            <li><a href="#" onclick="openTab('home')">Главная</a></li>
            <li><a href="#" onclick="openTab('referendums')">Запланированные референдумы</a></li>
            <li><a href="#" onclick="openTab('about')">О нас</a></li>
            <li><a href="#" onclick="openTab('process')">Процесс участия</a></li>
            <li><a href="#" onclick="openTab('registration')">Регистрация</a></li>
            <li><a href="#" onclick="openTab('initiatives')">Инициативы</a></li>
            <li><a href="#" onclick="openTab('results')">Результаты</a></li>
            <li><a href="#" onclick="openTab('support')">Техподдержка</a></li>
        </ul>
    </nav>
    
    <div class="container">
        <!-- Главная страница -->
        <div id="home" class="tab-content active">
            <h2>Добро пожаловать в систему электронного голосования</h2>
            <p>Наша платформа предоставляет гражданам удобный инструмент для участия в местных референдумах, инициации общественных инициатив и выражения своей гражданской позиции.</p>
            
            <div style="display: flex; justify-content: space-around; margin: 30px 0;">
                <div style="text-align: center;">
                    <h3>Голосование</h3>
                    <p>Примите участие в текущих референдумах</p>
                    <a href="#" onclick="openTab('referendums')" class="btn">Перейти</a>
                </div>
                <div style="text-align: center;">
                    <h3>Инициатива</h3>
                    <p>Предложите свою инициативу для референдума</p>
                    <a href="#" onclick="openTab('initiatives')" class="btn">Перейти</a>
                </div>
                <div style="text-align: center;">
                    <h3>Результаты</h3>
                    <p>Ознакомьтесь с итогами голосований</p>
                    <a href="#" onclick="openTab('results')" class="btn">Перейти</a>
                </div>
            </div>
        </div>
        
        <!-- Запланированные референдумы -->
        <div id="referendums" class="tab-content">
            <h2>Запланированные местные референдумы (Волгоградская область)</h2>
            
            <div class="section">
                <h3>Текущие референдумы</h3>
                <div class="ballot">
                    <h4>Строительство мусоросжигающего и перерабатывающего завода в Дубовском муниципальном районе Волгоградской области</h4>
                    <p>Дата проведения: 15.10.2026</p>
                    <p>Статус: сбор подписей</p>
                    <div class="progress-bar">
                        <div class="progress" style="width: 42%;"></div>
                    </div>
                    <p>Собрано подписей: 42% от необходимого количества</p>
                    <a href="#" class="btn">Подробнее</a>
                    <a href="#" class="btn">Подписать</a>
                </div>
            </div>
            
            <div class="section">
                <h3>Прошедшие референдумы</h3>
                <ul>
                    <li>Референдум о строительстве нового моста через реку Волга (12.06.2026) - <a href="#">Результаты</a></li>
                    <li>Референдум о переименовании улицы Ленина в г. Волжский (03.04.2026) - <a href="#">Результаты</a></li>
                </ul>
            </div>
        </div>
        
        <!-- О нас -->
        <div id="about" class="tab-content">
            <h2>О системе "Местный референдум"</h2>
            <p>Электронная автоматизированная система "Местный референдум" разработана для упрощения и цифровизации процесса организации и проведения местных референдумов на территории Российской Федерации.</p>
            
            <h3>Наши преимущества:</h3>
            <ul>
                <li>Полностью цифровой процесс от инициации до подведения итогов</li>
                <li>Интеграция с порталом Госуслуг для удобной верификации</li>
                <li>Прозрачность всех этапов процесса</li>
                <li>Гарантия тайны голосования</li>
                <li>Доступность для всех граждан</li>
            </ul>
            
            <h3>Технологии:</h3>
            <p>Система использует современные технологии защиты данных, включая криптографические алгоритмы и блокчейн-технологии для обеспечения безопасности и неизменности результатов голосования.</p>
        </div>
        
        <!-- Процесс участия -->
        <div id="process" class="tab-content">
            <h2>Последовательность участия в электронном голосовании</h2>
            
            <div style="display: flex; justify-content: space-between; margin: 30px 0;">
                <div style="width: 30%; text-align: center;">
                    <h3>1. Регистрация</h3>
                    <p>Зарегистрируйтесь в системе через Госуслуги или лично в МФЦ</p>
                </div>
                <div style="width: 30%; text-align: center;">
                    <h3>2. Инициатива</h3>
                    <p>Предложите свою инициативу или поддержите существующую</p>
                </div>
                <div style="width: 30%; text-align: center;">
                    <h3>3. Голосование</h3>
                    <p>Примите участие в референдуме в установленные сроки</p>
                </div>
            </div>
            
            <div class="section">
                <h3>Подробное описание процесса</h3>
                <h4>Регистрация</h4>
                <p>Платформа предоставляет пользователям два удобных способа регистрации, обеспечивающих надежную верификацию личности и места жительства: электронный вариант через систему Госуслуг (ЕСИА) с автоматической авторизацией или традиционный очный способ путем личного обращения в МФЦ либо административный орган муниципалитета.</p>
                
                <h4>Инициация референдума</h4>
                <p>Процесс начинается с заполнения специальной электронной формы, где инициаторы указывают название, полное и краткое описание предлагаемой инициативы (с возможностью прикрепления PDF-документов), а также предоставляют её юридическое обоснование, при необходимости.</p>
                
                <h4>Сбор подписей</h4>
                <p>Сбор подписей осуществляется через инновационную систему электронных подписных листов, где каждая подпись подтверждается через верифицированную учетную запись пользователя и электронной графической подписи.</p>
                
                <h4>Голосование</h4>
                <p>После утверждения даты и окончательной формулировки вопроса референдума, система организует безопасный процесс электронного голосования через подтвержденные аккаунты пользователей, используя блокчейн-технологии или усиленные системы онлайн-защиты для обеспечения полной конфиденциальности и неизменности волеизъявления граждан.</p>
            </div>
        </div>
        
        <!-- Регистрация -->
        <div id="registration" class="tab-content">
            <h2>Регистрация в системе</h2>
            
            <div class="login-form">
                <h3>Вход через Госуслуги (ЕСИА)</h3>
                <p>Для входа в систему используйте вашу учетную запись на портале Госуслуг.</p>
                <a href="#" class="btn" style="background-color: #2a7bb6;">Войти через Госуслуги</a>
                
                <div style="text-align: center; margin: 20px 0;">
                    <hr style="border-top: 1px solid #ddd;">
                    <span style="background-color: #f9f9f9; padding: 0 10px; position: relative; top: -15px;">ИЛИ</span>
                </div>
                
                <h3>Очная регистрация</h3>
                <p>Если у вас нет учетной записи на Госуслугах, вы можете зарегистрироваться лично в МФЦ или администрации вашего муниципалитета.</p>
                <div class="form-group">
                    <label>Фамилия</label>
                    <input type="text">
                </div>
                <div class="form-group">
                    <label>Имя</label>
                    <input type="text">
                </div>
                <div class="form-group">
                    <label>Отчество</label>
                    <input type="text">
                </div>
                <div class="form-group">
                    <label>Адрес проживания</label>
                    <input type="text">
                </div>
                <div class="form-group">
                    <label>Электронная почта</label>
                    <input type="email">
                </div>
                <div class="form-group">
                    <label>Номер телефона</label>
                    <input type="tel">
                </div>
                <a href="#" class="btn">Зарегистрироваться</a>
            </div>
        </div>
        
        <!-- Инициативы -->
        <div id="initiatives" class="tab-content">
            <h2>Регистрация инициативы</h2>
            
            <div class="section">
                <h3>Новая инициатива</h3>
                <form>
                    <div class="form-group">
                        <label>Фамилия / Имя / Отчество*</label>
                        <input type="text" placeholder="Фамилия Имя Отчество">
                    </div>
                    <div class="form-group">
                        <label>Паспортные данные*</label>
                        <input type="text" placeholder="Серия и номер паспорта">
                    </div>
                    <div class="form-group">
                        <label>Эл. почта / Номер телефона*</label>
                        <input type="text" placeholder="example@example.com или +7XXXXXXXXXX">
                    </div>
                    <div class="form-group">
                        <label>Содержание инициативы*</label>
                        <textarea placeholder="Подробно опишите вашу инициативу"></textarea>
                    </div>
                    <div class="form-group">
                        <label>Прикрепить документы (если имеются)</label>
                        <div class="file-upload">
                            <p>Перетащите файлы сюда или</p>
                            <input type="file" id="file-upload">
                            <label for="file-upload" class="btn">Выбрать файл</label>
                            <p id="file-name">Файл не выбран</p>
                        </div>
                    </div>
                    <button type="submit" class="btn">Зарегистрировать инициативу</button>
                </form>
            </div>
            
            <div class="section">
                <h3>Текущие инициативы</h3>
                <div class="ballot">
                    <h4>Строительство детского сада в микрорайоне "Южный"</h4>
                    <p>Инициатор: Иванов Иван Иванович</p>
                    <p>Дата регистрации: 15.08.2026</p>
                    <p>Статус: сбор инициативной группы</p>
                    <div class="progress-bar">
                        <div class="progress" style="width: 65%;"></div>
                    </div>
                    <p>Участников группы: 65 из 100 необходимых</p>
                    <a href="#" class="btn">Подробнее</a>
                    <a href="#" class="btn">Присоединиться</a>
                </div>
                
                <div class="ballot">
                    <h4>Ограничение скорости на улице Центральной до 40 км/ч</h4>
                    <p>Инициатор: Петрова Мария Сергеевна</p>
                    <p>Дата регистрации: 01.09.2026</p>
                    <p>Статус: сбор подписей</p>
                    <div class="progress-bar">
                        <div class="progress" style="width: 28%;"></div>
                    </div>
                    <p>Собрано подписей: 28% от необходимого количества</p>
                    <a href="#" class="btn">Подробнее</a>
                    <a href="#" class="btn">Подписать</a>
                </div>
            </div>
        </div>
        
        <!-- Результаты -->
        <div id="results" class="tab-content">
            <h2>Итоговые результаты голосования</h2>
            
            <div class="section">
                <h3>Референдум о строительстве нового моста через реку Волга</h3>
                <p>Дата проведения: 12.06.2026</p>
                <p>Явка: 68% от общего числа зарегистрированных избирателей</p>
                
                <div style="display: flex; justify-content: space-between; margin: 20px 0;">
                    <div style="width: 48%; background-color: #00850b; padding: 15px; border-radius: 5px;">
                        <h4>За строительство</h4>
                        <p>42,356 голосов (62%)</p>
                    </div>
                    <div style="width: 48%; background-color: #ff0026; padding: 15px; border-radius: 5px;">
                        <h4>Против строительства</h4>
                        <p>25,987 голосов (38%)</p>
                    </div>
                </div>
                
                <p><strong>Итог:</strong> Инициатива о строительстве нового моста через реку Волга принята большинством голосов.</p>
            </div>
            
            <div class="section">
                <h3>Референдум о переименовании улицы Ленина в г. Волжский</h3>
                <p>Дата проведения: 03.04.2026</p>
                <p>Явка: 54% от общего числа зарегистрированных избирателей</p>
                
                <div style="display: flex; justify-content: space-between; margin: 20px 0;">
                    <div style="width: 48%; background-color: #00850b; padding: 15px; border-radius: 5px;">
                        <h4>За переименование</h4>
                        <p>18,742 голосов (45%)</p>
                    </div>
                    <div style="width: 48%; background-color: #ff0026; padding: 15px; border-radius: 5px;">
                        <h4>Против переименования</h4>
                        <p>22,856 голосов (55%)</p>
                    </div>
                </div>
                
                <p><strong>Итог:</strong> Инициатива о переименовании улицы Ленина в г. Волжский не набрала необходимого количества голосов.</p>
            </div>
        </div>
        
        <!-- Техподдержка -->
        <div id="support" class="tab-content">
            <h2>Техническая поддержка</h2>
            
            <div class="section">
                <h3>Часто задаваемые вопросы</h3>
                <div>
                    <h4>Как зарегистрироваться в системе?</h4>
                    <p>Вы можете зарегистрироваться через портал Госуслуг или лично в МФЦ или администрации вашего муниципалитета.</p>
                </div>
                <div>
                    <h4>Как предложить свою инициативу?</h4>
                    <p>Перейдите в раздел "Инициативы", заполните форму и следуйте инструкциям системы.</p>
                </div>
                <div>
                    <h4>Как проголосовать?</h4>
                    <p>В период проведения референдума в вашем личном кабинете появится возможность проголосовать по текущим вопросам.</p>
                </div>
            </div>
            
            <div class="section">
                <h3>Свяжитесь с нами</h3>
                <form>
                    <div class="form-group">
                        <label>Ваше имя</label>
                        <input type="text">
                    </div>
                    <div class="form-group">
                        <label>Электронная почта</label>
                        <input type="email">
                    </div>
                    <div class="form-group">
                        <label>Тема обращения</label>
                        <select>
                            <option>Техническая проблема</option>
                            <option>Вопрос по регистрации</option>
                            <option>Вопрос по голосованию</option>
                            <option>Другое</option>
                        </select>
                    </div>
                    <div class="form-group">
                        <label>Сообщение</label>
                        <textarea></textarea>
                    </div>
                    <button type="submit" class="btn">Отправить</button>
                </form>
            </div>
        </div>
        
        <!-- Форма голосования -->
        <div id="vote" class="tab-content">
            <h2>Форма электронного избирательного бюллетеня</h2>
            
            <div class="section">
                <div style="background-color: #f5f5f5; padding: 15px; border-radius: 5px; margin-bottom: 20px;">
                    <h3>Разъяснение о порядке заполнения электронного избирательного бюллетеня</h3>
                    <p>1. Процедура голосования:</p>
                    <p>Для выражения своей воли выберите один из предложенных вариантов ответа на вопрос референдума:</p>
                    <p>Нажмите на квадрат (□) справа от варианта "ЗА", если поддерживаете предложенную инициативу;</p>
                    <p>Нажмите на квадрат (□) справа от варианта "ПРОТИВ", если выступаете против предложенной инициативы.</p>
                    <p>Система автоматически зафиксирует ваш выбор в виде отметки (✓) в соответствующем квадрате.</p>
                    
                    <p>2. Требования к действительности бюллетеня</p>
                    <p>Бюллетень считается действительным, если отмечен только один вариант ответа.</p>
                    <p>Бюллетень признаётся недействительным, если:</p>
                    <p>не отмечен ни один вариант;</p>
                    <p>отмечены оба варианта ответа;</p>
                    <p>внесены несанкционированные изменения в форму бюллетеня.</p>
                </div>
                
                <div class="ballot">
                    <h3>Вопрос референдума:</h3>
                    <p>Строительство мусоросжигающего и перерабатывающего завода в Дубовском муниципальном районе Волгоградской области?</p>
                    
                    <div class="ballot-option" onclick="selectOption(this)">
                        <input type="radio" name="vote" id="vote-yes" style="display: none;">
                        <label for="vote-yes" style="display: flex; align-items: center;">
                            <div style="width: 20px; height: 20px; border: 2px solid #1e5f8c; margin-right: 10px; display: flex; align-items: center; justify-content: center;">
                                <div style="width: 12px; height: 12px; background-color: #1e5f8c; display: none;"></div>
                            </div>
                            <span>ЗА строительство мусоросжигающего и перерабатывающего завода в Дубовском муниципальном районе Волгоградской области</span>
                        </label>
                    </div>
                    
                    <div class="ballot-option" onclick="selectOption(this)">
                        <input type="radio" name="vote" id="vote-no" style="display: none;">
                        <label for="vote-no" style="display: flex; align-items: center;">
                            <div style="width: 20px; height: 20px; border: 2px solid #1e5f8c; margin-right: 10px; display: flex; align-items: center; justify-content: center;">
                                <div style="width: 12px; height: 12px; background-color: #1e5f8c; display: none;"></div>
                            </div>
                            <span>ПРОТИВ строительства мусоросжигающего и перерабатывающего завода в Дубовском муниципальном районе Волгоградской области</span>
                        </label>
                    </div>
                    
                    <div style="margin-top: 30px; display: flex; justify-content: space-between;">
                        <a href="#" class="btn" style="background-color: #757575;">Назад</a>
                        <a href="#" class="btn" id="confirm-btn" style="display: none;">Подтвердить</a>
                    </div>
                </div>
            </div>
        </div>
    </div>
    
    <footer>
        <p>Авторские права © 2026 Все права защищены - ЭАС "Местный референдум"</p>
        
    </footer>
    
    <script>
        function openTab(tabId) {
            // Скрыть все вкладки
            var tabs = document.getElementsByClassName('tab-content');
            for (var i = 0; i < tabs.length; i++) {
                tabs[i].classList.remove('active');
            }
            
            // Показать выбранную вкладку
            document.getElementById(tabId).classList.add('active');
        }
        
        function selectOption(element) {
            // Убрать выделение со всех вариантов
            var options = document.getElementsByClassName('ballot-option');
            for (var i = 0; i < options.length; i++) {
                options[i].classList.remove('selected');
                options[i].querySelector('div div').style.display = 'none';
            }
            
            // Выделить выбранный вариант
            element.classList.add('selected');
            element.querySelector('div div').style.display = 'block';
            
            // Показать кнопку подтверждения
            document.getElementById('confirm-btn').style.display = 'inline-block';
        }
        
        // Обработка загрузки файла
        document.getElementById('file-upload').addEventListener('change', function(e) {
            var fileName = e.target.files[0] ? e.target.files[0].name : 'Файл не выбран';
            document.getElementById('file-name').textContent = fileName;
        });
    </script>
</body>
</html>
