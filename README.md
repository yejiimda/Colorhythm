<!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Choose your color!</title>
    <style>
       @import url('https://fonts.googleapis.com/css2?family=Do+Hyeon&family=Gugi&family=Moirai+One&display=swap');
        
        body {
            margin: 0;
            padding: 0;
            font-family: "Moirai One", system-ui;
            background: linear-gradient(45deg, #FF9FF3, #FECA57, #96ffff, #a97dff);
            background-size: 400% 400%;
            animation: gradient 10s ease infinite;
            color: white;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            overflow: hidden;
            /* 여기에 트랜지션 효과 추가 - 배경 변경시 1.5초 동안 부드럽게 변경 */
            transition: background 20s ease;
        }
        
        @keyframes gradient {
            0% {
                background-position: 0% 50%;
            }
            50% {
                background-position: 100% 50%;
            }
            100% {
                background-position: 0% 50%;
            }
        }
        
        .splash-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            width: 100%;
            max-width: 1200px;
            padding: 0 20px;
        }
        
        .splash-title {
            font-size: 5rem;
            font-weight: bold;
            margin-bottom: 50px;
            text-shadow: 5px 5px 0px rgba(0, 0, 0, 0.3);
            letter-spacing: 2px;
            animation: bounce 2s ease infinite;
            color: #FFF;
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {transform: translateY(0);}
            40% {transform: translateY(-20px);}
            60% {transform: translateY(-10px);}
        }
        
        .color-options {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: nowrap;
            width: 100%;
            max-width: 960px;
        }
        
        .color-option {
            display: flex;
            flex-direction: column;
            align-items: center;
            cursor: pointer;
            transition: all 0.3s cubic-bezier(0.68, -0.55, 0.27, 1.55);
        }
        
        .color-icon {
            width: 100px;
            height: 100px;
            border-radius: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
            margin-bottom: 15px;
            position: relative;
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
            transform: rotate(-5deg);
        }
        
        .color-option:nth-child(even) .color-icon {
            transform: rotate(5deg);
        }
        
        .color-icon:before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            border-radius: 30px;
            opacity: 0;
            transition: all 0.4s ease;
            z-index: -1;
        }
        
        .color-name {
            font-size: 1.5rem;
            font-weight: 500;
            transition: all 0.3s ease;
            background-color: rgba(255, 255, 255, 0.2);
            padding: 5px 15px;
            border-radius: 20px;
            transform: scale(0.9);
        }
        
        /* Red */
        .red .color-icon {
            background: linear-gradient(145deg, #ff5252, #d32f2f);
            border: 4px solid #fff;
        }
        
        .red .color-icon:before {
            background: radial-gradient(circle, #ff8a80 0%, #c62828 100%);
        }
        
        .red:hover .color-icon {
            transform: scale(1.3) rotate(10deg);
            box-shadow: 0 15px 25px rgba(255, 82, 82, 0.6);
        }
        
        .red:hover .color-name {
            color: #ff5252;
            background-color: white;
            transform: scale(1.1);
        }
        
        body.red-bg {
            background: linear-gradient(45deg, #ff5252, #d32f2f);
            background-size: 400% 400%;
        }
        
        /* Blue */
        .blue .color-icon {
            background: linear-gradient(145deg, #448aff, #2962ff);
            border: 4px solid #fff;
        }
        
        .blue .color-icon:before {
            background: radial-gradient(circle, #82b1ff 0%, #2979ff 100%);
        }
        
        .blue:hover .color-icon {
            transform: scale(1.3) rotate(-10deg);
            box-shadow: 0 15px 25px rgba(68, 138, 255, 0.6);
        }
        
        .blue:hover .color-name {
            color: #448aff;
            background-color: white;
            transform: scale(1.1);
        }
        
        body.blue-bg {
            background: linear-gradient(45deg, #448aff, #2962ff);
            background-size: 400% 400%;
        }
        
        /* Green */
        .green .color-icon {
            background: linear-gradient(145deg, #69f0ae, #00c853);
            border: 4px solid #fff;
        }
        
        .green .color-icon:before {
            background: radial-gradient(circle, #b9f6ca 0%, #00e676 100%);
        }
        
        .green:hover .color-icon {
            transform: scale(1.3) rotate(10deg);
            box-shadow: 0 15px 25px rgba(105, 240, 174, 0.6);
        }
        
        .green:hover .color-name {
            color: #00c853;
            background-color: white;
            transform: scale(1.1);
        }
        
        body.green-bg {
            background: linear-gradient(45deg, #69f0ae, #00c853);
            background-size: 400% 400%;
        }
        
        /* Purple */
        .purple .color-icon {
            background: linear-gradient(145deg, #e040fb, #aa00ff);
            border: 4px solid #fff;
        }
        
        .purple .color-icon:before {
            background: radial-gradient(circle, #ea80fc 0%, #aa00ff 100%);
        }
        
        .purple:hover .color-icon {
            transform: scale(1.3) rotate(-10deg);
            box-shadow: 0 15px 25px rgba(224, 64, 251, 0.6);
        }
        
        .purple:hover .color-name {
            color: #aa00ff;
            background-color: white;
            transform: scale(1.1);
        }
        
        body.purple-bg {
            background: linear-gradient(45deg, #e040fb, #aa00ff);
            background-size: 400% 400%;
        }
        
        /* Yellow */
        .yellow .color-icon {
            background: linear-gradient(145deg, #ffeb3b, #ffc107);
            border: 4px solid #fff;
        }
        
        .yellow .color-icon:before {
            background: radial-gradient(circle, #fff9c4 0%, #ffd600 100%);
        }
        
        .yellow:hover .color-icon {
            transform: scale(1.3) rotate(10deg);
            box-shadow: 0 15px 25px rgba(255, 235, 59, 0.6);
        }
        
        .yellow:hover .color-name {
            color: #ffc107;
            background-color: white;
            transform: scale(1.1);
        }
        
        body.yellow-bg {
            background: linear-gradient(45deg, #ffeb3b, #ffc107);
            background-size: 400% 400%;
        }
        
        /* Pink */
        .pink .color-icon {
            background: linear-gradient(145deg, #ff80ab, #ec407a);
            border: 4px solid #fff;
        }
        
        .pink .color-icon:before {
            background: radial-gradient(circle, #ff80ab 0%, #c2185b 100%);
        }
        
        .pink:hover .color-icon {
            transform: scale(1.3) rotate(-10deg);
            box-shadow: 0 15px 25px rgba(255, 128, 171, 0.6);
        }
        
        .pink:hover .color-name {
            color: #ec407a;
            background-color: white;
            transform: scale(1.1);
        }
        
        body.pink-bg {
            background: linear-gradient(45deg, #ff80ab, #ec407a);
            background-size: 400% 400%;
        }
        
        .color-icon svg {
            width: 60%;
            height: 60%;
            fill: white;
            filter: drop-shadow(0 2px 3px rgba(0, 0, 0, 0.2));
            transition: all 0.3s ease;
            animation: wiggle 3s ease-in-out infinite;
        }
        
        @keyframes wiggle {
            0%, 100% { transform: rotate(0); }
            25% { transform: rotate(10deg); }
            75% { transform: rotate(-10deg); }
        }
        
        .color-option:hover .color-icon svg {
            filter: drop-shadow(0 0 5px rgba(255, 255, 255, 0.8));
            animation: spin 0.7s ease-in-out;
        }
        
        @keyframes spin {
            0% { transform: rotate(0); }
            100% { transform: rotate(360deg); }
        }
        
        .sparkle {
            position: absolute;
            width: 30px;
            height: 30px;
            background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='30' height='30' viewBox='0 0 24 24'%3E%3Cpath fill='%23FFFFFF' d='M12,1L9,9L1,12L9,15L12,23L15,15L23,12L15,9L12,1Z'/%3E%3C/svg%3E");
            background-repeat: no-repeat;
            pointer-events: none;
            z-index: 9999;
            opacity: 0;
        }
        
        .bubble {
            position: absolute;
            width: 20px;
            height: 20px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            animation: float 4s ease-in infinite;
            z-index: -1;
        }
        
        @keyframes float {
            0% {
                transform: translateY(0) scale(0);
                opacity: 0;
            }
            50% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) scale(1);
                opacity: 0;
            }
        }
        
        /* 배경 전환을 위한 그라데이션 오버레이 */
        .bg-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            opacity: 0;
            transition: opacity 1.5s ease;
            background-size: 400% 400%;
            animation: gradient 10s ease infinite;
        }
        
        .red-overlay {
            background: linear-gradient(45deg, #ff5252, #d32f2f);
        }
        
        .blue-overlay {
            background: linear-gradient(45deg, #448aff, #2962ff);
        }
        
        .green-overlay {
            background: linear-gradient(45deg, #69f0ae, #00c853);
        }
        
        .purple-overlay {
            background: linear-gradient(45deg, #e040fb, #aa00ff);
        }
        
        .yellow-overlay {
            background: linear-gradient(45deg, #ffeb3b, #ffc107);
        }
        
        .pink-overlay {
            background: linear-gradient(45deg, #ff80ab, #ec407a);
        }
        
        .bg-overlay.active {
            opacity: 1;
        }
        
        /* 반응형 디자인을 위한 미디어 쿼리 */
        @media (max-width: 960px) {
            .color-options {
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .color-option {
                margin: 10px;
            }
            
            .splash-title {
                font-size: 3.5rem;
            }
        }
        
        @media (max-width: 600px) {
            .color-icon {
                width: 80px;
                height: 80px;
            }
            
            .color-name {
                font-size: 1.2rem;
            }
            
            .splash-title {
                font-size: 2.5rem;
            }
        }
    </style>
</head>
<body>
    <!-- 배경 그라데이션 오버레이 추가 -->
    <div class="bg-overlay red-overlay" id="red-overlay"></div>
    <div class="bg-overlay blue-overlay" id="blue-overlay"></div>
    <div class="bg-overlay green-overlay" id="green-overlay"></div>
    <div class="bg-overlay purple-overlay" id="purple-overlay"></div>
    <div class="bg-overlay yellow-overlay" id="yellow-overlay"></div>
    <div class="bg-overlay pink-overlay" id="pink-overlay"></div>
    
    <!-- 배경 버블 효과 -->
    <script>
        document.addEventListener('DOMContentLoaded', function() {
            for (let i = 0; i < 20; i++) {
                createBubble();
            }
            
            function createBubble() {
                const bubble = document.createElement('div');
                bubble.classList.add('bubble');
                bubble.style.left = Math.random() * 100 + 'vw';
                bubble.style.animationDuration = Math.random() * 5 + 3 + 's';
                bubble.style.width = Math.random() * 30 + 10 + 'px';
                bubble.style.height = bubble.style.width;
                document.body.appendChild(bubble);
                
                setTimeout(() => {
                    bubble.remove();
                    createBubble();
                }, 8000);
            }
            
            // 마우스 이펙트
            document.addEventListener('mousemove', function(e) {
                if (Math.random() > 0.9) {
                    const sparkle = document.createElement('div');
                    sparkle.classList.add('sparkle');
                    sparkle.style.left = e.pageX + 'px';
                    sparkle.style.top = e.pageY + 'px';
                    document.body.appendChild(sparkle);
                    
                    gsapAnimate(sparkle);
                    
                    setTimeout(() => {
                        sparkle.remove();
                    }, 1000);
                }
            });
            
            function gsapAnimate(elem) {
                elem.style.transition = 'all 1s ease';
                elem.style.opacity = '1';
                elem.style.transform = 'scale(1.5) rotate(' + (Math.random() * 360) + 'deg)';
                
                setTimeout(() => {
                    elem.style.opacity = '0';
                    elem.style.transform = 'scale(0.2) rotate(' + (Math.random() * 360) + 'deg)';
                }, 300);
            }

            // 컬러 옵션 호버 시 배경 오버레이 변경 (서서히 변화)
            const colorOptions = document.querySelectorAll('.color-option');
            const overlays = document.querySelectorAll('.bg-overlay');
            
            // 초기화: 모든 오버레이 비활성화
            overlays.forEach(overlay => {
                overlay.classList.remove('active');
            });
            
            colorOptions.forEach(option => {
                option.addEventListener('mouseenter', function() {
                    const colorClass = this.classList[1];
                    const overlay = document.getElementById(colorClass + '-overlay');
                    
                    // 모든 오버레이 비활성화
                    overlays.forEach(o => {
                        o.classList.remove('active');
                    });
                    
                    // 선택된 오버레이만 활성화
                    overlay.classList.add('active');
                });
                
                option.addEventListener('mouseleave', function() {
                    // 마우스가 떠났을 때 모든 오버레이 비활성화
                    overlays.forEach(overlay => {
                        overlay.classList.remove('active');
                    });
                });
            });
        });
    </script>

    <div class="splash-container">
        <h1 class="splash-title">Choose your color!</h1>
        
        <div class="color-options">
            <div class="color-option red">
                <div class="color-icon">
                    <svg viewBox="0 0 24 24">
                        <path d="M12,21.35L10.55,20.03C5.4,15.36 2,12.27 2,8.5C2,5.41 4.42,3 7.5,3C9.24,3 10.91,3.81 12,5.08C13.09,3.81 14.76,3 16.5,3C19.58,3 22,5.41 22,8.5C22,12.27 18.6,15.36 13.45,20.03L12,21.35Z" />
                    </svg>
                </div>
                <span class="color-name">Black</span>
            </div>
            
            <div class="color-option blue">
                <div class="color-icon">
                    <svg viewBox="0 0 24 24">
                        <path d="M12,3C16.97,3 21,7.03 21,12C21,16.97 16.97,21 12,21C7.03,21 3,16.97 3,12C3,7.03 7.03,3 12,3M12,5C8.14,5 5,8.14 5,12C5,15.86 8.14,19 12,19C15.86,19 19,15.86 19,12C19,8.14 15.86,5 12,5M12,15.15C10.73,15.15 9.55,14.6 8.71,13.7C8.33,13.29 8.36,12.68 8.77,12.3C9.18,11.92 9.79,11.95 10.17,12.37C10.65,12.9 11.3,13.15 12,13.15C12.7,13.15 13.35,12.9 13.83,12.37C14.21,11.95 14.82,11.92 15.23,12.3C15.64,12.68 15.67,13.29 15.29,13.7C14.45,14.6 13.27,15.15 12,15.15M9,10C9.53,10 10,9.53 10,9C10,8.47 9.53,8 9,8C8.47,8 8,8.47 8,9C8,9.53 8.47,10 9,10M15,10C15.53,10 16,9.53 16,9C16,8.47 15.53,8 15,8C14.47,8 14,8.47 14,9C14,9.53 14.47,10 15,10Z" />
                    </svg>
                </div>
                <span class="color-name">Blue</span>
            </div>
            
            <div class="color-option green">
                <div class="color-icon">
                    <svg viewBox="0 0 24 24">
                        <path d="M17,8C8,10 5.9,16.17 3.82,21.34L5.71,22L6.66,19.7C7.14,19.87 7.64,20 8,20C19,20 22,3 22,3C21,5 14,5.25 9,6.25C4,7.25 2,11.5 2,13.5C2,15.5 3.75,17.25 3.75,17.25C7,8 17,8 17,8Z" />
                    </svg>
                </div>
                <span class="color-name">Green</span>
            </div>
            
            <div class="color-option purple">
                <div class="color-icon">
                    <svg viewBox="0 0 24 24">
                        <path d="M12,2A10,10 0 0,0 2,12A10,10 0 0,0 12,22A10,10 0 0,0 22,12A10,10 0 0,0 12,2M7.07,18.28C7.5,17.38 8.13,16.55 8.93,15.85C9.71,15.14 10.68,14.57 11.7,14.35C12.1,14.23 12.5,14.23 12.77,14.14C13.07,14.03 13.33,13.83 13.5,13.6C12.8,13.18 11.97,13 11.12,13C8.59,13 6.5,14.57 5.45,16.84C4.5,16 4,14.1 4,12C4,7.59 7.59,4 12,4C16.41,4 20,7.59 20,12C20,15.45 17.94,18.39 15,19.46C15.95,18.43 16.5,16.97 16.5,15.38C16.5,14.38 16.13,13.39 15.54,12.67C14.95,11.95 14.16,11.37 13.25,11.06C13.25,11.06 12.89,11.5 12,11.5C11.12,11.5 10.75,11.05 10.75,11.05C9.85,11.35 9.07,11.94 8.47,12.67C7.89,13.39 7.5,14.38 7.5,15.38C7.5,16.5 7.8,17.59 8.34,18.5C7.96,18.47 7.59,18.39 7.24,18.28L7.07,18.28Z" />
                    </svg>
                </div>
                <span class="color-name">Purple</span>
            </div>
            
            <div class="color-option yellow">
                <div class="color-icon">
                    <svg viewBox="0 0 24 24">
                        <path d="M12,7A5,5 0 0,1 17,12A5,5 0 0,1 12,17A5,5 0 0,1 7,12A5,5 0 0,1 12,7M12,9A3,3 0 0,0 9,12A3,3 0 0,0 12,15A3,3 0 0,0 15,12A3,3 0 0,0 12,9M12,2L14.39,5.42C13.65,5.15 12.84,5 12,5C11.16,5 10.35,5.15 9.61,5.42L12,2M3.34,7L7.5,6.65C6.9,7.16 6.36,7.78 5.94,8.5C5.5,9.24 5.25,10 5.11,10.79L3.34,7M3.36,17L5.12,13.23C5.26,14 5.53,14.78 5.95,15.5C6.37,16.24 6.91,16.86 7.5,17.37L3.36,17M20.65,7L18.88,10.79C18.74,10 18.47,9.23 18.05,8.5C17.63,7.78 17.1,7.15 16.5,6.64L20.65,7M20.64,17L16.5,17.36C17.09,16.85 17.62,16.22 18.04,15.5C18.46,14.77 18.73,14 18.87,13.21L20.64,17M12,22L9.59,18.56C10.33,18.83 11.14,19 12,19C12.82,19 13.63,18.83 14.37,18.56L12,22Z" />
                    </svg>
                </div>
                <span class="color-name">Yellow</span>
            </div>
            
            <div class="color-option pink">
                <div class="color-icon">
                    <svg viewBox="0 0 24 24">
                        <path d="M12,2C6.47,2 2,6.47 2,12C2,17.53 6.47,22 12,22A10,10 0 0,0 22,12C22,6.47 17.5,2 12,2M12,20A8,8 0 0,1 4,12A8,8 0 0,1 12,4A8,8 0 0,1 20,12A8,8 0 0,1 12,20M13,9.94L14.06,11L15.12,9.94L16.18,11L17.24,9.94L15.12,7.82L13,9.94M8.88,9.94L9.94,11L11,9.94L8.88,7.82L6.76,9.94L7.82,11L8.88,9.94M12,17.5C14.33,17.5 16.31,16.04 17.11,14H6.89C7.69,16.04 9.67,17.5 12,17.5Z" />
                    </svg>
                </div>
                <span class="color-name">Pink</span>
            </div>
        </div>
    </div>
</body>
</html>
