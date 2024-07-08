<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JARAW Coffee Shop</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.4/css/all.min.css" integrity="sha512-J+JUy1Us5tGptZHv7brWl3W8kma0g7vFbERp+Y3EiQO1nG0sWbh2O2hjDrW5Fk1+6QHXnDwuN/nDEfQggrm/9A==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <style>
        /* Reset default browser styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        /* Basic styling */
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            background-color: #f5f5f5; /* Light background */
            color: #333; /* Dark text color */
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .container {
            width: 80%;
            padding: 20px;
        }

        header {
            background-color: #8d6e63; /* Darker coffee color for header */
            color: #fff; /* White text color */
            padding: 20px 0;
            text-align: center;
            margin-bottom: 20px;
            width: 100%;
        }

        header h1 {
            font-size: 3rem;
            font-weight: bold;
            margin-bottom: 10px;
        }

        section {
            background-color: #fff; /* White background for sections */
            margin-bottom: 20px;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); /* Soft shadow */
            width: 100%;
            max-width: 800px;
            position: relative; /* Ensure coffee icon positioning relative to section */
        }

        section h2 {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: #333; /* Dark text color */
            text-align: center;
        }

        section p {
            font-size: 1.2rem;
            line-height: 1.8;
            color: #666; /* Lighter text color */
            text-align: justify;
        }

        .contact-info {
            font-weight: bold;
            color: #333; /* Dark text color */
        }

        footer {
            background-color: #8d6e63; /* Darker coffee color for footer */
            color: #fff; /* White text color */
            text-align: center;
            padding: 10px 0;
            width: 100%;
            position: fixed;
            bottom: 0;
        }

        /* Coffee icons styling */
        .coffee-icon {
            position: absolute;
            font-size: 50px;
            color: rgba(0, 0, 0, 0.1); /* Light coffee color for icons */
            pointer-events: none;
        }

        .coffee-icon-top {
            top: 10px;
            left: 10px;
        }

        .coffee-icon-side {
            top: 50%;
            transform: translateY(-50%);
            right: 10px;
        }

        .coffee-icon-bottom {
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
        }

        /* Responsive image styling */
        .coffee-images {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }

        .coffee-images img {
            width: 100%;
            max-width: 200px;
            height: auto;
            border-radius: 8px;
            box-shadow: 0 0 8px rgba(0, 0, 0, 0.2); /* Soft shadow */
        }

        /* Style for modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 9999;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.7);
            overflow: auto;
        }

        .modal-content {
            display: block;
            margin: 15% auto;
            width: 70%;
            max-width: 800px;
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
            cursor: pointer;
        }

        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>JARAW Coffee Shop</h1>
        </div>
    </header>

    <section id="about" class="container">
        <h2>About Us</h2>
        <p>At JARAW Coffee Shop, we're passionate about serving you the finest coffee experience. From carefully selected beans to expertly brewed beverages, we ensure every cup is crafted with love and precision.</p>
        <i class="fas fa-coffee coffee-icon coffee-icon-top"></i>
    </section>

    <section id="menu" class="container">
        <h2>Our Menu</h2>
        <p>Explore our diverse menu featuring a range of specialty coffees, teas, and delicious pastries. Whether you prefer a rich espresso or a soothing herbal tea, we have something to satisfy every palate.</p>
        <i class="fas fa-coffee coffee-icon coffee-icon-side"></i>
    </section>

    <section id="commitment" class="container">
        <h2>Our Commitment</h2>
        <p>We are committed to quality, sustainability, and community. Our beans are sourced responsibly, and we strive to minimize our environmental footprint. Join us in supporting local initiatives and enjoying exceptional coffee.</p>
        <i class="fas fa-coffee coffee-icon coffee-icon-bottom"></i>
    </section>

    <div class="container">
        <h2>More Coffee Moments</h2>
        <div class="coffee-images">
            <img src="https://i.imgur.com/gtao7xy.jpeg" alt="Coffee Cup 1">
            <img src="https://i.imgur.com/ohF33VB.jpeg" alt="Coffee Cup 2">
            <img src="https://i.imgur.com/BH0l38Q.jpeg" alt="Coffee Cup 3">
            <img src="https://i.imgur.com/BNvHlvY.jpeg" alt="Coffee Cup 4">
            <img src="https://i.imgur.com/psGiYnA.jpeg" alt="Coffee Cup 5">
        </div>
    </div>

    <section id="video" class="container">
        <h2>Watch Our Story</h2>
        <p>Click the video icon below to watch our journey and commitment to great coffee.</p>
        <i class="fas fa-video video-icon" onclick="openVideo('https://i.imgur.com/eWuRwvW.mp4')"></i>
    </section>

    <!-- Popup Video Modal -->
    <div id="videoModal" class="modal">
        <span class="close" onclick="closeVideo()">&times;</span>
        <video class="modal-content" controls>
            <source id="videoSource" src="" type="video/mp4">
            Your browser does not support HTML5 video.
        </video>
    </div>

    <footer>
        <div class="container">
            <p>&copy; 2024 JARAW Coffee Shop. All rights reserved.</p>
        </div>
    </footer>

    <script>
        // Function to open video modal
        function openVideo(videoURL) {
            var modal = document.getElementById('videoModal');
            var video = document.getElementById('videoSource');
            video.src = videoURL;
            modal.style.display = 'block';
        }

        // Function to close video modal
        function closeVideo() {
            var modal = document.getElementById('videoModal');
            var video = document.getElementById('videoSource');
            video.pause();
            video.currentTime = 0;
            modal.style.display = 'none';
        }
    </script>
</body>
</html>
