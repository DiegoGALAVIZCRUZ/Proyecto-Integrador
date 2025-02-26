<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Un Paso a la Programación Web</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://kit.fontawesome.com/a076d05399.js" crossorigin="anonymous"></script>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      font-family: 'Poppins', sans-serif;
    }
    h1, h2 {
      font-family: 'Playfair Display', serif;
    }
  </style>
</head>
<body class="bg-gray-100">
  <!-- Header -->
  <header class="bg-[#D85C47] text-white p-4 flex justify-between items-center">
    <h1 class="text-lg font-bold">Un Paso a la Programación Web</h1>
    <div class="flex gap-2 items-center">
      <div class="w-6 h-6 bg-white rounded-full"></div>
      <button onclick="toggleMenu()" class="text-white text-2xl">&#9776;</button>
    </div>
  </header>

  <!-- Menú de hamburguesa (oculto por defecto) -->
  <nav id="mobileMenu" class="hidden bg-[#D85C47] text-white p-4">
    <ul class="space-y-2">
      <li><a href="#" class="block">Inicio</a></li>
      <li><a href="#" class="block">Secciones</a></li>
      <li><a href="#" class="block">Videos</a></li>
      <li><a href="#" class="block">Ayuda</a></li>
    </ul>
  </nav>

  <!-- Barra de búsqueda -->
  <div class="p-4">
    <input type="text" placeholder="Buscar" class="w-full p-2 border border-[#B5A1C5] rounded-lg">
  </div>

  <!-- Carousel -->
  <div class="relative w-full max-w-lg mx-auto overflow-hidden">
    <div class="flex transition-transform duration-500 ease-in-out" id="carousel">
      <img src="https://anelis.com/wp-content/uploads/2009/12/diseno-programacion-web.jpg" class="w-full h-40 flex-shrink-0 rounded-lg" alt="Diseño y programación web">
      <img src="https://www.comunicare.es/wp-content/uploads/2021/02/diseno-y-desarrollo-web-senati-1800-x-1190.jpg" class="w-full h-40 flex-shrink-0 rounded-lg" alt="Diseño y desarrollo web">
      <img src="https://www.inesby.com/gallery/programacion-web-a-medida-ts1612178707.jpg?ts=1725352163" class="w-full h-40 flex-shrink-0 rounded-lg" alt="Programación web a medida">
    </div>
    <button onclick="prevSlide()" class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-gray-800 text-white p-2 rounded-full">&#10094;</button>
    <button onclick="nextSlide()" class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-gray-800 text-white p-2 rounded-full">&#10095;</button>
  </div>

  <!-- Texto de Bienvenida -->
  <section class="text-center p-6">
    <h2 class="text-xl font-bold text-gray-800">Imagina que descargas una nueva aplicación y no puedes encontrar cómo registrarte.</h2>
    <p class="mt-2 text-md text-gray-600">Te frustras y decides eliminarla. Pero, ¿qué pasó? Muchas veces, la falta de una interfaz clara y amigable puede hacer que una aplicación no tenga éxito.</p>
    <p class="mt-2 text-md text-gray-600">En nuestra plataforma, te enseñamos a crear experiencias digitales intuitivas y funcionales, desde los fundamentos de la programación hasta las mejores prácticas de diseño.</p>
    <button class="mt-4 bg-[#7289DA] text-white px-4 py-2 rounded-lg">Ver más</button>
  </section>

  <!-- Artículos Relacionados -->
  <div class="bg-[#2D3748] text-white p-4 text-center">
    <h2 class="text-lg font-bold">Artículos relacionados</h2>
    <div class="flex justify-center gap-4 py-4">
      <!-- Se añadió loading="eager" para que la imagen se cargue inmediatamente -->
      <img src="https://cdn.prod.website-files.com/5f5a53e153805db840dae2db/654e136987af46540ec90058_utilidad-programacion-equipos-diseno-p-800.webp" class="w-24 h-24 rounded-lg" alt="Utilidad en programación y equipos de diseño" loading="eager">
      <img src="https://www.nexeinformatica.com/wp-content/uploads/2019/05/Que-diferencia-hay-entre-desarrollo-web-y-diseno-web.jpg" class="w-24 h-24 rounded-lg" alt="Diferencia entre desarrollo web y diseño web" loading="eager">
    </div>
    <div class="flex justify-center gap-4">
      <button class="bg-[#7289DA] text-white px-4 py-2 rounded-lg">Ver más</button>
      <button class="bg-[#7289DA] text-white px-4 py-2 rounded-lg">Ver más</button>
    </div>
  </div>

  <script>
    // Funcionalidad del Carousel
    let index = 0;
    function showSlide() {
      const carousel = document.getElementById("carousel");
      carousel.style.transform = `translateX(${-index * 100}%)`;
    }
    function prevSlide() {
      const carousel = document.getElementById("carousel");
      index = (index > 0) ? index - 1 : carousel.children.length - 1;
      showSlide();
    }
    function nextSlide() {
      const carousel = document.getElementById("carousel");
      index = (index < carousel.children.length - 1) ? index + 1 : 0;
      showSlide();
    }
    setInterval(nextSlide, 3000); // Cambio automático cada 3 segundos

    // Funcionalidad del menú de hamburguesa
    function toggleMenu() {
      const menu = document.getElementById("mobileMenu");
      menu.classList.toggle("hidden");
    }
  </script>

  <!-- Footer -->
  <footer class="bg-[#D85C47] text-white p-4 text-center flex justify-between items-center">
    <div class="flex gap-4">
      <a href="#" class="text-white text-2xl"><i class="fab fa-facebook"></i></a>
      <a href="#" class="text-white text-2xl"><i class="fab fa-instagram"></i></a>
      <a href="#" class="text-white text-2xl"><i class="fab fa-x-twitter"></i></a>
      <a href="#" class="text-white text-2xl"><i class="fab fa-whatsapp"></i></a>
    </div>
    <span>&#8226;</span>
    <span>Contáctanos</span>
  </footer>
  <br>
</body>
</html>
