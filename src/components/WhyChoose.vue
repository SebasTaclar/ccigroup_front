<template>
  <section class="why-section" aria-labelledby="why-title">
    <div class="why-overlay"></div>
    <div class="why-content">
      <h2 id="why-title" class="why-title">¿Por qué elegir Glóbika<span class="rating-simbolos">?</span></h2>
      <p class="why-intro">Porque entendemos que en muchos procesos una buena traducción o una interpretación correcta no es un detalle: es la diferencia entre avanzar con confianza o generar errores, retrasos y malentendidos.</p>

      <div class="differentials">
        <div class="diff-item">
          <h3>Experiencia internacional</h3>
          <p>Contamos con el respaldo y la visión de CCI Group, con trayectoria en servicios lingüísticos y operación en distintos mercados.</p>
        </div>

        <div class="diff-item">
          <h3>Adaptación a Colombia</h3>
          <p>Nuestra propuesta en el país responde a la realidad local, a sus instituciones, a sus dinámicas de negocio y a sus necesidades culturales y operativas.</p>
        </div>

        <div class="diff-item">
          <h3>Calidad y precisión</h3>
          <p>Trabajamos para que el mensaje se entienda de forma correcta, clara y profesional.</p>
        </div>

        <div class="diff-item">
          <h3>Acompañamiento cercano</h3>
          <p>No ofrecemos solo un servicio puntual; buscamos acompañar al cliente con orientación, respuesta y soluciones a la medida.</p>
        </div>

        <div class="diff-item">
          <h3>Confidencialidad y profesionalismo</h3>
          <p>Entendemos la sensibilidad de la información y la importancia de manejar cada proceso con responsabilidad.</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({ name: 'WhyChoose' })
</script>

<style scoped>
.why-section {
  position: relative;
  background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS37tX7yZB0BajGxHLidYOBOJSxqbMUG7tkIw&s');
  background-size: cover;
  background-position: center;
  color: #fff;
  padding: 80px 16px;
  min-height: 320px;
  display: flex;
  align-items: center;
}

.why-overlay {
   position: absolute;
  inset: 0;
   background: linear-gradient(
    251.52deg,
    rgba(170, 0, 166, 0.82) 4.31%,
    rgba(61, 0, 173, 0.80) 25.6%,
    rgba(0, 10, 172, 0.78) 47.51%,
    rgba(0, 5, 89, 0.84) 77.72%,
    rgba(0, 0, 0, 0.90) 98.63%
  );
  z-index: 2;
}

.why-content {
  position: relative;
  z-index: 2;
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.rating-simbolos {
  font-size: 38px;
  color: #ffffff;
  font-weight: 600;
}

.why-title {
  font-size: clamp(22px, 3.6vw, 32px);
  font-weight: 400;
  margin: 0;
  color: #ffffff;
}

.why-intro {
  color: rgba(255,255,255,0.95);
  font-size: clamp(14px, 1.6vw, 18px);
  margin: 0;
}

.differentials {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 18px 24px;
  margin-top: 12px;
}

.diff-item {
  background: rgba(255,255,255,0.04);
  padding: 16px;
  border-radius: 12px;
}

.diff-item h3 {
  margin: 0 0 6px 0;
  font-size: 16px;
  font-weight: 400;
  color: #ffffff;
}

.diff-item p {
  margin: 0;
  color: rgba(255,255,255,0.9);
  font-size: 15px;
  line-height: 1.5;
}

@media (max-width: 768px) {
  .why-section { padding: 48px 12px; }
  .differentials { grid-template-columns: 1fr; }
  .why-title { font-size: clamp(24px, 3.6vw, 24px); text-align: center; }
  .why-intro { text-align: center; font-size: 16px; }
}
</style>
