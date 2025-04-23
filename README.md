<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Responsive Webpage</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <nav class="navbar">
        <div class="logo">Logo</div>
        <ul class="nav-links">
            <li><a href="#">Home</a></li>
            <li><a href="#">About</a></li>
            <li><a href="#">Services</a></li>
            <li><a href="#">Contact</a></li>
        </ul>
        <div class="menu-toggle">☰</div>
    </nav>
    <div class="container">
        <header class="header">
            <h1>Welcome to Our Website</h1>
        </header>
        <main class="main-content">
            <section class="content">
                <h2>Main Content</h2>
                <p>This is the main content area. It adjusts based on screen size using CSS Grid and media queries.</p>
            </section>
            <aside class="sidebar">
                <h2>Sidebar</h2>
                <p>Additional information or links can go here.</p>
            </aside>
        </main>
        <footer class="footer">
            <p>&copy; 2025 Responsive Webpage. All rights reserved.</p>
        </footer>
    </div>
    <script>
        document.querySelector('.menu-toggle').addEventListener('click', () => {
            document.querySelector('.nav-links').classList.toggle('active');
        });
    </script>
</body>
</html>

/* Reset default styles */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Body styles */
body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
}

/* Navigation Bar (Flexbox) */
.navbar {
    background-color: #333;
    color: white;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1rem 2rem;
    position: sticky;
    top: 0;
    z-index: 100;
}

.navbar .logo {
    font-size: 1.5rem;
    font-weight: bold;
}

.nav-links {
    display: flex;
    list-style: none;
}

.nav-links li {
    margin-left: 2rem;
}

.nav-links a {
    color: white;
    text-decoration: none;
    font-size: 1rem;
}

.nav-links a:hover {
    color: #ddd;
}

.menu-toggle {
    display: none;
    font-size: 1.5rem;
    cursor: pointer;
}

/* Main Container (CSS Grid) */
.container {
    display: grid;
    grid-template-areas:
        "header"
        "main"
        "footer";
    grid-gap: 1rem;
    padding: 1rem;
    max-width: 1200px;
    margin: 0 auto;
}

.header {
    grid-area: header;
    background-color: #f4f4f4;
    padding: 2rem;
    text-align: center;
}

.main-content {
    grid-area: main;
    display: grid;
    grid-template-areas: "content sidebar";
    grid-template-columns: 2fr 1fr;
    grid-gap: 1rem;
}

.content {
    grid-area: content;
    background-color: #fff;
    padding: 1.5rem;
    border: 1px solid #ddd;
}

.sidebar {
    grid-area: sidebar;
    background-color: #f9f9f9;
    padding: 1.5rem;
    border: 1px solid #ddd;
}

.footer {
    grid-area: footer;
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1rem;
}

/* Media Queries */

/* Mobile (up to 600px) */
@media (max-width: 600px) {
    .navbar {
        flex-wrap: wrap;
    }

    .nav-links {
        display: none;
        width: 100%;
        flex-direction: column;
        align-items: center;
    }

    .nav-links.active {
        display: flex;
    }

    .nav-links li {
        margin: 0.5rem 0;
    }

    .menu-toggle {
        display: block;
    }

    .main-content {
        grid-template-areas:
            "content"
            "sidebar";
        grid-template-columns: 1fr;
    }

    .container {
        padding: 0.5rem;
    }
}

/* Tablet (601px to 768px) */
@media (min-width: 601px) and (max-width: 768px) {
    .navbar {
        flex-wrap: wrap;
    }

    .nav-links {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
    }

    .nav-links li {
        margin: 0.5rem 1rem;
    }

    .menu-toggle {
        display: none;
    }

    .main-content {
        grid-template-areas:
            "content"
            "sidebar";
        grid-template-columns: 1fr;
    }
}

/* Desktop (769px and above) */
@media (min-width: 769px) {
    .nav-links {
        display: flex;
    }

    .menu-toggle {
        display: none;
    }

    .main-content {
        grid-template-areas: "content sidebar";
        grid-template-columns: 2fr 1fr;
    }
}
