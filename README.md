<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Photo Slideshow</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: black;
    }
    .slideshow-container {
      position: relative;
      width: 100%;
      max-width: 800px;
      height: 450px;
      overflow: hidden;
    }
    .slide {
      position: absolute;
      width: 100%;
      height: 100%;
      opacity: 0;
      transition: opacity 1s ease-in-out;
    }
    .slide.active {
      opacity: 1;
    }
  </style>
</head>
<body>
  <div class="slideshow-container">
    <img src="photo1.jpg" alt="Photo 1" class="slide active">
    <img src="photo2.jpg" alt="Photo 2" class="slide">
    <img src="photo3.jpg" alt="Photo 3" class="slide">
  </div>

  <script>
    const slides = document.querySelectorAll('.slide');
    let currentIndex = 0;

    function showNextSlide() {
      slides[currentIndex].classList.remove('active');
      currentIndex = (currentIndex + 1) % slides.length;
      slides[currentIndex].classList.add('active');
    }

    setInterval(showNextSlide, 3000); // 每3秒切换一张照片
  </script>
</body>
</html>
