<html lang="ro">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Modele 3D cu Limită de Activitate</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-image: url('fundal.jpg');
            background-size: cover;
            background-position: center;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            padding: 20px;
        }
        .model {
            margin-bottom: 20px;
            position: relative;
        }
        .model-name {
            color: #FFFFFF;
            margin-top: 10px;
        }
        .inactive {
            pointer-events: none;
            opacity: 0.5;
        }
    </style>
</head>
<body>

<div class="model active" id="model1" data-src="https://augmentedrealityweb.github.io/AF1/index.html">AirForce1</div>
<div class="model" id="model2" data-src="https://augmentedrealityweb.github.io/Chanel/index.html">Poșetă Chanel</div>
<div class="model" id="model3" data-src="https://augmentedrealityweb.github.io/Guler-Cervical/index.html">Guler Cervical</div>
<div class="model" id="model4" data-src="https://augmentedrealityweb.github.io/Jordan/index.html">AirJordan</div>
<div class="model" id="model5" data-src="https://augmentedrealityweb.github.io/Scaun-Ikea/index.html">Scaun Ikea</div>
<div class="model" id="model6" data-src="https://augmentedrealityweb.github.io/Nike/index.html">Nike Metcon 4</div>

<script>
    document.addEventListener("DOMContentLoaded", function() {
        const models = document.querySelectorAll('.model');

        function deactivateAllModels() {
            models.forEach(model => {
                const iframe = model.querySelector('iframe');
                if (iframe) {
                    // Salvează src într-un atribut de date și elimină src pentru a opri redarea
                    model.setAttribute('data-active-src', iframe.src);
                    iframe.src = '';
                }
                model.classList.add('inactive');
            });
        }

        models.forEach(model => {
            model.addEventListener('click', function() {
                deactivateAllModels();
                
                // Creați sau actualizați iframe-ul numai pentru modelul activat
                let iframe = model.querySelector('iframe');
                if (!iframe) {
                    iframe = document.createElement('iframe');
                    iframe.style.width = '200px';
                    iframe.style.height = '240px';
                    iframe.style.border = 'none';
                    iframe.style.borderRadius = '80px';
                    iframe.style.transform = 'scale(1)';
                    iframe.style.transformOrigin = '0 0';
                    iframe.style.overflow = 'hidden';
                    model.appendChild(iframe);
                }
                // Setează src din atributul de date pentru a reactiva redarea
                iframe.src = model.getAttribute('data-active-src') || model.getAttribute('data-src');
                
                model.classList.remove('inactive');
            });
        });

        // Inițial, dezactivează toate modelele
        deactivateAllModels();
        // Activează primul model
        models[0].click();
    });
</script>
</body>
