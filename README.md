<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <link rel="stylesheet" href="main.css">
</head>
<body>
    
    <section class="container">
        <div class="content">
            <h1>Hi,</h1>
            <p>I am Samantha CHIU Yuen Sim.</p>
        </div>
    </section>

    <section class="container">
        <div class="content">
            <h1>Step 1</h1>
            <p>Start it like this..</p>
        </div>
    </section>

    <section class="container">
        <div class="content">
            <h1>Step 2</h1>
            <p>Start it like this..</p>
        </div>
    </section>

    <section class="container">
        <div class="content">
            <h1>Step 3</h1>
            <p>Start it like this..</p>
        </div>
    </section>

    <section class="container">
        <div class="content">
                <img src="hi.jpg" alt="hi">
            <h1>Step 4</h1>
            <p>Start it like this..</p>
        </div>
    </section>

    <div id="set-height"></div>

    <video id="v0" tabindex="0", autobuffer preload>
        <source type='video/mp4;codecs="avc1.42E01E, mp4a.40.2"' src="IMG_4774.MP4"></source>
    </video>
    <script src="sticky.js"></script>
    <script>

        enterView({
            selector: 'section',
            enter: function(el) {
                el.classList.add('entered');
            }
        })
    
        var frameNumber = 0, // start video at frame 0
        // lower numbers = faster playback
        playbackConst = 100, 
        // get page height from video duration
        setHeight = document.getElementById("set-height"), 
        // select video element         
        vid = document.getElementById('v0'); 
        // var vid = $('#v0')[0]; // jquery option

    // dynamically set the page height according to video length
    vid.addEventListener('loadedmetadata', function() {
    setHeight.style.height = Math.floor(vid.duration) * playbackConst + "px";
    });


    // Use requestAnimationFrame for smooth playback
    function scrollPlay(){  
    var frameNumber  = window.pageYOffset/playbackConst;
    vid.currentTime  = frameNumber;
    window.requestAnimationFrame(scrollPlay);
    }

    window.requestAnimationFrame(scrollPlay);
    
    </script>
</body>
</html>
