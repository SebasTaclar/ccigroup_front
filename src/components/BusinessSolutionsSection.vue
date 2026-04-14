<template>
  <section class="business-solutions" aria-labelledby="business-title">
    <div class="business-container">
      <h2 id="business-title" class="business-title">Soluciones para organizaciones y personas</h2>
      <p class="business-text">
        Atendemos requerimientos de empresas, instituciones, organizaciones, profesionales y usuarios que necesitan servicios lingüísticos confiables para sus procesos, trámites, reuniones, eventos y documentación.
      </p>
      <p class="business-text business-text--commit">Nuestro compromiso es ofrecer una atención clara, profesional y alineada con cada necesidad.</p>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({ name: 'BusinessSolutionsSection' })
</script>

<style scoped>
.business-solutions {
  background: #f4f4f4; /* tono claro */
  color: #0f172a;
  padding: 40px clamp(20px, 5vw, 80px);
}
.business-container {
  max-width: 1100px;
  margin: 0 0;
  display: flex;
  flex-direction: column;
  gap: 12px;
}
.business-title {
  font-size: clamp(20px, 3.2vw, 32px);
  font-weight: 400;
  margin: 0;
  color: #282828;
}
.business-text {
  color: #757575;
  font-size: 16px;
  margin: 0;
  line-height: 1.6;
  font-size: 18px;
  font-weight: 400;
}
.business-text--commit {
  font-weight: 400;
}
@media (max-width: 768px) {
  .business-solutions { padding: 32px 12px; }
  .business-container { align-items: center; text-align: center; }
  .business-title { font-size: 24px; }
  .business-text { font-size: 16px; }
}
</style>
