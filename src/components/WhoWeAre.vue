<template>
  <section class="who-section" aria-labelledby="who-title">
    <div class="who-overlay"></div>
    <div class="who-content">
      <h2 id="who-title" class="who-title">Globika en Colombia</h2>
      <p class="who-text">
        Globika es la operación para Colombia de una organización con trayectoria internacional en servicios lingüísticos. Como parte de CCI Group, llegamos al país con el objetivo de ofrecer soluciones profesionales de interpretación, traducción, notarización y apoyo multilingüe para diferentes sectores.
      </p>
      <p class="who-text who-text--lead">
        Nuestro enfoque combina experiencia operativa, estándares de calidad y entendimiento cultural para ayudar a que cada mensaje llegue de forma correcta, oportuna y profesional.
      </p>
      <p class="who-text">
        No solo traducimos palabras: facilitamos entendimiento, continuidad operativa y confianza entre las partes.
      </p>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({ name: 'WhoWeAre' })
</script>

<style scoped>
.who-section {
  position: relative;
  /* Imagen de fondo proporcionada por el usuario */
  background-image: url('https://www.translate.one/wp-content/uploads/Translations-for-Technology-1.webp');
  background-size: cover;
  background-position: center;
  color: #ffffff;
  padding: 80px 16px;
  min-height: 320px;
  display: flex;
  align-items: center;
}

.who-overlay {
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

.who-content {
  position: relative;
  z-index: 2;
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.who-title {
  font-size: clamp(22px, 3.6vw, 36px);
  font-weight: 400;
  margin: 0;
  color: #ffffff;
  font-size: 32px;
}

.who-text {
  color: rgba(255, 255, 255, 0.92);
  font-size: clamp(14px, 1.6vw, 18px);
  line-height: 1.6;
  margin: 0;
  text-align: justify;
  font-size: 18px;
}

.who-text--lead {
  font-weight: 600;
}

@media (max-width: 768px) {
  .who-section { padding: 48px 12px; }
  .who-content { padding: 0 8px; text-align: center; gap: 16px; align-items: center; }
  .who-text { text-align: center; font-size: 16px; }

  .who-title {
  font-size: clamp(24px, 3.6vw, 24px);
  font-weight: 400;
  margin: 0;
  color: #ffffff;
}
}
</style>
