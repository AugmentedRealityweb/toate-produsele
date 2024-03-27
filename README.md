<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modele AR Optimizate</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
            background-image: url('fundal.jpg');
            background-size: cover;
            background-position: center;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            align-items: flex-start;
            height: 100vh;
            overflow-y: auto;
        }
        .model {
            margin: 20px;
            text-align: center;
        }
        iframe {
            width: 200px;
            height: 240px;
            overflow: hidden;
            border: none;
            transform: scale(1);
            transform-origin: 0 0;
            margin-top: 10px;
            border-radius: 80px;
        }
        p {
            color: white;
        }
    </style>
</head>
<body>

<div class="model">
    <iframe data-src="https://augmentedrealityweb.github.io/AF1/index.html" class="lazy-load-iframe"></iframe>
    <p>AirForce1</p>
</div>

<div class="model">
    <iframe data-src="https://augmentedrealityweb.github.io/Chanel/index.html" class="lazy-load-iframe"></iframe>
    <p>Poșetă Chanel</p>
</div>

<div class="model">
    <iframe data-src="https://augmentedrealityweb.github.io/Guler-Cervical/index.html" class="lazy-load-iframe"></iframe>
    <p>Guler Cervical</p>
</div>

<div class="model">
    <iframe data-src="https://augmentedrealityweb.github.io/Jordan/index.html" class="lazy-load-iframe"></iframe>
    <p>AirJordan</p>
</div>

<div class="model">
    <iframe data-src="https://augmentedrealityweb.github.io/Scaun-Ikea/index.html" class="lazy-load-iframe"></iframe>
    <p>Scaun Ikea</p>
</div>

<div class="model">
    <iframe data-src="https://augmentedrealityweb.github.io/Nike/index.html" class="lazy-load-iframe"></iframe>
    <p>Nike Metcon 4</p>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if(entry.isIntersecting) {
        const iframe = entry.target;
        iframe.src = iframe.getAttribute('data-src');
        observer.unobserve(iframe);
      }
    });
  }, { rootMargin: '0px', threshold: 0.1 });

  document.querySelectorAll('.lazy-load-iframe').forEach(iframe => {
    observer.observe(iframe);
  });
});
</script>
</body>
