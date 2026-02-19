# Arzhel
Open it, you will love it
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Essay About My Teacher</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f2f6ff;
            margin: 0;
            padding: 0;
        }

        .container {
            max-width: 900px;
            margin: 40px auto;
            background: darkcyan;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(255, 0, 0, 0.516);
        }

        h1 {
            text-align: center;
            color: peachpuff;
            margin-bottom: 25px;
        }

        p {
            text-align: justify;
            line-height: 1.8;
            color: peachpuff;
            margin-bottom: 15px;
        }

        button {
            display: block;
            margin: 20px auto;
            padding: 10px 20px;
            background-color: paleturquoise;
            color: gray;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #3548b8;
        }

        #message {
            text-align: center;
            font-weight: bold;
            color: peachpuff;
        }

        /* Typing animation */
        .typing-text {
            font-family: "Courier New", Courier, monospace;
            font-weight: bold;
            color: peachpuff;
            border-right: 2px solid peachpuff;
            white-space: nowrap;
            overflow: hidden;
            display: inline-block;
            vertical-align: middle;
            padding-right: 5px;
            box-sizing: content-box;
        }

        @keyframes blink {
            50% { border-color: transparent; }
        }

        .typing-text { animation: blink 1s steps(1, end) infinite; }

        /* Floating pink hearts */
        .heart {
            position: absolute;
            width: 18px;
            height: 18px;
            background: rgb(236, 10, 176);
            transform: rotate(45deg);
            left: 50%;
            bottom: 0;
            pointer-events: none;
            opacity: 0.95;
            filter: drop-shadow(0 2px 6px rgba(0,0,0,0.15));
        }

        .heart::before,
        .heart::after {
            content: "";
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgb(236, 10, 176);
            border-radius: 50%;
            top: -50%;
            left: 0;
        }

        .heart::after {
            left: -50%;
            top: 0;
        }

        @keyframes floatUp {
            0% { transform: translateY(0) rotate(45deg); opacity: 1; }
            100% { transform: translateY(-140vh) rotate(45deg); opacity: 0; }
        }

        #hearts {
            position: fixed;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            overflow: visible;
            z-index: 1000;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>My Teacher: <span class="typing-text" data-text="Ma’am Kristin Ranyah"></span></h1>

        <p>
            A teacher plays a very important role in every student’s life. Teachers do not only
            teach lessons from books, but they also guide students to become better people.
            One teacher who truly made an impact on my life is my teacher, Ma’am Kristin Ranyah.
            She is a person who combines beauty, kindness, discipline, and dedication in her work.
        </p>

        <p>
            Ma’am Kristin Ranyah is beautiful not only in appearance but also in her character.
            She always comes to class with confidence and grace, making the classroom feel warm
            and welcoming. Her smile is one of the things students notice first. Whenever she smiles,
            it makes students feel comfortable and less afraid to participate in class discussions.
            Her smile shows how much she cares about her students and her profession.
        </p>

        <p>
            Aside from being beautiful, Ma’am Kristin is also very kind. She understands that students
            have different abilities and learning speeds. She patiently explains lessons until students
            can understand them. When students make mistakes, she does not embarrass them. Instead,
            she corrects them in a calm and respectful way, helping them learn from their errors.
        </p>

        <p>
            Although Ma’am Kristin is kind and always smiling, there are times when she becomes serious.
            Sometimes, she is strict because she wants her students to be disciplined and responsible.
            Her seriousness is not meant to scare students, but to teach them the importance of rules,
            respect, and hard work. She knows when to be gentle and when to be firm, which makes her
            a balanced and effective teacher.
        </p>

        <p>
            Ma’am Kristin believes that education is not just about memorizing lessons, but about
            developing good values. She encourages students to be confident, respectful, and hardworking.
            She motivates her students to always do their best and never give up, even when lessons
            become difficult.
        </p>

        <p>
            In conclusion, Ma’am Kristin Ranyah is a teacher who truly inspires her students.
            Her beauty, kindness, warm smile, and sometimes serious attitude all contribute to
            making her an excellent teacher. She teaches not only academic lessons, but also life
            lessons that students will carry with them in the future. I am thankful to have a teacher
            like Ma’am Kristin Ranyah, and I will always remember her positive influence on my life.
        </p>

        <button onclick="showMessage()">Click Me</button>
        <p id="message"></p>
    </div>

    <div id="hearts" aria-hidden="true"></div>

    <script>
        function showMessage() {
            document.getElementById("message").innerText =
                "Thank you, Ma’am Kristin Ranyah, for being a wonderful and inspiring teacher!";
            // burst of hearts
            for (let i = 0; i < 6; i++) setTimeout(createHeart, i * 80);
        }

        document.addEventListener("DOMContentLoaded", function() {
            const el = document.querySelector(".typing-text");
            if (el) {
                const text = el.dataset.text || el.textContent;
                el.textContent = "";
                let i = 0;
                function type() {
                    if (i <= text.length) {
                        el.textContent = text.slice(0, i);
                        i++;
                        setTimeout(type, 60 + Math.random() * 80);
                    } else {
                        setTimeout(() => { el.style.borderRight = "none"; }, 600);
                    }
                }
                type();
            }

            // occasional floating hearts
            setInterval(function() {
                createHeart();
            }, 1800);
        });

        function createHeart() {
            const container = document.getElementById("hearts");
            if (!container) return;
            const heart = document.createElement("div");
            heart.className = "heart";
            const size = 10 + Math.random() * 20;
            heart.style.width = size + "px";
            heart.style.height = size + "px";
            heart.style.left = Math.random() * 100 + "%";
            heart.style.bottom = "-30px";
            const duration = 3000 + Math.random() * 3000;
            heart.style.animation = `floatUp ${duration}ms linear forwards`;
            heart.style.opacity = (0.6 + Math.random() * 0.4).toFixed(2);
            heart.style.transform = `translateY(0) rotate(${Math.random()*40-20}deg) scale(${0.6 + Math.random()*0.8}) rotate(45deg)`;
            container.appendChild(heart);
            setTimeout(() => { heart.remove(); }, duration + 100);
        }
    </script>
</body>
</html>
