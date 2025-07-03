<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Моя страница Матрёшка RP</title>
    <style>
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }
        
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #e2c2ff 0%, #a18cd1 50%, #fbc2eb 100%);
            background-attachment: fixed;
            color: #4a2c82;
            text-align: center;
            padding: 20px;
            min-height: 100vh;
            margin: 0;
            overflow-x: hidden;
            line-height: 1.6;
        }
        
        .container {
            max-width: 800px;
            margin: 30px auto;
            background-color: rgba(255, 255, 255, 0.85);
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
            backdrop-filter: blur(5px);
            animation: fadeIn 0.8s ease-out;
            position: relative;
            z-index: 1;
            border: 1px solid rgba(255, 255, 255, 0.3);
            width: 95%;
        }
        
        h1 {
            color: #6a3093;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.1);
            margin-bottom: 20px;
            font-size: clamp(24px, 5vw, 32px);
        }
        
        .game-info {
            margin: 25px 0;
            padding: 20px;
            background-color: rgba(255, 255, 255, 0.7);
            border-radius: 15px;
            box-shadow: inset 0 0 10px rgba(0, 0, 0, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.5);
            font-size: clamp(16px, 3vw, 18px);
        }
        
        .social-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 25px 0;
            flex-wrap: wrap;
        }
        
        .social-button {
            display: inline-block;
            padding: 16px 30px;
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            font-size: clamp(16px, 3vw, 18px);
            flex: 1 1 200px;
            max-width: 250px;
        }
        
        .social-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
        }
        
        .youtube {
            background: linear-gradient(45deg, #ff0000, #cc0000);
        }
        
        .telegram {
            background: linear-gradient(45deg, #0088cc, #00aced);
        }
        
        .contact-link {
            display: inline-block;
            margin-top: 25px;
            padding: 16px 40px;
            background: linear-gradient(45deg, #8e44ad, #9b59b6);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            font-size: clamp(16px, 3vw, 18px);
            width: 80%;
            max-width: 350px;
        }
        
        .contact-link:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
            background: linear-gradient(45deg, #9b59b6, #8e44ad);
        }
        
        .play-button {
            display: inline-block;
            margin: 30px 0 20px;
            padding: 18px 40px;
            background: linear-gradient(45deg, #2ecc71, #27ae60);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
            animation: float 4s ease-in-out infinite;
            font-size: clamp(18px, 4vw, 22px);
            width: 90%;
            max-width: 400px;
        }
        
        .play-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
        }
        
        .avatar {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 20px;
            border: 4px solid rgba(255, 255, 255, 0.7);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            animation: fadeIn 1s ease-out, float 6s ease-in-out infinite;
        }
        
        .avatar:hover {
            transform: scale(1.05);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
        }
        
        .socials-title {
            font-size: clamp(20px, 4vw, 24px);
            margin: 40px 0 20px;
            color: #6a3093;
            font-weight: bold;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.1);
            position: relative;
            display: inline-block;
        }
        
        .socials-title::after {
            content: '';
            position: absolute;
            bottom: -8px;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 4px;
            background: linear-gradient(90deg, #9b59b6, #e2c2ff);
            border-radius: 3px;
        }
        
        /* Декоративные элементы */
        .decoration {
            position: fixed;
            opacity: 0.1;
            z-index: 0;
            display: none;
        }
        
        @media (min-width: 768px) {
            .decoration {
                display: block;
            }
            .social-button {
                padding: 18px 35px;
                font-size: 18px;
            }
            .play-button {
                padding: 20px 45px;
            }
            .contact-link {
                padding: 18px 45px;
                width: auto;
            }
        }
        
        .dec-1 {
            top: 10%;
            left: 5%;
            font-size: 100px;
            animation: float 8s ease-in-out infinite;
        }
        
        .dec-2 {
            bottom: 15%;
            right: 8%;
            font-size: 80px;
            animation: float 7s ease-in-out infinite 1s;
        }
        
        .dec-3 {
            top: 30%;
            right: 10%;
            font-size: 60px;
            animation: float 9s ease-in-out infinite 0.5s;
        }
    </style>
</head>
<body>
    <!-- Декоративные элементы (только для десктопов) -->
    <div class="decoration dec-1">✦</div>
    <div class="decoration dec-2">❀</div>
    <div class="decoration dec-3">✧</div>
    
    <div class="container">
        <!-- Замените ссылку на ваше фото -->
        <img src="https://via.placeholder.com/150" alt="Мой аватар" class="avatar">
        
        <h1>Привет! Я играю в Матрёшка RP</h1>
        
        <div class="game-info">
            <p>Присоединяйтесь ко мне в увлекательной игре Матрёшка RP! Здесь я создаю уникальные ролевые сюжеты и интересные истории.</p>
        </div>
        
        <!-- Кнопка "Начать играть" -->
        <a href="https://matrp.cc/CwTb6x" class="play-button">Начать играть со мной в Матрёшка RP</a>
        
        <!-- Подпись "Мои соцсети" -->
        <div class="socials-title">Мои соцсети</div>
        
        <div class="social-buttons">
            <!-- Замените ссылки на свои профили -->
            <a href="https://www.youtube.com/@DanyaVanichkin" class="social-button youtube">YouTube</a>
            <a href="https://t.me/Danya_Vanichkin" class="social-button telegram">Telegram</a>
        </div>
        
        <!-- Замените ссылку на ваш контактный Telegram -->
        <a href="https://t.me/MrrDanya" class="contact-link">Связаться со мной в Telegram</a>
    </div>
</body>
