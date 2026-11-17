<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="theme-color" content="#0b1020">
    <meta name="description" content="Mark Dave's portfolio — aspiring software developer building useful digital experiences.">
    <title>Mark Dave — Developer Portfolio</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            color-scheme: dark;
            --bg: #0b1020;
            --surface: #111a2e;
            --surface-raised: #151f35;
            --text: #f3f6ff;
            --muted: #a4afc5;
            --accent: #70e1d1;
            --accent-strong: #b6a4ff;
            --line: rgba(192, 207, 238, .13);
            --page-width: 1080px;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        html {
            scroll-behavior: smooth;
            scroll-padding-top: 90px;
        }

        body {
            min-width: 320px;
            background:
                radial-gradient(ellipse at 82% 14%, rgba(84, 76, 158, .17), transparent 31rem),
                radial-gradient(ellipse at 8% 50%, rgba(47, 145, 137, .1), transparent 28rem),
                var(--bg);
            color: var(--text);
            font-family: "DM Sans", sans-serif;
            line-height: 1.65;
        }

        a {
            color: inherit;
        }

        a:focus-visible {
            outline: 3px solid var(--accent);
            outline-offset: 4px;
        }

        .container {
            width: min(var(--page-width), calc(100% - 48px));
            margin-inline: auto;
        }

        .skip-link {
            position: fixed;
            z-index: 10;
            top: 12px;
            left: 12px;
            padding: 10px 16px;
            transform: translateY(-160%);
            border-radius: 8px;
            background: var(--accent);
            color: #0b1020;
            font-weight: 700;
        }

        .skip-link:focus {
            transform: translateY(0);
        }

        .site-header {
            position: sticky;
            z-index: 5;
            top: 0;
            border-bottom: 1px solid var(--line);
            background: rgba(11, 16, 32, .82);
            backdrop-filter: blur(18px);
        }

        nav {
            display: flex;
            min-height: 76px;
            align-items: center;
            justify-content: space-between;
            gap: 24px;
        }

        .logo {
            color: var(--text);
            font-family: "Space Grotesk", sans-serif;
            font-size: 1.25rem;
            font-weight: 700;
            letter-spacing: -.05em;
            text-decoration: none;
        }

        .logo span {
            color: var(--accent);
        }

        nav ul {
            display: flex;
            flex-wrap: wrap;
            justify-content: flex-end;
            gap: 8px 26px;
            list-style: none;
        }

        nav ul a {
            color: var(--muted);
            font-size: .92rem;
            text-decoration: none;
            transition: color .2s ease;
        }

        nav ul a:hover {
            color: var(--accent);
        }

        .hero {
            display: grid;
            min-height: min(760px, calc(100svh - 76px));
            grid-template-columns: minmax(0, 1.15fr) minmax(280px, .85fr);
            align-items: center;
            gap: 56px;
            padding-block: 96px;
        }

        .eyebrow {
            display: inline-flex;
            align-items: center;
            gap: 9px;
            color: var(--accent);
            font-size: .78rem;
            font-weight: 700;
            letter-spacing: .14em;
            text-transform: uppercase;
        }

        .eyebrow::before {
            width: 7px;
            height: 7px;
            border-radius: 50%;
            background: currentColor;
            content: "";
            box-shadow: 0 0 14px currentColor;
        }

        h1, h2, h3 {
            font-family: "Space Grotesk", sans-serif;
            line-height: 1.15;
        }

        .hero h1 {
            max-width: 680px;
            margin-top: 22px;
            font-size: clamp(3rem, 7vw, 5.7rem);
            letter-spacing: -.075em;
        }

        .hero h1 span {
            color: var(--accent);
        }

        .hero-copy {
            max-width: 570px;
            margin-top: 24px;
            color: var(--muted);
            font-size: clamp(1rem, 2vw, 1.13rem);
        }

        .hero-actions {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            gap: 14px;
            margin-top: 34px;
        }

        .button {
            display: inline-flex;
            min-height: 48px;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 0 20px;
            border: 1px solid transparent;
            border-radius: 10px;
            background: var(--accent);
            color: #0b1020;
            font-weight: 700;
            text-decoration: none;
            transition: transform .2s ease, background .2s ease;
        }

        .button:hover {
            transform: translateY(-2px);
            background: #91eee0;
        }

        .button-secondary {
            border-color: var(--line);
            background: transparent;
            color: var(--text);
        }

        .button-secondary:hover {
            background: rgba(255, 255, 255, .06);
        }

        .hero-art {
            position: relative;
            display: grid;
            min-height: 360px;
            place-items: center;
            overflow: clip;
        }

        .orbit {
            position: absolute;
            width: min(340px, 80vw);
            aspect-ratio: 1;
            border: 1px solid rgba(182, 164, 255, .22);
            border-radius: 50%;
            transform: rotate(-24deg) scaleY(.65);
        }

        .orbit::before,
        .orbit::after {
            position: absolute;
            width: 11px;
            height: 11px;
            border-radius: 50%;
            content: "";
        }

        .orbit::before {
            top: 13%;
            left: 16%;
            background: var(--accent);
            box-shadow: 0 0 22px var(--accent);
        }

        .orbit::after {
            right: 12%;
            bottom: 18%;
            background: var(--accent-strong);
            box-shadow: 0 0 22px var(--accent-strong);
        }

        .monogram {
            display: grid;
            width: 210px;
            aspect-ratio: 1;
            place-items: center;
            border: 1px solid rgba(255, 255, 255, .2);
            border-radius: 36% 64% 57% 43% / 43% 38% 62% 57%;
            background: linear-gradient(145deg, rgba(112, 225, 209, .2), rgba(182, 164, 255, .23));
            box-shadow: 0 24px 90px rgba(112, 225, 209, .12), inset 0 0 48px rgba(255, 255, 255, .05);
            color: var(--text);
            font-family: "Space Grotesk", sans-serif;
            font-size: 5rem;
            font-weight: 700;
            letter-spacing: -.09em;
            transform: rotate(-8deg);
        }

        section {
            padding-block: 92px;
        }

        .section-heading {
            max-width: 650px;
            margin-bottom: 38px;
        }

        .section-heading h2 {
            margin-top: 12px;
            font-size: clamp(2rem, 4vw, 3rem);
            letter-spacing: -.055em;
        }

        .section-heading p {
            margin-top: 12px;
            color: var(--muted);
        }

        .about-panel,
        .skill-card,
        .project-card,
        .contact-panel {
            border: 1px solid var(--line);
            background: linear-gradient(145deg, rgba(21, 31, 53, .88), rgba(17, 26, 46, .75));
            box-shadow: 0 18px 60px rgba(0, 0, 0, .12);
        }

        .about-panel {
            max-width: 820px;
            padding: clamp(24px, 5vw, 42px);
            border-radius: 18px;
            color: var(--muted);
            font-size: 1.05rem;
        }

        .skills {
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 14px;
        }

        .skill-card {
            display: flex;
            min-height: 92px;
            align-items: center;
            gap: 15px;
            padding: 20px;
            border-radius: 14px;
            transition: transform .2s ease, border-color .2s ease;
        }

        .skill-card:hover,
        .project-card:hover {
            transform: translateY(-4px);
            border-color: rgba(112, 225, 209, .42);
        }

        .skill-mark {
            display: grid;
            width: 42px;
            height: 42px;
            flex: 0 0 auto;
            place-items: center;
            border-radius: 12px;
            background: rgba(112, 225, 209, .1);
            color: var(--accent);
            font-family: "Space Grotesk", sans-serif;
            font-size: .85rem;
            font-weight: 700;
        }

        .skill-card h3 {
            font-size: 1rem;
        }

        .projects {
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 18px;
        }

        .project-card {
            overflow: hidden;
            border-radius: 16px;
            transition: transform .2s ease, border-color .2s ease;
        }

        .project-preview {
            display: grid;
            min-height: 166px;
            place-items: center;
            overflow: hidden;
            background:
                radial-gradient(circle at 50% 50%, rgba(112, 225, 209, .2), transparent 40%),
                linear-gradient(135deg, #182840, #1d1a3b);
        }

        .project-card:nth-child(2) .project-preview {
            background:
                radial-gradient(circle at 50% 50%, rgba(255, 190, 117, .2), transparent 40%),
                linear-gradient(135deg, #28243b, #1b2b40);
        }

        .project-card:nth-child(3) .project-preview {
            background:
                radial-gradient(circle at 50% 50%, rgba(182, 164, 255, .24), transparent 40%),
                linear-gradient(135deg, #202244, #172f3b);
        }

        .preview-symbol {
            color: rgba(243, 246, 255, .92);
            font-family: "Space Grotesk", sans-serif;
            font-size: 3rem;
            font-weight: 600;
            letter-spacing: -.08em;
        }

        .project-content {
            padding: 22px;
        }

        .project-content h3 {
            font-size: 1.2rem;
        }

        .project-content p {
            min-height: 52px;
            margin-top: 9px;
            color: var(--muted);
            font-size: .93rem;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-top: 18px;
            list-style: none;
        }

        .project-tags li {
            padding: 4px 9px;
            border: 1px solid var(--line);
            border-radius: 99px;
            color: #c5cce0;
            font-size: .75rem;
        }

        .contact-panel {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 30px;
            padding: clamp(24px, 5vw, 44px);
            border-radius: 18px;
        }

        .contact-panel h3 {
            font-size: clamp(1.45rem, 3vw, 2rem);
            letter-spacing: -.04em;
        }

        .contact-panel p {
            max-width: 510px;
            margin-top: 10px;
            color: var(--muted);
        }

        footer {
            padding-block: 26px;
            border-top: 1px solid var(--line);
            color: var(--muted);
            font-size: .9rem;
        }

        .footer-inner {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 10px 24px;
        }

        @media (max-width: 760px) {
            .hero {
                min-height: auto;
                grid-template-columns: 1fr;
                gap: 8px;
                padding-block: 82px 56px;
            }

            .hero-art {
                min-height: 280px;
                grid-row: 1;
            }

            .monogram {
                width: 165px;
                font-size: 4rem;
            }

            .orbit {
                width: 270px;
            }

            .hero-copy {
                max-width: 640px;
            }

            .skills {
                grid-template-columns: repeat(2, minmax(0, 1fr));
            }

            .projects {
                grid-template-columns: 1fr;
            }

            .project-content p {
                min-height: 0;
            }

            section {
                padding-block: 68px;
            }
        }

        @media (max-width: 520px) {
            .container {
                width: min(var(--page-width), calc(100% - 32px));
            }

            nav {
                min-height: 68px;
                align-items: flex-start;
                flex-direction: column;
                justify-content: center;
                gap: 8px;
                padding-block: 12px;
            }

            nav ul {
                justify-content: flex-start;
                gap: 4px 18px;
            }

            nav ul a {
                font-size: .84rem;
            }

            .hero {
                padding-top: 50px;
            }

            .hero h1 {
                font-size: clamp(2.8rem, 15vw, 4rem);
            }

            .hero-actions {
                align-items: stretch;
                flex-direction: column;
            }

            .button {
                width: 100%;
            }

            .skills {
                gap: 10px;
            }

            .skill-card {
                min-height: 82px;
                gap: 10px;
                padding: 14px 12px;
            }

            .skill-mark {
                width: 36px;
                height: 36px;
                font-size: .75rem;
            }

            .skill-card h3 {
                font-size: .9rem;
            }

            .contact-panel {
                align-items: stretch;
                flex-direction: column;
            }
        }

        @media (prefers-reduced-motion: reduce) {
            *,
            *::before,
            *::after {
                scroll-behavior: auto !important;
                transition-duration: .01ms !important;
            }
        }
    </style>
</head>
<body>
    <a class="skip-link" href="#main">Skip to content</a>
    <header class="site-header">
        <nav class="container" aria-label="Main navigation">
            <a class="logo" href="#home" aria-label="Mark Dave, home">MD<span>.</span></a>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main id="main">
        <div class="container">
            <section class="hero" id="home" aria-labelledby="hero-title">
                <div>
                    <p class="eyebrow">Aspiring software developer</p>
                    <h1 id="hero-title">Hello, I'm <span>Mark Dave.</span></h1>
                    <p class="hero-copy">
                        I build modern websites and applications with a focus on thoughtful design,
                        clear experiences, and solving real-world problems.
                    </p>
                    <div class="hero-actions">
                        <a class="button" href="#projects">Explore my work <span aria-hidden="true">↓</span></a>
                        <a class="button button-secondary" href="#contact">Get in touch</a>
                    </div>
                </div>
                <div class="hero-art" aria-hidden="true">
                    <div class="orbit"></div>
                    <div class="monogram">MD</div>
                </div>
            </section>

            <section id="about" aria-labelledby="about-title">
                <div class="section-heading">
                    <p class="eyebrow">A little about me</p>
                    <h2 id="about-title">Curious by nature.<br>Developer by choice.</h2>
                </div>
                <div class="about-panel">
                    <p>
                        I'm a passionate developer dedicated to creating clean, responsive, and
                        user-friendly applications. I continuously learn new technologies and enjoy
                        turning ideas into practical digital experiences.
                    </p>
                </div>
            </section>

            <section id="skills" aria-labelledby="skills-title">
                <div class="section-heading">
                    <p class="eyebrow">Tools I use</p>
                    <h2 id="skills-title">My skills</h2>
                    <p>A growing toolkit for designing, building, and shipping for the web.</p>
                </div>
                <div class="skills">
                    <article class="skill-card"><span class="skill-mark" aria-hidden="true">H5</span><h3>HTML5</h3></article>
                    <article class="skill-card"><span class="skill-mark" aria-hidden="true">C3</span><h3>CSS3</h3></article>
                    <article class="skill-card"><span class="skill-mark" aria-hidden="true">JS</span><h3>JavaScript</h3></article>
                    <article class="skill-card"><span class="skill-mark" aria-hidden="true">Py</span><h3>Python</h3></article>
                    <article class="skill-card"><span class="skill-mark" aria-hidden="true">Git</span><h3>Git</h3></article>
                    <article class="skill-card"><span class="skill-mark" aria-hidden="true">GH</span><h3>GitHub</h3></article>
                </div>
            </section>

            <section id="projects" aria-labelledby="projects-title">
                <div class="section-heading">
                    <p class="eyebrow">Selected work</p>
                    <h2 id="projects-title">Projects</h2>
                    <p>A few things I've been building and exploring.</p>
                </div>
                <div class="projects">
                    <article class="project-card">
                        <div class="project-preview" aria-hidden="true"><span class="preview-symbol">&lt;/&gt;</span></div>
                        <div class="project-content">
                            <h3>Portfolio Website</h3>
                            <p>A personal website to introduce my work, skills, and approach.</p>
                            <ul class="project-tags" aria-label="Technologies"><li>HTML</li><li>CSS</li><li>Responsive</li></ul>
                        </div>
                    </article>
                </div>
            </section>

            <section id="contact" aria-labelledby="contact-title">
                <div class="contact-panel">
                    <div>
                        <p class="eyebrow">Have a project in mind?</p>
                        <h3 id="contact-title">Let's build something useful.</h3>
                        <p>I'd love to hear about your idea, collaborate, or just talk about technology.</p>
                    </div>
                    <a class="button" href="mailto:your@email.com">Email me <span aria-hidden="true">↗</span></a>
                </div>
            </section>
        </div>
    </main>

    <footer>
        <div class="container footer-inner">
            <p>© 2026 Mark Dave. All rights reserved.</p>
            <a href="https://github.com/yourusername">GitHub <span aria-hidden="true">↗</span></a>
        </div>
    </footer>
</body>
</html>
