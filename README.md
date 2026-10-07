<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>Abhishek | Pre Developer</title>

    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: Arial, sans-serif;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            background: #050816;
            color: white;
            overflow-x: hidden;
        }

        /* Animated background */
        body::before {
            content: "";
            position: fixed;
            width: 500px;
            height: 500px;
            background: #6c2cff;
            filter: blur(180px);
            opacity: .25;
            top: -150px;
            left: -150px;
            z-index: -1;
        }

        body::after {
            content: "";
            position: fixed;
            width: 450px;
            height: 450px;
            background: #00d9ff;
            filter: blur(180px);
            opacity: .18;
            bottom: -150px;
            right: -100px;
            z-index: -1;
        }

        /* Navbar */
        nav {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 20px 8%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: rgba(5, 8, 22, .65);
            backdrop-filter: blur(15px);
            z-index: 100;
        }

        .logo {
            font-size: 25px;
            font-weight: bold;
            color: #00eaff;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            color: white;
            text-decoration: none;
            transition: .3s;
        }

        nav a:hover {
            color: #00eaff;
            text-shadow: 0 0 15px #00eaff;
        }

        /* Hero */
        .hero {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            padding: 100px 20px;
        }

        .hero-content {
            animation: float 4s ease-in-out infinite;
        }

        .hero h1 {
            font-size: clamp(50px, 9vw, 100px);
            background: linear-gradient(90deg, #00eaff, #8c52ff, #ff3cac);
            -webkit-background-clip: text;
            color: transparent;
            margin-bottom: 15px;
        }

        .hero h2 {
            font-size: 30px;
            margin-bottom: 15px;
        }

        .hero p {
            color: #b7bfdc;
            font-size: 18px;
            max-width: 650px;
            margin: auto;
            line-height: 1.7;
        }

        .btn {
            display: inline-block;
            margin-top: 30px;
            padding: 14px 30px;
            border-radius: 30px;
            background: linear-gradient(90deg, #00d9ff, #7c3cff);
            color: white;
            text-decoration: none;
            font-weight: bold;
            transition: .4s;
            box-shadow: 0 0 25px rgba(0, 217, 255, .3);
        }

        .btn:hover {
            transform: translateY(-8px) scale(1.05);
            box-shadow: 0 0 40px #00d9ff;
        }

        /* Sections */
        section {
            padding: 100px 8%;
        }

        .title {
            text-align: center;
            font-size: 45px;
            margin-bottom: 60px;
        }

        .title span {
            color: #00eaff;
        }

        /* 3D Cards */
        .cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 30px;
            perspective: 1000px;
        }

        .card {
            padding: 35px 25px;
            background: rgba(255,255,255,.06);
            border: 1px solid rgba(255,255,255,.12);
            border-radius: 25px;
            text-align: center;
            backdrop-filter: blur(15px);
            transition: .5s;
            transform-style: preserve-3d;
        }

        .card:hover {
            transform: rotateX(8deg) rotateY(-8deg) translateY(-15px);
            border-color: #00eaff;
            box-shadow:
                0 20px 50px rgba(0,0,0,.5),
                0 0 25px rgba(0,234,255,.25);
        }

        .card .icon {
            font-size: 50px;
            margin-bottom: 20px;
        }

        .card h3 {
            font-size: 23px;
            margin-bottom: 12px;
        }

        .card p {
            color: #aeb6d3;
            line-height: 1.6;
        }

        /* About */
        .about {
            max-width: 900px;
            margin: auto;
            text-align: center;
        }

        .about p {
            font-size: 19px;
            color: #c1c7dc;
            line-height: 1.9;
        }

        /* Contact */
        .contact-box {
            max-width: 700px;
            margin: auto;
            padding: 45px;
            text-align: center;
            border-radius: 30px;
            background: rgba(255,255,255,.06);
            border: 1px solid rgba(255,255,255,.12);
            transition: .4s;
        }

        .contact-box:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 50px rgba(0,234,255,.15);
        }

        .socials {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .social {
            padding: 13px 22px;
            border-radius: 30px;
            background: #11172d;
            color: white;
            text-decoration: none;
            border: 1px solid #293150;
            transition: .3s;
        }

        .social:hover {
            transform: translateY(-6px) scale(1.05);
            border-color: #00eaff;
            color: #00eaff;
            box-shadow: 0 0 20px rgba(0,234,255,.3);
        }

        footer {
            text-align: center;
            padding: 30px;
            color: #777f9e;
            border-top: 1px solid rgba(255,255,255,.08);
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-15px);
            }
        }

        /* Mobile */
        @media(max-width: 700px) {
            nav {
                padding: 15px 5%;
            }

            nav ul {
                gap: 12px;
                font-size: 13px;
            }

            .hero h2 {
                font-size: 23px;
            }

            section {
                padding: 80px 5%;
            }

            .title {
                font-size: 35px;
            }
        }
    </style>
</head>

<body>

    <!-- NAVBAR -->
    <nav>
        <div class="logo">ABHISHEK.</div>

        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#gaming">Gaming</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>


    <!-- HERO -->
    <section class="hero" id="home">
        <div class="hero-content">

            <h1>ABHISHEK</h1>

            <h2>Pre Developer • Creator • Gamer</h2>

            <p>
                Welcome to my personal website.
                I love creating beautiful websites, 3D designs,
                animations and creative digital experiences.
            </p>

            <a href="#about" class="btn">
                Explore My World →
            </a>

        </div>
    </section>


    <!-- ABOUT -->
    <section id="about">

        <h2 class="title">About <span>Me</span></h2>

        <div class="about">

            <p>
                Hi! I am <b>Abhishek</b>, a passionate pre developer,
                Minecraft gamer and creative creator. I enjoy designing
                beautiful websites with modern animations, 3D effects
                and creative ideas.
            </p>

            <p>
                I am always learning new technologies and improving
                my skills to create better digital experiences.
            </p>

        </div>

    </section>


    <!-- SKILLS -->
    <section id="skills">

        <h2 class="title">My <span>Skills</span></h2>

        <div class="cards">

            <div class="card">
                <div class="icon">💻</div>
                <h3>Web Development</h3>
                <p>
                    Creating beautiful and modern websites
                    with creative designs.
                </p>
            </div>

            <div class="card">
                <div class="icon">🌐</div>
                <h3>3D Websites</h3>
                <p>
                    Building websites with 3D effects,
                    animations and interactive elements.
                </p>
            </div>

            <div class="card">
                <div class="icon">✨</div>
                <h3>Creative Design</h3>
                <p>
                    Designing unique and attractive digital
                    experiences.
                </p>
            </div>

            <div class="card">
                <div class="icon">🎬</div>
                <h3>YouTube</h3>
                <p>
                    Creating creative gaming and Minecraft
                    content.
                </p>
            </div>

        </div>

    </section>


    <!-- GAMING -->
    <section id="gaming">

        <h2 class="title">My <span>Gaming</span></h2>

        <div class="cards">

            <div class="card">

                <div class="icon">⛏️</div>

                <h3>Minecraft</h3>

                <p>
                    Minecraft is one of my favourite games.
                </p>

                <p style="margin-top:15px;">
                    <b>My Minecraft ID:</b><br>
                    smarty_piy2589
                </p>

            </div>

            <div class="card">

                <div class="icon">🎮</div>

                <h3>Gamer & Creator</h3>

                <p>
                    I enjoy gaming, creating videos and
                    sharing creative content.
                </p>

            </div>

        </div>

    </section>


    <!-- CONTACT -->
    <section id="contact">

        <h2 class="title">Contact <span>Me</span></h2>

        <div class="contact-box">

            <h2>Let's Connect 🚀</h2>

            <p style="margin-top:15px; color:#aeb6d3;">
                You can find me on YouTube and Instagram.
            </p>

            <div class="socials">

                <a class="social"
                   href="https://www.youtube.com/@Its_DarkGamerX"
                   target="_blank">
                    ▶ YouTube
                </a>

                <a class="social"
                   href="https://www.instagram.com/code_with_abhishek/"
                   target="_blank">
                    📸 Instagram
                </a>

                <a class="social"
                   href="mailto:as9834068404@mal.com">
                    ✉ Email
                </a>

            </div>

        </div>

    </section>


    <footer>
        © 2026 Abhishek • Pre Developer • Creator • Gamer
    </footer>


    <script>
        // 3D mouse movement effect
        const cards = document.querySelectorAll(".card");

        cards.forEach(card => {

            card.addEventListener("mousemove", e => {

                const rect = card.getBoundingClientRect();

                const x = e.clientX - rect.left;
                const y = e.clientY - rect.top;

                const centerX = rect.width / 2;
                const centerY = rect.height / 2;

                const rotateX =
                    ((y - centerY) / centerY) * -8;

                const rotateY =
                    ((x - centerX) / centerX) * 8;

                card.style.transform =
                    `rotateX(${rotateX}deg)
                     rotateY(${rotateY}deg)
                     translateY(-15px)`;
            });

            card.addEventListener("mouseleave", () => {
                card.style.transform =
                    "rotateX(0deg) rotateY(0deg) translateY(0)";
            });

        });
    </script>

</body>
</html>
