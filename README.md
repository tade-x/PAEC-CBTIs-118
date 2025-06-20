# PAEC-CBTIs-118
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>PAEC CBTis 118</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:opsz,wght@9..144,400;9..144,700&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after {
    box-sizing: border-box;
  }
  body {
    margin: 0;
    font-family: 'Montserrat', sans-serif;
    background: url('https://i.postimg.cc/pLZqsRfG/reciclaje.jpg') no-repeat center center fixed;
    background-size: cover;
    color: #233212;
    line-height: 1.7;
    font-weight: 400;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    scroll-behavior: smooth;
  }
  a {
    color: inherit;
    text-decoration: none;
    transition: color 0.25s ease;
  }
  a:focus-visible,
  button:focus-visible {
    outline: 3px solid #a1d56f;
    outline-offset: 2px;
  }
  header {
    position: relative;
    min-height: 520px;
    background-image: url('https://images.unsplash.com/photo-1564866657318-3fe3d8e67b94?auto=format&fit=crop&w=1600&q=90');
    background-attachment: fixed;
    background-position: center center;
    background-repeat: no-repeat;
    background-size: cover;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    color: #e8f0d6;
    padding: 2rem 1.5rem 3rem;
    gap: 1.4rem;
  }
  header::before {
    content: "";
    position: absolute;
    inset: 0;
    background: linear-gradient(180deg, rgba(29, 58, 12, 0.82) 20%, rgba(29, 58, 12, 0.95) 90%);
    z-index: 0;
  }
  header h1, header p {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    text-shadow:
      0 2px 5px rgba(0,0,0,0.35),
      0 0 10px rgba(0,0,0,0.15);
    opacity: 0;
    animation: fadeInUp 1s ease forwards;
  }
  header h1:first-child {
    font-size: clamp(2.75rem, 6vw, 3.8rem);
    margin-bottom: 0.3rem;
    animation-delay: 0.2s;
  }
  header h1:nth-child(2) {
    font-size: clamp(1.8rem, 3vw, 2.4rem);
    font-style: italic;
    margin-bottom: 1rem;
    font-weight: 600;
    animation-delay: 0.5s;
  }
  header p {
    font-size: clamp(1rem, 1.1vw, 1.25rem);
    font-weight: 400;
    line-height: 1.6;
    color: #d2dfb6;
    max-width: 820px;
    margin-bottom: 1rem;
    animation-delay: 0.8s;
  }
  nav {
    background: #1e4709;
    display: flex;
    justify-content: center;
    gap: 3.6rem;
    padding: 1.1rem 0;
    position: sticky;
    top: 0;
    z-index: 2000;
    box-shadow: 0 4px 12px rgba(0,0,0,0.14);
    user-select: none;
  }
  nav a {
    font-weight: 600;
    font-size: 1.1rem;
    color: #b6d68a;
    padding: 0.25rem 0;
    position: relative;
    transition: color 0.3s ease;
  }
  nav a::after {
    content: '';
    position: absolute;
    bottom: -6px;
    left: 50%;
    width: 0;
    height: 3px;
    background: #a3d15f;
    border-radius: 20px;
    transition: width 0.3s ease, left 0.3s ease;
  }
  nav a:hover,
  nav a:focus-visible {
    color: #e0f3a3;
  }
  nav a:hover::after,
  nav a:focus-visible::after {
    width: 40%;
    left: 30%;
  }
  .section {
    max-width: 1080px;
    margin: 4rem auto 5rem;
    padding: 0 1.5rem;
  }
  .section h2 {
    font-variation-settings: 'wght' 700, 'opsz' 14;
    font-size: 2.5rem;
    color: #4f7428;
    border-bottom: 3.5px solid #9dd160;
    padding-bottom: 0.35rem;
    margin-bottom: 2.2rem;
    letter-spacing: 0.04em;
    user-select: none;
    opacity: 0;
    animation: fadeIn 1s ease forwards;
  }
  .section:nth-of-type(1) h2 { animation-delay: 0.3s; }
  .section:nth-of-type(2) h2 { animation-delay: 0.5s; }
  .section:nth-of-type(3) h2 { animation-delay: 0.7s; }
  .section:nth-of-type(4) h2 { animation-delay: 0.9s; }
  .cards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    gap: 30px 28px;
  }
  .card {
    background: #fff;
    border-radius: 20px;
    padding: 2.2rem 2.6rem;
    box-shadow:
      0 9px 14px rgba(45, 54, 25, 0.12),
      0 3px 8px rgba(45, 54, 25, 0.08);
    transition:
      transform 0.35s cubic-bezier(0.22, 1, 0.36, 1),
      box-shadow 0.35s ease;
    cursor: default;
  }
  .card:hover,
  .card:focus-within {
    transform: perspective(650px) rotateX(2.5deg) rotateY(3deg) translateY(-7px);
    box-shadow:
      0 20px 40px rgba(45, 54, 25, 0.22),
      0 7px 18px rgba(45, 54, 25, 0.15);
    outline: none;
  }
  .card h3 {
    margin-top: 0;
    margin-bottom: 1.25rem;
    font-variation-settings: 'wght' 700, 'opsz' 14;
    font-size: 1.5rem;
    color: #2f4911;
    line-height: 1.15;
  }
  .card p {
    font-weight: 500;
    font-size: 1.05rem;
    color: #47592a;
    line-height: 1.6;
  }
  .gallery {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 1.7rem;
    justify-items: center;
    margin-top: 1rem;
  }
  .gallery img {
    width: 280px;
    height: 190px;
    object-fit: cover;
    border-radius: 16px;
    box-shadow:
      0 13px 26px rgba(50, 74, 20, 0.23),
      0 4px 10px rgba(50, 74, 20, 0.15);
    cursor: pointer;
    transition: transform 0.3s ease, box-shadow 0.3s ease;
    display: block;
  }
  .gallery img:hover,
  .gallery img:focus-visible {
    transform: scale(1.08);
    box-shadow:
      0 22px 42px rgba(50, 74, 20, 0.33),
      0 6px 18px rgba(50, 74, 20, 0.22);
    outline: none;
  }
  #equipo p {
    font-weight: 600;
    font-size: 1.1rem;
    max-width: 900px;
    margin: 0 auto;
    color: #3a5613;
    letter-spacing: 0.02em;
  }
  footer {
    background: #1e4709;
    color: #b9da7f;
    text-align: center;
    padding: 2.3rem 1.25rem;
    font-weight: 600;
    font-size: 1.05rem;
    border-top-left-radius: 30px;
    border-top-right-radius: 30px;
    box-shadow: inset 0 6px 14px rgba(255,255,255,0.08);
    user-select: none;
    letter-spacing: 0.02em;
  }
  .video-container {
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    overflow: hidden;
    max-width: 100%;
    border-radius: 16px;
    box-shadow:
      0 13px 26px rgba(50, 74, 20, 0.23),
      0 4px 10px rgba(50, 74, 20, 0.15);
    margin-top: 1rem;
  }
  .video-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: 0;
  }

  @keyframes fadeInUp {
    0% {
      opacity: 0;
      transform: translateY(15px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }
  @keyframes fadeIn {
    from {
      opacity: 0;
    }
    to {
      opacity: 1;
    }
  }

  @media (max-width: 768px) {
    header {
      min-height: 420px;
      padding: 1.5rem 1rem 2rem;
      gap: 1rem;
    }
    header h1:first-child {
      font-size: 2.6rem;
    }
    header h1:nth-child(2) {
      font-size: 1.6rem;
      margin-bottom: 1rem;
    }
    header p {
      font-size: 1rem;
      max-width: 90vw;
      margin-bottom: 0.85rem;
    }
    nav {
      gap: 2.5rem;
      padding: 0.8rem 0;
    }
    nav a {
      font-size: 1rem;
    }
    .section {
      margin: 3rem auto 4rem;
      padding: 0 1rem;
    }
    .section h2 {
      font-size: 2rem;
      margin-bottom: 1.8rem;
    }
    .card {
      padding: 1.8rem 2rem;
    }
    .gallery {
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    }
    .gallery img {
      width: 220px;
      height: 150px;
    }
  }
  @media (max-width: 400px) {
    header h1:first-child {
      font-size: 1.85rem;
    }
    header h1:nth-child(2) {
      font-size: 1.2rem;
    }
    header p {
      font-size: 0.9rem;
    }
  }
</style>
</head>
<body>
  <header>
    <h1>Separación Responsable de Residuos Sólidos</h1>
    <h1>y desarrollo de hábitos conscientes en el CBTis 118 y la comunidad</h1>
    <p>Separación responsable de residuos sólidos y desarrollo de hábitos conscientes de consumo en el CBTis 118 y la comunidad es un proyecto interdisciplinario cuyo objetivo general es promover la conciencia ecológica dentro y fuera del plantel educativo, mediante acciones concretas que fomenten la correcta separación de residuos y el consumo responsable.</p>
    <p>El propósito es fortalecer la educación ambiental en los estudiantes, integrando conocimientos de distintas asignaturas para generar un impacto real en su entorno inmediato. Se busca que cada participante reconozca su papel como agente de cambio, aplicando lo aprendido en contextos locales como su escuela, su colonia y su hogar.</p>
    <p>Entre los objetivos específicos se encuentra el sensibilizar a la comunidad educativa sobre el impacto ambiental de los residuos sólidos, fomentar hábitos de reciclaje, integrar conocimientos académicos con acciones comunitarias y difundir buenas prácticas ambientales en diferentes espacios.</p>
  </header>
  <nav>
    <a href="#asignaturas">Asignaturas</a>
    <a href="#entrevistas">Entrevistas</a>
    <a href="#equipo">Equipo</a>
  </nav>

  <section class="section" id="asignaturas">
    <h2>Asignaturas Integradas</h2>
    <div class="cards">
      <div class="card" tabindex="0">
        <h3>🔢 Pensamiento Matemático II</h3>
        <p>En esta asignatura se llevó a cabo una colecta de latas de aluminio, con el enfoque principal de no fomentar el consumo de bebidas enlatadas, sino la recolección consciente de aquellas latas que ya se encuentran tiradas en el entorno o separadas en casa como parte del reciclaje doméstico.Esta actividad permitió desarrollar habilidades matemáticas con una aplicación social y ambiental real, relacionando números con acciones concretas para el cuidado del planeta.</p>
        <div class="gallery" aria-label="Imágenes de Pensamiento Matemático II">
          <img src="https://i.postimg.cc/J4tpP96M/1da1c628-c38f-4472-815e-02387b6d7e12.jpg" alt="Imagen Matemáticas 1" tabindex="0" />
          <img src="https://i.postimg.cc/tgGDR7X4/ESC22-CAT-B-STATIS222.jpg" alt="Imagen Matemáticas 2" tabindex="0" />
        </div>
      </div>

      <div class="card" tabindex="0">
        <h3>📝 Lengua y Comunicación II</h3>
        <p>Desde esta materia, los alumnos elaboraron reseñas informativas y reflexivas sobre las actividades realizadas en el marco del proyecto. A través de la escritura, expresaron sus experiencias personales, valoraron el impacto de las acciones y argumentaron la importancia de generar un cambio de hábitos en la comunidad. Las reseñas también funcionaron como medios de difusión, redactadas con un lenguaje accesible y claro, para compartir con otras personas el sentido del proyecto. Se trabajaron habilidades de redacción, estructura textual, argumentación y comunicación escrita como herramientas para promover la conciencia ecológica desde una mirada crítica y humanista.</p>
        <div class="gallery" aria-label="Imágenes de Lengua y Comunicación">
          <img src="https://i.postimg.cc/4dwcTSS5/rese-a1.jpg" alt="Reseña 1" tabindex="0" />
          <img src="https://i.postimg.cc/HkQVgNJy/rese-a-2.jpg" alt="Reseña 2" tabindex="0" />
          </div>
      </div>

      <div class="card" tabindex="0">
        <h3>🌍 Inglés II</h3>
        <p>Como parte del componente bilingüe del proyecto, se realizó la rotulación en inglés y español de los contenedores de residuos ubicados en el CBTis 118. Esta actividad tuvo como finalidad mejorar la señalización para la correcta separación de desechos, a la vez que se fortalecían las competencias lingüísticas de los estudiantes. Cada contenedor fue etiquetado con términos como Plastic / Plástico, Paper / Papel, Organic Waste / Residuos Orgánicos, Glass / Vidrio, entre otros, promoviendo el aprendizaje contextual del idioma y la funcionalidad del vocabulario. Esto ayudó a facilitar el reciclaje y a involucrar a todos los miembros del plantel, independientemente de su dominio del idioma inglés.</p>
        <div class="gallery" aria-label="Imágenes de Inglés II">
          <img src="https://i.postimg.cc/NjFv8JTH/ingles.jpg" alt="Inglés Imagen 1" tabindex="0" />
          <img src="https://i.postimg.cc/8zYQZRBn/ingles-2.jpg" alt="Inglés Imagen 2" tabindex="0" />
        </div>
      </div>

      <div class="card" tabindex="0">
        <h3>🧠 Ciencias Sociales II</h3>
        <p>En esta asignatura, los estudiantes desarrollaron un podcast creativo e informativo con el objetivo de difundir conocimientos sobre el adecuado manejo de residuos sólidos. El podcast incluyó experiencias personales, entrevistas, reflexiones locales y propuestas de acción relacionadas con las problemáticas ambientales de su comunidad. Además de fomentar la producción mediática, este recurso permitió que los jóvenes ejercieran su ciudadanía de manera activa, analizando su realidad y proponiendo soluciones desde una mirada crítica y contextual. El proyecto también fortaleció su capacidad de comunicación oral y de trabajo colaborativo, integrando la tecnología como medio de transformación social.</p>
        
        <div class="video-container" aria-label="Video Ciencias Sociales">
          <iframe src="https://www.youtube.com/embed/MGMzkmf3F1Y" title="Video Ciencias Sociales" allowfullscreen></iframe>
        </div>
      </div>

      <div class="card" tabindex="0">
        <h3>🧪 Conservación de la Materia</h3>
        <p>El proyecto contempló la realización de un experimento para demostrar la ley de conservación de la materia, mostrando que la masa total permanece constante antes y después de una reacción química simple. Se utilizaron materiales reciclables para enfatizar la relación entre la ciencia y el cuidado ambiental, y se presentaron conclusiones. Este enfoque práctico acercó a los alumnos a la realidad ambiental y les permitió valorar la importancia del reciclaje y la conservación en un contexto experimental.</p>
        <div class="gallery" aria-label="Imágenes de Conservación de la Materia">
          <img src="https://i.postimg.cc/XvxNNGwf/quimica.jpg" alt="Experimento Conservación de la Materia 1" tabindex="0" />
          <img src="https://i.postimg.cc/FsGDVf76/Imagen-de-Whats-App-2025-06-15-a-las-20-16-40-49ea75cf.jpg" alt="Experimento Conservación de la Materia 2" tabindex="0" />
        </div>
      </div>

      <div class="card" tabindex="0">
        <h3>📢 Logística y Difusión</h3>
        <p>Como parte de las acciones de difusión y vinculación con la comunidad, se elaboraron carteles informativos sobre la correcta clasificación de los materiales reciclables, los cuales fueron colocados en puntos estratégicos del plantel. Estos carteles incluyeron imágenes, instrucciones y códigos de colores para facilitar la participación de todos. Se identificaron negocios que reciclan papel, cartón, plástico, metales y residuos orgánicos, lo cual abrió la posibilidad de establecer alianzas y rutas de reciclaje comunitarias. Esta sección del proyecto resaltó la importancia de la logística, la comunicación visual y la participación externa para lograr un impacto mayor y sostenido.</p>
        <div class="gallery" aria-label="Imágenes de Logística y Difusión">
          <img src="https://i.postimg.cc/x1fjBZjC/Imagen-de-Whats-App-2025-06-11-a-las-12-47-39-07037e00.jpg" alt="Imagen Logística 1" tabindex="0" />
          <img src="https://i.postimg.cc/6397Yxh0/logistica.jpg" alt="Imagen Logística 2" tabindex="0" />
        </div>
      </div>
    </div>
  </section>

  <section class="section" id="entrevistas">
    <h2>Entrevistas</h2>
    <div class="video-container" aria-label="Video entrevista">
      <iframe src="https://www.youtube.com/embed/GXCL7qouUvU" title="Video Entrevista" allowfullscreen></iframe>
    </div>
  </section>

  <section class="section" id="equipo">
    <h2>Equipo 4</h2>
    <p>IBARRA RESENDIZ KAROL NOELIA, MORALES GOMEZ CAMILA, RESENDIZ RAMOS MARIA GUADALUPE, TORRES RUIZ NAOMI y ZUÑIGA AVILES ALEJANDRO TADEO.</p>
  </section>

  <footer>
    <p>© 2025 CBTis 118 | Proyecto Interdisciplinario | Diseño por Equipo 4</p>
  </footer>
</body>
</html>
