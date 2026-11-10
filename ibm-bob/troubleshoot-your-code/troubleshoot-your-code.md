
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Roast Toast Coast Cafe</title>

    <style>
        @font-face {
            font-family: 'Bogart';
            src: url('https://fonts.cdnfonts.com/s/24702/Bogart-Light.woff') format('woff');
            font-weight: normal;
            font-style: normal;
        }

        body {
            background-color: black;
            font-family: 'Bogart', sans-serif;
            margin: 0;
            padding: 0;
            display: grid;
            grid-template-columns: 1fr 1fr;
            min-height: 100vh;
        }

        .content {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .image-container {
            background-image: url('https://images.unsplash.com/photo-1514066558159-fc8c737ef259?q=80&w=2574&auto=format&fit=crop&ixlib=rb-4.0.3');
            background-size: cover;
            background-position: center;
            min-height: 100%;
        }

        .header-container {
            background-color: wheat;
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 15px;
            padding: 20px;
            margin-bottom: 20px;
            width: 90%;
            box-shadow: 0px 4px 15px rgba(0, 0, 0, 0.7);
            text-align: center;
        }

        header h1 {
            color: #663300;
            font-size: 3em;
            margin-bottom: 10px;
            line-height: 1.2;
        }

        header p {
            font-size: 1.3em;
            color: #333333;
            margin: 0;
        }

        .menu-section {
            background-color: #000000;
            color: #FFFFFF;
            padding: 10px;
            margin: 20px 0 20px 10%;
            width: 60%;
            border-radius: 10px;
            box-shadow: 0px 4px 10px rgba(189, 180, 180, 0.7);
            text-align: center;
        }

        .menu-section h2 {
            color: #FFCC00;
            font-size: 2em;
            margin-bottom: 20px;
        }

        .menu-toggle {
            background: none;
            border: none;
            color: #FFCC00;
            font-family: inherit;
            font-size: inherit;
            cursor: pointer;
        }

        .menu-toggle:hover {
            color: #FF9933;
        }

        .menu-toggle:focus-visible {
            outline: 2px solid white;
            outline-offset: 4px;
        }

        .menu-items {
            list-style-type: none;
            padding: 0;
            display: none;
        }

        .menu-items li {
            background-color: #222222;
            color: #F7F7F7;
            padding: 10px;
            border-radius: 5px;
            margin: 10px 0;
            text-align: center;
            font-size: 1.1em;
            box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.5);
        }

        @media (max-width: 768px) {
            body {
                grid-template-columns: 1fr;
            }

            .image-container {
                min-height: 300px;
                grid-row: 1;
            }

            .content {
                padding: 20px;
            }

            .menu-section {
                width: 80%;
                margin: 20px auto;
            }

            header h1 {
                font-size: 2em;
            }
        }
    </style>
</head>

<body>

    <div class="content">

        <div class="header-container">
            <h1>Welcome to the<br>Roast Toast Coast Cafe!</h1>
            <p>Where flavor meets the shore!</p>
        </div>

        <section class="menu-section">

            <h2>
                <button
                    class="menu-toggle"
                    type="button"
                    aria-expanded="false"
                    aria-controls="menu-items">
                    Our Menu
                </button>
            </h2>

            <ul class="menu-items" id="menu-items">
                <li>Breezy Brews</li>
                <li>Toasty Delights</li>
                <li>Coastal Bites</li>
                <li>Sunset Sips</li>
            </ul>

        </section>

    </div>

    <div class="image-container" role="img"
         aria-label="Cafe and food background image"></div>

    <script>
        function toggleMenuItems() {

            const menuItems = document.querySelector('.menu-items');
            const menuToggle = document.querySelector('.menu-toggle');

            const isVisible = menuItems.style.display === 'block';

            menuItems.style.display = isVisible ? 'none' : 'block';

            menuToggle.setAttribute(
                'aria-expanded',
                String(!isVisible)
            );
        }

        document.querySelector('.menu-toggle')
            .addEventListener('click', toggleMenuItems);
    </script>

</body>
</html>
