<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Samyak loves Anubha ❤️</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #1a202c;
            overflow: hidden;
            background-image: url('http://googleusercontent.com/file_content/uploaded:ChatGPT Image Aug 31, 2025, 07_20_44 PM.jpg-c6e14c5b-1961-4375-9078-a04df28f8ace');
            background-size: cover;
            background-position: center;
            background-repeat: no-repeat;
        }

        .heart {
            position: absolute;
            font-size: 2rem;
            color: #e91e63;
            animation: floatUp linear infinite;
            transform: translateY(0) scale(0);
            opacity: 0.5; /* Increased opacity to be more visible on the image */
        }

        @keyframes floatUp {
            0% {
                transform: translateY(0) scale(0);
                opacity: 0;
            }
            10% {
                transform: translateY(-50px) scale(1);
                opacity: 0.5;
            }
            100% {
                transform: translateY(-100vh) scale(1.5);
                opacity: 0;
            }
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
                text-shadow: 0 0 10px #ff69b4;
            }
            50% {
                transform: scale(1.05);
                text-shadow: 0 0 20px #ff69b4, 0 0 30px #ff69b4;
            }
        }

        .text-pulse {
            animation: pulse 2s infinite ease-in-out;
        }

        /* Responsive adjustments */
        @media (max-width: 768px) {
            .text-5xl {
                font-size: 3rem;
            }
        }
    </style>
</head>
<body class="flex items-center justify-center min-h-screen relative text-white">

    <!-- Floating hearts animation -->
    <div id="heart-container" class="absolute inset-0 z-10"></div>

    <div class="z-20 text-center px-4 py-8 bg-black bg-opacity-70 rounded-lg shadow-xl border-2 border-pink-500 max-w-lg mx-auto">
        <h1 class="text-3xl sm:text-5xl font-extrabold text-pink-500 mb-4 text-pulse">
            Samyak loves Anubha
        </h1>
        <p class="text-xl sm:text-2xl font-semibold text-gray-200">
            You are the most beautiful person in the world ❤️
        </p>
    </div>

    <script>
        // Custom function to show a pop-up message on page load
        function showSweetAlert() {
            Swal.fire({
                title: 'A message for you!',
                text: 'My love, this page is just a small reflection of the immense love I have for you. I hope it brings a smile to your beautiful face.',
                icon: 'success',
                confirmButtonText: 'You\'re the best!',
                confirmButtonColor: '#ff69b4',
                background: '#1a202c',
                color: '#fff',
                customClass: {
                    container: 'my-swal-container',
                    title: 'my-swal-title',
                    content: 'my-swal-content'
                },
                willOpen: () => {
                    const button = Swal.getConfirmButton();
                    if (button) {
                        button.addEventListener('mouseover', () => {
                            button.style.transform = 'scale(1.1)';
                            button.style.transition = 'transform 0.2s';
                        });
                        button.addEventListener('mouseout', () => {
                            button.style.transform = 'scale(1)';
                        });
                    }
                }
            });
        }

        window.onload = function() {
            showSweetAlert();
        };

        const heartContainer = document.getElementById('heart-container');
        const heartInterval = 300; // Milliseconds between new hearts

        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('heart');
            heart.innerHTML = '❤️';

            const size = Math.random() * 20 + 10;
            heart.style.fontSize = `${size}px`;

            const startPosition = Math.random() * 100;
            heart.style.left = `${startPosition}vw`;

            const animationDuration = Math.random() * 5 + 5;
            heart.style.animationDuration = `${animationDuration}s`;

            heartContainer.appendChild(heart);

            // Remove heart after animation ends to prevent memory leak
            heart.addEventListener('animationend', () => {
                heart.remove();
            });
        }

        setInterval(createHeart, heartInterval);
    </script>
</body>
</html>
