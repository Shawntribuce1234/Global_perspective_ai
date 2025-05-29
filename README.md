<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">]
    <meta name="author" content="Shawn Tribuce">
    <title>Global Perspective</title>
    <link rel="stylesheet" href="styles.css">
</head>
<styles>
  /* Page set up */
html, body {
    margin: 0;
    padding: 0;
    height: 100%;
    overflow-x: hidden;
    font-family: sans-serif;
}

/* Background video container */
.hero-section {
    width: 100vw;
    height: 100vh;
    overflow: hidden;
}

/* Video that fills the container*/
.hero-section video {
    width: 100%;
    height: auto;
    object-fit: contain;
    object-position: center;
    display: block; 
}

/* Content scroller */
.content {
    min-height: 100vh;
    padding-top: 1rem;
    padding-left: 1rem;
    padding-right: 1rem;
    display: flex;
    justify-content: flex-start;
    align-items: center;
    flex-direction: column;
}

/* Center Text */
.centered-text{ 
    font-weight: bold;
    color: gray;
    text-align: center;
    font-size: 2vw;
    margin: 0;

}

/* Design for the video section */
.scroll-video-section {
    background-color: white;
    padding: 1rem 1rem;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

/* Making a clean design */
.scroll-video-section video {
    max-width: 50%;
    width: 50%;
    height: auto;
    display: block;
    border-radius: 12px;
    

}

/* For section of image */
.image-section {
    background-color: white;
    padding: 2rem 2rem;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 50vh;
}

.image-section img {
    width: 40%;
    height: auto;
    max-width: 100%;

}

.wipe-up{ 
    opacity: 1;
    transform: translateY(50px);
    transition: all 1s ease-out;

}

.wipe-up.animate{
    opacity: 1;
    transform: translateY(0);
}

.small-image-section {
    background-color: white;
    padding: 2rem;
    display: flex;
    align-items: center;
    justify-content: center;

}

.small-image {
    max-width: auto;
    width: 50%;
    height: 50%;
    border-radius: 10px;

}
.image {
    max-width: auto;
    width: 50%;
    height: auto;
    border-radius: 10px;

}

.button-section {
    height: 30vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #808080;

}

.square-button {
    width: 400px;
    height: 150px;
    background-color: white;
    color: #808080;
    text-decoration: none;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 2rem;
    border-radius: 5px;
    text-align: center;
}
.square-button:hover {
    background-color: gray;

}
</styles>
<body>
    <div class="hero-section">
        <video autoplay muted loop playsinline>
            <source src="the_vid.mp4" type="video/mp4">
        </video>
    </div>
    <div class="small-image-section">
            <img src="the_dou.png" alt="the_title" class="image">
    </div>
    <div class="content">
        <div class="scroll-video-section">
            <video class="scroll-video" muted playsinline>
                <source src="us.mp4" type="video/mp4">
            </video>
        </div>
        <div class="scroll-video-section">
            <video class="scroll-video" muted playsinline>
                <source src="text.mp4" type="video/mp4">
            </video>
        </div>
        <div class="scroll-video-section">
            <video class="scroll-video" muted playsinline>
                <source src="scary_part.mp4" type="video/mp4">
            </video>
        </div>
    </div>
    <div>
        <div class="small-image-section">
            <img src="p5.png" alt="qoutes" class="small-image">
        </div>
        <div class="image-section">
            <img src="iphone.png" alt="iphone_template" class="wipe-up">
        </div>
    </div>
    <div class="button-section">
        <a href="www.apple.com" target="blank" class="square-button">
            Try Global Perspective AI
        </a>

    </div>



<script>
    const videos = document.querySelectorAll(".scroll-video");
    videos.forEach(video =>{
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                if (video.paused && video.currentTime === 0) {
                    video.play();
                }
            }
        });
    }, {
        thheshold: 0.5
    });
    observer.observe(video);
});

    const wipeImage = document.querySelector(".wipe-up");

    const imageObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                wipeImage.classList.add("animate");
            }
        });
    }, {
        threshold: 0.9
    });
    imageObserver.observe(wipeImage);

</script>
</body>
</html>
