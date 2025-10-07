<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сравнение автомобилей Mercedes, Porsche и Audi</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --mercedes-color: #00a7b5;
            --porsche-color: #cc0000;
            --audi-color: #c42034;
            --dark-bg: #1a1a1a;
            --light-bg: #f8f9fa;
            --card-bg: #ffffff;
            --text-dark: #333333;
            --text-light: #ffffff;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--light-bg);
            color: var(--text-dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--dark-bg) 0%, #2d2d2d 100%);
            color: var(--text-light);
            padding: 80px 0 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="%23000000" fill-opacity="0.1" d="M0,224L48,213.3C96,203,192,181,288,181.3C384,181,480,203,576,192C672,181,768,139,864,138.7C960,139,1056,181,1152,197.3C1248,213,1344,203,1392,197.3L1440,192L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-size: cover;
            background-position: center bottom;
        }

        .header-content {
            position: relative;
            z-index: 1;
        }

        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
            font-weight: 700;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        .subtitle {
            font-size: 1.2rem;
            margin-bottom: 40px;
            opacity: 0.8;
            font-weight: 300;
        }

        nav {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
        }

        .nav-link {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 500;
            padding: 12px 25px;
            border-radius: 30px;
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }

        .nav-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.1);
            transition: var(--transition);
        }

        .nav-link:hover::before {
            left: 0;
        }

        .nav-link.mercedes {
            border: 2px solid var(--mercedes-color);
        }

        .nav-link.porsche {
            border: 2px solid var(--porsche-color);
        }

        .nav-link.audi {
            border: 2px solid var(--audi-color);
        }

        .nav-link:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
        }

        /* Comparison Section */
        .comparison-section {
            padding: 80px 0;
            background-color: var(--light-bg);
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            position: relative;
            font-weight: 700;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(to right, var(--mercedes-color), var(--porsche-color), var(--audi-color));
            border-radius: 2px;
        }

        .comparison-table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 60px;
            background-color: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .comparison-table:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
        }

        .comparison-table th, .comparison-table td {
            padding: 20px;
            text-align: center;
            border-bottom: 1px solid #eee;
        }

        .comparison-table th {
            background-color: var(--dark-bg);
            color: var(--text-light);
            font-weight: 600;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .comparison-table tr:last-child td {
            border-bottom: none;
        }

        .comparison-table tbody tr:hover {
            background-color: rgba(0, 0, 0, 0.02);
        }

        .brand-header {
            font-weight: 700;
            font-size: 1.1rem;
        }

        .mercedes-header {
            color: var(--mercedes-color);
        }

        .porsche-header {
            color: var(--porsche-color);
        }

        .audi-header {
            color: var(--audi-color);
        }

        .highlight {
            background-color: rgba(204, 0, 0, 0.1);
            font-weight: 600;
            color: var(--porsche-color);
        }

        /* Car Sections */
        .car-section {
            padding: 100px 0;
            position: relative;
            overflow: hidden;
        }

        .car-section::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.03);
            z-index: -1;
        }

        .car-section:nth-child(even) {
            background-color: #f0f2f5;
        }

        .car-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }

        .car-image {
            flex: 1;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .car-image:hover {
            transform: scale(1.03);
        }

        .car-image img {
            width: 100%;
            height: auto;
            display: block;
            transition: var(--transition);
        }

        .car-info {
            flex: 1;
        }

        .car-title {
            font-size: 2.5rem;
            margin-bottom: 20px;
            font-weight: 700;
        }

        .mercedes-title {
            color: var(--mercedes-color);
        }

        .porsche-title {
            color: var(--porsche-color);
        }

        .audi-title {
            color: var(--audi-color);
        }

        .car-description {
            margin-bottom: 30px;
            font-size: 1.1rem;
            line-height: 1.8;
        }

        .car-features {
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            margin-bottom: 30px;
        }

        .feature {
            background-color: var(--card-bg);
            padding: 10px 20px;
            border-radius: 30px;
            font-size: 0.9rem;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .feature:hover {
            transform: translateY(-3px);
        }

        .mercedes-feature {
            border-left: 4px solid var(--mercedes-color);
        }

        .porsche-feature {
            border-left: 4px solid var(--porsche-color);
        }

        .audi-feature {
            border-left: 4px solid var(--audi-color);
        }

        .car-links {
            display: flex;
            gap: 15px;
            margin-top: 30px;
        }

        .btn {
            display: inline-flex;
            align-items: center;
            gap: 10px;
            padding: 12px 25px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.15);
        }

        .btn-primary {
            background-color: var(--dark-bg);
            color: var(--text-light);
        }

        .btn-secondary {
            background-color: transparent;
            color: var(--text-dark);
            border: 2px solid var(--dark-bg);
        }

        .mercedes-btn {
            background-color: var(--mercedes-color);
            color: white;
        }

        .porsche-btn {
            background-color: var(--porsche-color);
            color: white;
        }

        .audi-btn {
            background-color: var(--audi-color);
            color: white;
        }

        /* Progress Bars */
        .progress-container {
            margin-top: 30px;
        }

        .progress-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 8px;
            font-weight: 600;
        }

        .progress-bar {
            height: 10px;
            background-color: #e0e0e0;
            border-radius: 5px;
            overflow: hidden;
            margin-bottom: 20px;
        }

        .progress-fill {
            height: 100%;
            border-radius: 5px;
            transition: width 1.5s ease-in-out;
        }

        .mercedes-progress {
            background: linear-gradient(to right, var(--mercedes-color), #00c6d4);
        }

        .porsche-progress {
            background: linear-gradient(to right, var(--porsche-color), #ff3333);
        }

        .audi-progress {
            background: linear-gradient(to right, var(--audi-color), #e63347);
        }

        /* Footer */
        footer {
            background-color: var(--dark-bg);
            color: var(--text-light);
            padding: 60px 0 30px;
            text-align: center;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 30px;
        }

        .footer-logo {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .footer-links {
            display: flex;
            gap: 30px;
            margin-bottom: 30px;
        }

        .footer-link {
            color: var(--text-light);
            text-decoration: none;
            transition: var(--transition);
        }

        .footer-link:hover {
            color: #ccc;
        }

        .social-links {
            display: flex;
            gap: 20px;
            margin-bottom: 30px;
        }

        .social-link {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: rgba(255, 255, 255, 0.1);
            color: var(--text-light);
            text-decoration: none;
            transition: var(--transition);
        }

        .social-link:hover {
            background-color: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }

        .copyright {
            font-size: 0.9rem;
            opacity: 0.7;
        }

        /* Animations */
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

        .fade-in {
            animation: fadeInUp 0.8s ease forwards;
        }

        .delay-1 {
            animation-delay: 0.2s;
        }

        .delay-2 {
            animation-delay: 0.4s;
        }

        .delay-3 {
            animation-delay: 0.6s;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .car-content {
                flex-direction: column;
            }
            
            .car-image, .car-info {
                flex: none;
                width: 100%;
            }
            
            h1 {
                font-size: 2.5rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }

        @media (max-width: 768px) {
            nav {
                flex-direction: column;
                gap: 15px;
            }
            
            .nav-link {
                width: 200px;
                margin: 0 auto;
            }
            
            .comparison-table {
                display: block;
                overflow-x: auto;
            }
            
            .car-links {
                flex-direction: column;
            }
            
            .footer-links {
                flex-direction: column;
                gap: 15px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <h1 class="fade-in">Сравнение автомобилей премиум-класса</h1>
            <p class="subtitle fade-in delay-1">Mercedes-Benz, Porsche и Audi - немецкое качество и инновации</p>
            <nav class="fade-in delay-2">
                <a href="#mercedes" class="nav-link mercedes"><i class="fas fa-star"></i> Mercedes</a>
                <a href="#porsche" class="nav-link porsche"><i class="fas fa-bolt"></i> Porsche</a>
                <a href="#audi" class="nav-link audi"><i class="fas fa-cogs"></i> Audi</a>
            </nav>
        </div>
    </header>

    <section class="comparison-section">
        <div class="container">
            <h2 class="section-title fade-in">Сравнительная таблица</h2>
            <table class="comparison-table fade-in delay-1">
                <thead>
                    <tr>
                        <th>Характеристика</th>
                        <th class="brand-header mercedes-header">Mercedes-Benz E-Class</th>
                        <th class="brand-header porsche-header">Porsche Panamera</th>
                        <th class="brand-header audi-header">Audi A6</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Тип двигателя</td>
                        <td>Бензиновый / гибрид</td>
                        <td>Бензиновый / гибрид</td>
                        <td>Бензиновый / дизельный / гибрид</td>
                    </tr>
                    <tr>
                        <td>Расход топлива (л/100 км)</td>
                        <td>7.2</td>
                        <td>9.4</td>
                        <td>6.8</td>
                    </tr>
                    <tr>
                        <td>Тип КПП</td>
                        <td>Автоматическая</td>
                        <td>Роботизированная (PDK)</td>
                        <td>Автоматическая</td>
                    </tr>
                    <tr>
                        <td>Количество передач</td>
                        <td>9</td>
                        <td>8</td>
                        <td>7</td>
                    </tr>
                    <tr>
                        <td>Габариты (Д×Ш×В)</td>
                        <td>4935×1852×1468 мм</td>
                        <td>5049×1937×1423 мм</td>
                        <td>4939×1886×1457 мм</td>
                    </tr>
                    <tr>
                        <td>Объем багажника (л)</td>
                        <td>540</td>
                        <td>495</td>
                        <td>530</td>
                    </tr>
                    <tr>
                        <td>Разгон 0–100 км/ч</td>
                        <td>6.1 c</td>
                        <td>4.4 c</td>
                        <td>6.0 c</td>
                    </tr>
                    <tr>
                        <td>Максимальная скорость (км/ч)</td>
                        <td>250</td>
                        <td>295</td>
                        <td>250</td>
                    </tr>
                    <tr>
                        <td>Начальная цена (евро)</td>
                        <td>55 000</td>
                        <td class="highlight">95 000</td>
                        <td>53 000</td>
                    </tr>
                    <tr>
                        <td>Wi-Fi / Bluetooth</td>
                        <td>Да / Да</td>
                        <td>Да / Да</td>
                        <td>Да / Да</td>
                    </tr>
                    <tr>
                        <td>Системы безопасности</td>
                        <td>ABS, ESP, подушки, ассистенты</td>
                        <td>ABS, ESP, подушки, ассистенты</td>
                        <td>ABS, ESP, подушки, ассистенты</td>
                    </tr>
                    <tr>
                        <td>Гарантийный срок</td>
                        <td>3 года</td>
                        <td>2 года</td>
                        <td>3 года</td>
                    </tr>
                </tbody>
                <tfoot>
                    <tr>
                        <td>Итог</td>
                        <td>Комфорт и надежность</td>
                        <td>Динамика и премиум</td>
                        <td>Баланс и технологии</td>
                    </tr>
                </tfoot>
            </table>
        </div>
    </section>

    <section id="mercedes" class="car-section">
        <div class="container">
            <div class="car-content fade-in">
                <div class="car-image">
                    <img src="https://static.bangkokpost.com/media/content/20200303/3549909.jpg" alt="Mercedes E-Class">
                </div>
                <div class="car-info">
                    <h2 class="car-title mercedes-title">Mercedes-Benz E-Class</h2>
                    <p class="car-description">Mercedes-Benz E-Class - это эталон бизнес-класса, сочетающий в себе роскошь, комфорт и передовые технологии. Модель оснащена адаптивным круиз-контролем, системой удержания в полосе, а также функцией предотвращения столкновений.</p>
                    
                    <div class="car-features">
                        <div class="feature mercedes-feature">Бензиновый / гибридный двигатель</div>
                        <div class="feature mercedes-feature">9-ступенчатая АКПП</div>
                        <div class="feature mercedes-feature">Объем багажника 540 л</div>
                        <div class="feature mercedes-feature">Расход топлива 7.2 л/100км</div>
                    </div>
                    
                    <div class="progress-container">
                        <div class="progress-label">
                            <span>Безопасность</span>
                            <span>90%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill mercedes-progress" style="width: 90%"></div>
                        </div>
                        
                        <div class="progress-label">
                            <span>Комфорт</span>
                            <span>95%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill mercedes-progress" style="width: 95%"></div>
                        </div>
                        
                        <div class="progress-label">
                            <span>Технологии</span>
                            <span>88%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill mercedes-progress" style="width: 88%"></div>
                        </div>
                    </div>
                    
                    <div class="car-links">
                        <a href="https://www.mercedes-benz.com.my/passengercars/models/saloon/e-class/overview.html?abtest-new_cta_print=target&gagcmid=GA_20095899093_144110473170_715317443935&gclsrc=aw.ds&&cmp=SEM__googleSEM___mercedes%20malaysia&mkwid=s_pcrid_715317443935_pdv_t&gad_source=1&gad_campaignid=20095899093" class="btn mercedes-btn" target="_blank">
                            <i class="fas fa-external-link-alt"></i> Официальный сайт
                        </a>
                        <a href="https://www.mercedes-benz.co.in/passengercars/models/saloon/e-class/overview.html" class="btn btn-secondary" target="_blank">
                            <i class="fas fa-info-circle"></i> Подробнее
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="porsche" class="car-section">
        <div class="container">
            <div class="car-content fade-in">
                <div class="car-info">
                    <h2 class="car-title porsche-title">Porsche Panamera</h2>
                    <p class="car-description">Porsche Panamera - это уникальное сочетание спортивного характера и роскоши бизнес-класса. Модель предлагает гибридные версии, мощные V6 и V8 двигатели, адаптивную подвеску и спортивный салон с премиальными материалами.</p>
                    
                    <div class="car-features">
                        <div class="feature porsche-feature">Бензиновый / гибридный двигатель</div>
                        <div class="feature porsche-feature">8-ступенчатая PDK</div>
                        <div class="feature porsche-feature">Разгон 0-100 за 4.4 с</div>
                        <div class="feature porsche-feature">Макс. скорость 295 км/ч</div>
                    </div>
                    
                    <div class="progress-container">
                        <div class="progress-label">
                            <span>Безопасность</span>
                            <span>95%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill porsche-progress" style="width: 95%"></div>
                        </div>
                        
                        <div class="progress-label">
                            <span>Динамика</span>
                            <span>98%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill porsche-progress" style="width: 98%"></div>
                        </div>
                        
                        <div class="progress-label">
                            <span>Премиум-качество</span>
                            <span>96%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill porsche-progress" style="width: 96%"></div>
                        </div>
                    </div>
                    
                    <div class="car-links">
                        <a href="https://www.porsche.com/international/models/panamera/panamera-models/panamera" class="btn porsche-btn" target="_blank">
                            <i class="fas fa-external-link-alt"></i> Официальный сайт
                        </a>
                        <a href="https://www.porsche.cn/china/en/models/panamera" class="btn btn-secondary" target="_blank">
                            <i class="fas fa-info-circle"></i> Подробнее
                        </a>
                    </div>
                </div>
                <div class="car-image">
                    <img src="https://i.ytimg.com/vi/BrHUEeqYeXo/maxresdefault.jpg" alt="Porsche Panamera">
                </div>
            </div>
        </div>
    </section>

    <section id="audi" class="car-section">
        <div class="container">
            <div class="car-content fade-in">
                <div class="car-image">
                    <img src="https://columbauto.by/upload/iblock/5f8/5f8848634ba60c5fa3887160d117a3df.jpg" alt="Audi A6">
                </div>
                <div class="car-info">
                    <h2 class="car-title audi-title">Audi A6</h2>
                    <p class="car-description">Audi A6 - это гармоничное сочетание стиля, технологичности и немецкого качества. Модель оснащена системой mild-hybrid, полным приводом quattro и интеллектуальной мультимедийной системой MMI Touch с сенсорным управлением.</p>
                    
                    <div class="car-features">
                        <div class="feature audi-feature">Бензиновый / дизельный / гибрид</div>
                        <div class="feature audi-feature">7-ступенчатая АКПП</div>
                        <div class="feature audi-feature">Система полного привода quattro</div>
                        <div class="feature audi-feature">Расход топлива 6.8 л/100км</div>
                    </div>
                    
                    <div class="progress-container">
                        <div class="progress-label">
                            <span>Безопасность</span>
                            <span>88%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill audi-progress" style="width: 88%"></div>
                        </div>
                        
                        <div class="progress-label">
                            <span>Технологии</span>
                            <span>92%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill audi-progress" style="width: 92%"></div>
                        </div>
                        
                        <div class="progress-label">
                            <span>Экономичность</span>
                            <span>90%</span>
                        </div>
                        <div class="progress-bar">
                            <div class="progress-fill audi-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    
                    <div class="car-links">
                        <a href="https://www.audi.com/en" class="btn audi-btn" target="_blank">
                            <i class="fas fa-external-link-alt"></i> Официальный сайт
                        </a>
                        <a href="https://autoidea.by/aktualnyie-predlozheniya/novyi-bmw-5/?utm_source=yandex&utm_medium=cpc&utm_campaign=Мастер_кампаний_BMW_5_в_лизинг_001_в_BYN&utm_term=---autotargeting&utm_content=сентябрь&ybaip=1&yclid=8817427041896628223" class="btn btn-secondary" target="_blank">
                            <i class="fas fa-info-circle"></i> Подробнее
                        </a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">AutoComparison</div>
                <p>Сравнение автомобилей премиум-класса с акцентом на детали и технологии</p>
                
                <div class="footer-links">
                    <a href="#" class="footer-link">О проекте</a>
                    <a href="#" class="footer-link">Контакты</a>
                    <a href="#" class="footer-link">Политика конфиденциальности</a>
                </div>
                
                <div class="social-links">
                    <a href="#" class="social-link"><i class="fab fa-facebook-f"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-twitter"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-instagram"></i></a>
                    <a href="#" class="social-link"><i class="fab fa-youtube"></i></a>
                </div>
                
                <p class="copyright">© 2025 AutoComparison. Все права защищены.</p>
            </div>
        </div>
    </footer>

    <script>
        // Анимация прогресс-баров при прокрутке
        document.addEventListener('DOMContentLoaded', function() {
            const progressBars = document.querySelectorAll('.progress-fill');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const width = entry.target.style.width;
                        entry.target.style.width = '0';
                        setTimeout(() => {
                            entry.target.style.width = width;
                        }, 300);
                    }
                });
            }, { threshold: 0.5 });
            
            progressBars.forEach(bar => {
                observer.observe(bar);
            });
            
            // Плавная прокрутка к якорям
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    
                    const targetId = this.getAttribute('href');
                    const targetElement = document.querySelector(targetId);
                    
                    if (targetElement) {
                        window.scrollTo({
                            top: targetElement.offsetTop - 80,
                            behavior: 'smooth'
                        });
                    }
                });
            });
        });
    </script>
</body>
</html>
