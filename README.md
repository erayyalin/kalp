# kalp
,<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Senin İçin...</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            background-color: #1a1a1a;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            overflow: hidden;
        }
        .heart-container {
            cursor: pointer;
            transition: transform 0.3s;
            position: relative;
            z-index: 10;
        }
        .heart {
            background-color: #ff3366;
            width: 100px;
            height: 100px;
            position: relative;
            transform: rotate(-45deg);
            animation: heartbeat 1.2s infinite;
            box-shadow: 0 0 40px #ff3366;
        }
        .heart::before, .heart::after {
            content: "";
            background-color: #ff3366;
            border-radius: 50%;
            width: 100px;
            height: 100px;
            position: absolute;
        }
        .heart::before {
            top: -50px;
            left: 0;
        }
        .heart::after {
            top: 0;
            left: 50px;
        }
        @keyframes heartbeat {
            0% { transform: rotate(-45deg) scale(1); }
            14% { transform: rotate(-45deg) scale(1.3); }
            28% { transform: rotate(-45deg) scale(1); }
            42% { transform: rotate(-45deg) scale(1.3); }
            70% { transform: rotate(-45deg) scale(1); }
        }
        .instruction {
            color: white;
            margin-top: 60px;
            font-size: 1.2rem;
            letter-spacing: 2px;
            animation: fade 2s infinite;
        }
        @keyframes fade {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }
        .gallery {
            display: none;
            flex-wrap: wrap;
            justify-content: center;
            gap: 30px;
            padding: 20px;
            max-width: 900px;
            opacity: 0;
            transition: opacity 1.5s ease-in;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100%;
        }
        .photo {
            background: white;
            padding: 10px 10px 35px 10px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.8);
            transform: rotate(-5deg);
            transition: transform 0.4s ease;
        }
        .photo:nth-child(even) {
            transform: rotate(4deg);
        }
        .photo:nth-child(3n) {
            transform: rotate(-2deg);
        }
        .photo:hover {
            transform: scale(1.15) rotate(0deg);
            z-index: 20;
        }
        .photo img {
            width: 250px;
            height: 250px;
            object-fit: cover;
        }
        .message {
            width: 100%;
            text-align: center;
            color: #ff3366;
            font-size: 2.5rem;
            margin-bottom: 20px;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.5);
        }
    </style>
</head>
<body>

    <div class="heart-container" id="heartBtn" onclick="showSurprise()">
        <div class="heart"></div>
    </div>
    <div class="instruction" id="text">Kalbe Dokun</div>

    <div class="gallery" id="gallery">
        <div class="message">Seni Çok Seviyorum! ❤️</div>
        
        <div class="photo">
            <img src="FOTOGRAF_LINKI_1.jpg" alt="https://hizliresim.com/5cedtkwy">
        </div>
        <div class="photo">
            <img src="FOTOGRAF_LINKI_2.jpg" alt="https://hizliresim.com/fbizwh7x">
        </div>
        <div class="photo">
            <img src="FOTOGRAF_LINKI_3.jpg" alt="https://hizliresim.com/qpgg81fb">
        </div>
    </div>

    <script>
        function showSurprise() {
            document.getElementById('heartBtn').style.display = 'none';
            document.getElementById('text').style.display = 'none';
            
            const gallery = document.getElementById('gallery');
            gallery.style.display = 'flex';
            setTimeout(() => {
                gallery.style.opacity = '1';
            }, 100);
        }
    </script>
</body>
