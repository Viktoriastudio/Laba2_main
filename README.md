<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Сравнение автомобилей Lamborghini, Voyah и Jaguar</title>
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #34495e;
            --shadow: 0 10px 30px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            min-height: 100vh;
            padding: 20px;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }
        
        header {
            text-align: center;
            padding: 40px 0;
            margin-bottom: 40px;
            position: relative;
            overflow: hidden;
            border-radius: 15px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            color: white;
            box-shadow: var(--shadow);
        }
        
        header::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1440 320"><path fill="rgba(255,255,255,0.1)" d="M0,96L48,112C96,128,192,160,288,186.7C384,213,480,235,576,213.3C672,192,768,128,864,128C960,128,1056,192,1152,192C1248,192,1344,128,1392,96L1440,64L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"></path></svg>');
            background-size: cover;
            background-position: center;
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
            position: relative;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
        }
        
        .subtitle {
            font-size: 1.2rem;
            opacity: 0.9;
            position: relative;
        }
        
        .comparison-table {
            background-color: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            margin-bottom: 40px;
            transition: var(--transition);
        }
        
        .comparison-table:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 35px rgba(0,0,0,0.15);
        }
        
        table {
            width: 100%;
            border-collapse: collapse;
        }
        
        caption {
            font-size: 1.8rem;
            font-weight: bold;
            padding: 25px;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            color: white;
            position: relative;
        }
        
        th, td {
            padding: 18px 15px;
            text-align: center;
            transition: var(--transition);
        }
        
        thead th {
            background-color: var(--light-color);
            font-weight: 600;
            color: var(--dark-color);
            border-bottom: 2px solid #ddd;
            position: relative;
        }
        
        thead th:first-child {
            border-radius: 15px 0 0 0;
        }
        
        thead th:last-child {
            border-radius: 0 15px 0 0;
        }
        
        tbody tr:nth-child(even) {
            background-color: #f9f9f9;
        }
        
        tbody tr:hover {
            background-color: #f0f7ff;
        }
        
        tbody tr:hover td {
            transform: scale(1.02);
        }
        
        tfoot td {
            background-color: var(--light-color);
            font-weight: bold;
            color: var(--dark-color);
            border-top: 2px solid #ddd;
            padding: 20px;
        }
        
        mark {
            background: linear-gradient(120deg, #f6d365 0%, #fda085 100%);
            padding: 3px 8px;
            border-radius: 4px;
            font-weight: bold;
        }
        
        .car-details {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }
        
        .car-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }
        
        .car-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.15);
        }
        
        .car-images {
            height: 220px;
            overflow: hidden;
            position: relative;
        }
        
        .car-images img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: var(--transition);
        }
        
        .car-card:hover .car-images img {
            transform: scale(1.05);
        }
        
        .car-info {
            padding: 25px;
        }
        
        .car-info h3 {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: var(--primary-color);
            display: flex;
            align-items: center;
            justify-content: space-between;
        }
        
        .car-info h3 span {
            font-size: 0.9rem;
            background: var(--secondary-color);
            color: white;
            padding: 5px 10px;
            border-radius: 20px;
        }
        
        .car-info p {
            margin-bottom: 20px;
            color: #555;
        }
        
        .car-link {
            display: inline-block;
            background: linear-gradient(to right, var(--primary-color), var(--secondary-color));
            color: white;
            padding: 10px 20px;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            box-shadow: 0 4px 15px rgba(52, 152, 219, 0.3);
        }
        
        .car-link:hover {
            transform: translateY(-3px);
            box-shadow: 0 7px 20px rgba(52, 152, 219, 0.4);
        }
        
        .brand-logos {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin: 40px 0;
            flex-wrap: wrap;
        }
        
        .brand-logo {
            width: 120px;
            height: 120px;
            background: white;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: var(--shadow);
            transition: var(--transition);
            cursor: pointer;
        }
        
        .brand-logo:hover {
            transform: scale(1.1);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }
        
        .brand-logo img {
            max-width: 70%;
            max-height: 70%;
        }
        
        footer {
            text-align: center;
            padding: 30px;
            margin-top: 40px;
            color: var(--dark-color);
            font-size: 0.9rem;
            border-top: 1px solid #ddd;
        }
        
        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            .car-details {
                grid-template-columns: 1fr;
            }
            
            th, td {
                padding: 12px 8px;
                font-size: 0.9rem;
            }
            
            .brand-logos {
                gap: 20px;
            }
            
            .brand-logo {
                width: 80px;
                height: 80px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Сравнение автомобилей</h1>
            <p class="subtitle">Lamborghini, Voyah и Jaguar</p>
        </header>
        
        <div class="brand-logos">
            <div class="brand-logo">
                <img src="img/img1.svg" alt="Lamborghini">
            </div>
            <div class="brand-logo">
                <img src="img/img2.png" alt="Voyah">
            </div>
            <div class="brand-logo">
                <img src="img/img3.png" alt="Jaguar">
            </div>
        </div>
        
        <div class="comparison-table">
            <table>
                <caption>Основные характеристики автомобилей</caption>
                <thead>
                    <tr>
                        <th>Характеристика</th>
                        <th>Lamborghini Revuelto</th>
                        <th>Voyah Free</th>
                        <th>Jaguar F-Type</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Двигатель</td>
                        <td>Гибридный (V12 + электромотор)</td>
                        <td>Электрический / гибридный</td>
                        <td>Бензиновый (V8)</td>
                    </tr>
                    <tr>
                        <td>Расход топлива (л/100 км)</td>
                        <td>11.0</td>
                        <td>1.5 (гибрид)</td>
                        <td>10.7</td>
                    </tr>
                    <tr>
                        <td>Тип КПП</td>
                        <td>Роботизированная</td>
                        <td>Автоматическая</td>
                        <td>Автоматическая</td>
                    </tr>
                    <tr>
                        <td>Количество передач</td>
                        <td>8</td>
                        <td>7</td>
                        <td>8</td>
                    </tr>
                    <tr>
                        <td>Максимальная скорость (км/ч)</td>
                        <td><mark>350</mark></td>
                        <td>200</td>
                        <td>285</td>
                    </tr>
                    <tr>
                        <td>Разгон 0–100 км/ч</td>
                        <td>2.5 c</td>
                        <td>4.8 c</td>
                        <td>4.4 c</td>
                    </tr>
                    <tr>
                        <td>Гарантийный срок</td>
                        <td>3 года</td>
                        <td>5 лет</td>
                        <td>3 года</td>
                    </tr>
                    <tr>
                        <td>Наличие экологических сертификатов</td>
                        <td>Euro 6</td>
                        <td><mark>EV / Zero Emission</mark></td>
                        <td>Euro 6</td>
                    </tr>
                    <tr>
                        <td>Начальная цена (евро)</td>
                        <td><mark>≈ 500 000</mark></td>
                        <td>≈ 70 000</td>
                        <td>≈ 85 000</td>
                    </tr>
                </tbody>
                <tfoot>
                    <tr>
                        <td>Итоги</td>
                        <td>Самая дорогая и быстрая модель</td>
                        <td>Самая экологичная и доступная</td>
                        <td>Классический спортивный стиль</td>
                    </tr>
                </tfoot>
            </table>
        </div>
        
        <div class="car-details">
            <div class="car-card">
                <div class="car-images">
                    <img src="https://www.lamborghini.com/sites/it-en/files/DAM/lamborghini/0_facelift_2025/model_details/revuelto/gallery1-desktop.jpg" alt="Lamborghini Revuelto">
                </div>
                <div class="car-info">
                    <h3>Lamborghini Revuelto <span>Суперкар</span></h3>
                    <p>Revuelto глубоко чтит традиции Lamborghini и открывает новую эру также и в плане своего внешнего дизайна. В то время как силуэт автомобиля следует культовой единой центральной направляющей, четкие линии и плавные отрицательные радиусы создают хай-тек форму, благодаря которой Revuelto можно безошибочно отнести к новому поколению суперкаров Lamborghini. Культовый V-образный 12-цилиндровый двигатель очень хорошо заметен сзади.</p>
                    <a href="https://www.lamborghini.com/ru-en/модели/revuelto#val-ht" class="car-link" target="_blank">Официальный сайт</a>
                </div>
            </div>
            
            <div class="car-card">
                <div class="car-images">
                    <img src="https://www.major-voyah.ru/wp-content/uploads/2025/05/free-lg.webp" alt="Voyah Free">
                </div>
                <div class="car-info">
                    <h3>Voyah Free <span>Электромобиль</span></h3>
                    <p>Voyah Free — это полноразмерный люксовый кроссовер, выпускаемый китайской дочерней компанией Dongfeng под премиальным брендом Voyah, доступный как в полностью электрической (EV), так и в гибридной (E-REV) версиях. Автомобиль предлагает мощную динамику, полный привод, роскошный интерьер, пневматическую подвеску с регулируемым клиренсом и современные технологии, такие как адаптивный круиз-контроль, а также интегрированное мобильное приложение для управления функциями автомобиля.</p>
                    <a href="https://voyah.su/voyah-free" class="car-link" target="_blank">Официальный сайт</a>
                </div>
            </div>
            
            <div class="car-card">
                <div class="car-images">
                    <img src="https://www.allcarz.ru/wp-content/uploads/2016/01/foto-f-type-svr_01.jpg" alt="Jaguar F-Type">
                </div>
                <div class="car-info">
                    <h3>Jaguar F-Type <span>Спорткар</span></h3>
                    <p>Jaguar F-Type — это британский двухдверный двухместный спортивный автомобиль, выпускавшийся с 2013 по 2024 год, представляющий собой "духовного наследника" легендарного E-Type. Автомобиль предлагает динамику благодаря мощным двигателям V8 и 4-цилиндровым агрегатам, а также роскошный дизайн с плавными линиями кузова и алюминиевым кузовом. F-Type доступен в кузовах купе и кабриолет, с задним или полным приводом, и предлагает широкий диапазон характеристик, от 300 до 575 л.с., в зависимости от комплектации.</p>
                    <a href="https://www.jaguar.com/jaguar-range/f-type/index.html" class="car-link" target="_blank">Официальный сайт</a>
                </div>
            </div>
        </div>
        
        <footer>
            <p>© 2025 Сравнение автомобилей. Все права защищены.</p>
        </footer>
    </div>
</body>
</html>
