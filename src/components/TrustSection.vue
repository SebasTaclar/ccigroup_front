<template>
  <section class="trust-section" aria-labelledby="trust-title">
    <div class="trust-container">
      <h2 id="trust-title" class="trust-title">Experiencia global<span class="rating-simbolos">,</span> enfoque local<span class="rating-simbolos">.</span></h2>
      <p class="trust-text">
        En Globika conectamos idiomas, culturas y contextos. Acompañamos procesos donde la comunicación precisa es clave: reuniones, trámites, atención al cliente, procesos legales, entornos médicos, capacitaciones, eventos, documentos oficiales y operaciones empresariales
      </p>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({ name: 'TrustSection' })
</script>

<style scoped>
.trust-section {
  position: relative;
  background: #f3f4f6; /* tono claro gris */
  color: #0f172a;
  padding: 70px clamp(20px, 5vw, 80px);
}

.trust-container {
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 12px;
  align-items: center;
  text-align: center;
}
.trust-title {
  font-size: clamp(20px, 3.2vw, 28px);
  font-weight: 400;
  margin: 0;
  color: #282828;
  font-size: 32px;
}
.trust-text {
  font-size: 18px;
  margin: 0;
  color: #757575;
  line-height: 1.6;
  max-width: 900px;
  text-align: center;
}

.rating-simbolos{
  font-weight: 900;
  font-size: 28px;
}

@media (max-width: 768px) {
  .trust-section {
    padding: 32px 12px;
  }
}

@media (max-width: 480px) {
  .trust-section { padding: 28px 12px; }
  .trust-title { font-size: 24px; }
  .trust-text { font-size: 16px; max-width: 95%; }
}


</style>
