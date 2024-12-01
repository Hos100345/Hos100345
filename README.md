<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
    <meta charset="UTF-8">
    <title>ספירה לאחור ליום ההולדת של רבקה</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            direction: rtl;
            background-color: #FFE4E1;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        #countdown {
            font-size: 2.5em;
            color: #8B4513;
            background-color: white;
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 8px 16px rgba(0,0,0,0.2);
            text-align: center;
        }
        #message {
            margin-top: 20px;
            font-size: 1.5em;
            color: #FF69B4;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div>
        <div id="countdown"></div>
        <div id="message"></div>
    </div>

    <script>
        function calculateCountdown() {
            // חישוב התאריך עבור עוד 3 ימים
            const targetDate = new Date();
            targetDate.setDate(targetDate.getDate() + 3);

            const now = new Date();
            const difference = targetDate - now;

            const days = Math.floor(difference / (1000 * 60 * 60 * 24));
            const hours = Math.floor((difference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
            const minutes = Math.floor((difference % (1000 * 60 * 60)) / (1000 * 60));

            if (difference > 0) {
                document.getElementById('countdown').innerHTML = 
                    `${days} ימים, ${hours} שעות, ${minutes} דקות`;
                document.getElementById('message').innerHTML = '';
            } else {
                document.getElementById('countdown').innerHTML = '';
                document.getElementById('message').innerHTML = 
                    'יום הולדת שמח רבקה אהובה שלי! 🎂❤️';
            }
        }

        // עדכון מיידי וכל דקה
        calculateCountdown();
        setInterval(calculateCountdown, 1000);
    </script>
</body>
</html>
