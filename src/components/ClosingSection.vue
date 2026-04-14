<template>
  <section class="closing-section" aria-labelledby="closing-title">
    <div class="closing-overlay"></div>
    <div class="closing-content">
      <h2 id="closing-title" class="closing-title">Conectamos idiomas<span class="rating-simbolos">.</span> Facilitamos entendimiento<span class="rating-simbolos">.</span> Impulsamos confianza<span class="rating-simbolos">.</span></h2>
      <p class="closing-text">En un entorno cada vez más global, la comunicación precisa ya no es opcional. En Glóbika trabajamos para que cada conversación, documento o interacción multilingüe se convierta en una oportunidad de entendimiento y avance.</p>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({ name: 'ClosingSection' })
</script>

<style scoped>
.closing-section {
  position: relative;
  background-image: url('https://www.idisc.com/hubfs/images/blog/Young%20creative%20business%20people%20with%20a%20globe%20in%20the%20office.jpeg');
  background-size: cover;
  background-position: center;
  color: #fff;
  padding: 90px clamp(20px, 5vw, 80px);
  min-height: 260px;
  display: flex;
  align-items: center;
}

.closing-overlay {
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

.closing-content {
  position: relative;
  z-index: 2;
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.closing-title {
  font-size: clamp(20px, 3.2vw, 32px);
  font-weight: 400;
  margin: 0;
}

.closing-text {
  color: rgba(255,255,255,0.92);
  font-size: clamp(14px, 1.6vw, 18px);
  line-height: 1.6;
  margin: 0;
  text-align: justify;
  font-weight: 400;
}

@media (max-width: 768px) {
  .closing-section { padding: 48px 12px; }
  .closing-content { padding: 0 8px; text-align: center; }
  .closing-text { text-align: center; font-size: 16px; }
  .closing-title { font-size: 24px; }
}
</style>
