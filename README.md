<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Estev Music</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #191919; /* Gris oscuro del fondo */
            color: #fff;
            display: flex;
            flex-direction: column;
            align-items: center;
            height: auto; /* Ajusta la altura del cuerpo al contenido */
            overflow: auto; /* Habilita la barra de desplazamiento si es necesario */
            padding-bottom: 60px; /* Espacio adicional para el pie de página */
        }

        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            max-width: 1000px; /* Ancho más amplio para un diseño glamuroso */
            margin: 20px auto;
            background: linear-gradient(to bottom, #282828, #333); /* Degradado de gris oscuro */
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            transition: background-color 0.3s ease; /* Transición suave para el color de fondo */
            width: 100%; /* Ajusta el ancho del contenedor al 100% */
        }

        .container:hover {
            background: linear-gradient(to bottom, #333, #444); /* Degradado de gris oscuro más oscuro */
        }

        h1 {
            margin-bottom: 10px;
            text-align: center;
            color: #fff;
            font-size: 3em; /* Encabezado grande */
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5); /* Sombra de texto */
            transition: color 0.3s ease; /* Transición suave para el color del texto */
        }

        h1:hover {
            color: #29d47f; /* Gris claro al pasar el mouse */
        }

        .audio-player {
            width: 100%;
            margin-top: 20px;
            display: flex;
            flex-direction: column; /* Ordena el título y el reproductor */
            align-items: center;
            background: linear-gradient(to bottom, #333, #29d47f); /* Degradado de gris oscuro */
            padding: 10px;
            border-radius: 10px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2); /* Sombra */
            transition: background-color 0.3s ease; /* Transición suave para el color de fondo */
        }

        .audio-player:hover {
            background: linear-gradient(to bottom, #282828, #b128b1); /* Degradado de gris oscuro más claro */
        }

        .audio-player h2 {
            margin-bottom: 10px;
            color: #fff;
            text-align: center;
            font-size: 1.5em; /* Título de la canción más grande */
            transition: color 0.3s ease; /* Transición suave para el color del texto */
        }

        .audio-player h2:hover {
            color: #34b93a; /* Gris claro al pasar el mouse */
        }

        audio {
            width: 100%;
            max-width: 800px; /* Ancho más amplio para el reproductor */
            border-radius: 10px; /* Bordes redondeados */
            background-color: #282828; /* Gris oscuro para el reproductor */
            border: 2px solid #333; /* Borde gris oscuro */
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2); /* Sombra */
        }

        audio:hover {
            border: 2px solid #f0f0f0; /* Borde gris claro al pasar el mouse */
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.4); /* Sombra más fuerte al pasar el mouse */
        }

        .audio-player audio::-webkit-media-controls-panel {
            background-color: #282828; /* Gris oscuro para los controles */
            color: #fff; /* Color blanco para el texto */
        }

        .audio-player audio::-webkit-media-controls-play-button,
        .audio-player audio::-webkit-media-controls-pause-button {
            background-color: #f0f0f0; /* Gris claro para los botones */
            border-radius: 50%; /* Botones redondos */
            transition: background-color 0.3s ease; /* Transición suave para el color de fondo */
        }

        .audio-player audio::-webkit-media-controls-play-button:hover,
        .audio-player audio::-webkit-media-controls-pause-button:hover {
            background-color: #fff; /* Blanco al pasar el mouse */
        }

        .audio-player audio::-webkit-media-controls-volume-slider {
            background-color: #333; /* Gris oscuro para el control de volumen */
        }

        .audio-player audio::-webkit-media-controls-volume-slider-thumb {
            background-color: #fff; /* Blanco para el control de volumen */
            border-radius: 50%; /* Botón de volumen redondo */
            transition: background-color 0.3s ease; /* Transición suave para el color de fondo */
        }

        .audio-player audio::-webkit-media-controls-volume-slider-thumb:hover {
            background-color: #f0f0f0; /* Gris claro al pasar el mouse */
        }

        .biografia {
            margin-top: 30px;
            text-align: center;
            color: #fff;
            font-size: 1.2em;
            line-height: 1.6;
            transition: color 0.3s ease; /* Transición suave para el color del texto */
        }

        .biografia:hover {
            color: #f0f0f0; /* Gris claro al pasar el mouse */
        }

        /* Estilos para la sección de biografía */
        .biografia {
            margin-top: 30px;
            text-align: center;
            color: #fff;
            font-size: 1.2em;
            line-height: 1.6;
            transition: color 0.3s ease; /* Transición suave para el color del texto */
        }

        .biografia:hover {
            color: #f0f0f0; /* Gris claro al pasar el mouse */
        }

        .biografia p {
            color: #888; /* Gris claro para el texto de la biografía */
            margin-bottom: 15px; /* Espacio entre párrafos */
        }

        .biografia strong {
            color: #fff; /* Blanco para los elementos importantes */
        }

        /* Estilos para el pie de página */
        footer {
            background-color: #282828; /* Gris oscuro para el pie de página */
            padding: 20px;
            text-align: center;
            width: 100%;
            position: fixed; /* Fijar el pie de página al fondo */
            bottom: 0;
            left: 0;
        }

        footer p {
            color: #888; /* Gris claro para el texto del pie de página */
        }

        /* Estilos para dispositivos móviles */
        @media (max-width: 768px) {
            .container {
                padding: 10px;
                max-width: 90%; /* Ajusta el ancho del contenedor para dispositivos móviles */
            }

            h1 {
                font-size: 2em; /* Reduce el tamaño del encabezado para dispositivos móviles */
            }

            .audio-player h2 {
                font-size: 1.2em; /* Reduce el tamaño del título de la canción para dispositivos móviles */
            }

            .biografia {
                font-size: 1em; /* Reduce el tamaño del texto de la biografía para dispositivos móviles */
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Estev Music</h1>

        <div class="audio-player">
            <h2>Boli bol</h2>
            <audio controls>
                <source src="github.com/user-attachments/assets/c875c0aa-78dd-4f0d-ab28-fdd8f33624cc.mp4" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>

        <div class="audio-player">
            <h2>Macamequi</h2>
            <audio controls>
                <source src="Macamequi Master Pop, Master Sequoia Pop.mp3" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>

        <div class="audio-player">
            <h2>Mister Mario</h2>
            <audio controls>
                <source src="Mister Mario Master Pop, Master Sequoia Pop.mp3" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>

        <div class="audio-player">
            <h2>No Argentina</h2>
            <audio controls>
                <source src="No Argentina Master Pop, Master Sequoia Pop.mp3" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>

        <div class="audio-player">
            <h2>No quieres mi amor</h2>
            <audio controls>
                <source src="No quieres mi amor Master Pop, Master Sequoia Pop.mp3" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>

        <div class="audio-player">
            <h2>Oye tú ver al fin</h2>
            <audio controls>
                <source src="Oye tú ver al fin Master Pop, Master Sequoia Pop.mp3" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>

        <div class="audio-player">
            <h2>Salados</h2>
            <audio controls>
                <source src="Salados Master Pop, Master Sequoia Pop.mp3" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>

        <div class="audio-player">
            <h2>Santa Cecilia</h2>
            <audio controls>
                <source src="Santa Cecilia Master Pop, Master Sequoia Pop.mp3" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>

        <div class="audio-player">
            <h2>Thanks</h2>
            <audio controls>
                <source src="Thanks Master Pop, Master Sequoia Pop.mp3" type="audio/mpeg">
                Tu navegador no admite la reproducción de audio.
            </audio>
        </div>


        <!-- Agrega más reproductores de audio para las canciones de Estev -->

        <div class="biografia">
            <h2>Biografía</h2>
            <p>Nacido el <strong>11 de diciembre de 1999</strong> en <strong>San Martín de los Andes, provincia de Neuquén, Argentina</strong>, Estev es un artista único en su especie, un creador nato de música para el rock nacional argentino. Con más de <strong>2500 canciones</strong> en su haber, Estev es una fuerza creativa que no se detiene.</p>
            <p>Su pasión por la música comenzó desde muy joven. Aprendió a tocar la guitarra con una tabla de madera en la que dibujó cuerdas, practicando acordes de Fito Páez y Charly García. Este espíritu autodidacta lo llevó a formar parte de "Los Chalados de la Euritmia", una banda que le permitió desarrollar su talento y explorar su estilo musical.</p>
            <p>Luego de esta experiencia, Estev se embarcó en su carrera solista, creando canciones que han cautivado al público argentino. Su música es una mezcla de rock, pop y folclore, con letras profundas y melodías que se quedan grabadas en la memoria.</p>
            <p>Estev es un artista que ha nacido para crear música, un talento único que ha nacido en la Patagonia y que se ha convertido en un referente del rock nacional argentino.</p>
        </div>
    </div>

    <footer>
        <p>&copy; 2023 Estev Music. Todos los derechos reservados.</p>
    </footer>
</body>
</html>



