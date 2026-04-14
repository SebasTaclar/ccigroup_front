<template>
  <section class="value-section" aria-labelledby="value-title">
    <div class="value-container">
      <h2 id="value-title" class="value-title">Más que un proveedor de idiomas<span class="rating-simbolos">,</span> un aliado estratégico</h2>
      <p class="value-intro">Ayudamos a organizaciones y personas a comunicarse de manera efectiva en escenarios donde la precisión importa.</p>

      <ul class="value-list" role="list">
        <li>Cobertura de servicios lingüísticos integrales</li>
        <li>Atención profesional y acompañamiento personalizado</li>
        <li>Capacidad para procesos presenciales, virtuales y remotos</li>
        <li>Enfoque en calidad, confidencialidad y oportunidad</li>
        <li>Adaptación al contexto cultural y operativo de Colombia</li>
        <li>Respaldo de experiencia internacional a través de CCI Group</li>
      </ul>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({ name: 'ValueSection' })
</script>

<style scoped>
.value-section {
  background: #f8fafc; /* tono claro */
  color: #0f172a;
  padding: 80px clamp(20px, 5vw, 80px);
}

.value-container {
  max-width: 1100px;
  margin: 0 0;
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.value-title {
  font-size: clamp(20px, 3.2vw, 28px);
  font-weight: 400;
  margin: 0;
  color: #282828;
}

.value-intro {
  color: #757575;
  font-size: 18px;
  margin: 0;
  font-weight: 500;
}

.value-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 12px 24px;
}

.value-list li {
  position: relative;
  padding-left: 28px;
  color: #757575;
  font-weight: 400;
}

.value-list li::before {
  content: "•";
  position: absolute;
  left: 0;
  top: 0;
  color: #be009f;
  font-size: 28px;
  line-height: 1;
}

.rating-simbolos{
  font-weight: 900;
  font-size: 28px;
}

@media (max-width: 768px) {
  .value-list { grid-template-columns: 1fr; }
  .value-section { padding: 32px 16px; }
  .value-container { align-items: center; text-align: left; }
  .value-title {    font-size: clamp(24px, 3.6vw, 24px);  }
  .value-intro { font-size: 16px; text-align: justify; }
}
</style>
