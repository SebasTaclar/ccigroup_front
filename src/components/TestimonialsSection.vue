<template>
  <section class="institutional-section" aria-labelledby="institutional-title">
    <div class="institutional-overlay"></div>
    <div class="institutional-content">
      <h2 id="institutional-title" class="institutional-title">Respaldo internacional para Colombia</h2>
      <p class="institutional-text">
        Globika hace parte de CCI Group, grupo con experiencia en soluciones lingüísticas y comunicación intercultural. Nuestra llegada a Colombia refleja una apuesta por ofrecer al mercado local servicios con visión global, estructura profesional y capacidad de adaptación a diferentes industrias y escenarios.
      </p>
      <p class="institutional-text1">
        Combinamos experiencia, procesos y enfoque de servicio para atender las necesidades del país con una propuesta sólida, confiable y cercana.
      </p>
      <div class="institutional-cta" role="region" aria-label="CTA intermedio">
        <h3 class="cta-title">¿Necesitas apoyo lingüístico<span class="rating-simbolos">?</span></h3>
        <p class="cta-desc">En Globika estamos listos para acompañarle con interpretación, traducción, notarización remota y soluciones multilingües adaptadas a su necesidad.</p>
        <div class="cta-buttons">
          <a href="#contact" class="cta-btn cta-primary arrow">Hablar con un asesor <span class="arrow">›</span></a>
          <a href="#contact" class="cta-btn cta-outline arrow">Solicitar servicio <span class="arrow">›</span></a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({ name: 'TestimonialsSection' })
</script>

<style scoped>
.institutional-section {
  position: relative;
  background: #f4f4f4;
  background-size: cover;
  background-position: center;
  color: #282828;
  padding: 50px clamp(20px, 5vw, 80px);
  min-height: 300px;
  display: flex;
  align-items: center;
}

.rating-simbolos{
  font-weight: 500;
  font-size: 35px;
}

.institutional-content {
  position: relative;
  z-index: 2;
  max-width: 1100px;
  margin: 0 0;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.institutional-title {
  font-size: clamp(22px, 3.6vw, 32px);
  font-weight: 400;
  margin: 0;
  color: #282828;
}

.institutional-text {
  color: #757575;
  font-size: clamp(14px, 1.6vw, 18px);
  line-height: 1.6;
  text-align: justify;
  font-weight: 450;
}

.institutional-text1 {
  color: #757575;
  font-size: clamp(14px, 1.6vw, 18px);
  line-height: 1.6;
  text-align: justify;
  font-weight: 450;
  margin-bottom: 30px;
}

.institutional-cta {
  margin-top: 18px;
  display: flex;
  flex-direction: column;
  gap: 12px;
  max-width: 780px;
}

.cta-title {
  color: #282828;
  font-size: clamp(18px, 2.2vw, 32px);
  margin: 0;
  font-weight: 400;
}

.cta-desc {
  color: #757575;
  margin: 0;
  font-size: 18px;
  font-weight: 450;
}

.cta-buttons {
  display: flex;
  gap: 12px;
  margin-top: 6px;
  flex-wrap: wrap;
}

.cta-btn {
  padding: 10px 18px;
  border-radius: 9999px;
  text-decoration: none;
  font-weight: 700;
  font-size: 14px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

.cta-primary {
  background: #be009f;
  color: #ffffff;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.cta-outline {
  /* estilo secundario: fondo blanco, texto negro, sombra */
  background: #be009f;
  color: #ffffff;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

/* Arrow animation */
.cta-btn .arrow {
  display: inline-block;
  margin-left: 8px;
  transition: transform 0.3s ease;
}

/* Hover / Focus: botón blanco con texto negro */
.cta-btn:hover,
.cta-btn:focus,
.cta-btn:focus-visible {
  background: #ffffff;
  color: #000000;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.12);
  transform: translateY(-2px);
}

.cta-btn:hover .arrow,
.cta-btn:focus .arrow,
.cta-btn:focus-visible .arrow {
  transform: translateX(4px);
  color: #000000;
}

.cta-btn:active {
  transform: translateY(-1px);
}

@media (max-width: 768px) {
  .institutional-section { padding: 48px 12px; }
  .institutional-content { padding: 0 8px; text-align: left; }
  .institutional-text,
  .institutional-text1 { text-align: justify; font-size: 16px;}
  .institutional-cta { align-items: flex-start; }
  .cta-buttons { flex-direction: column; width: 100%; }
  .cta-btn { width: 100%; padding: 12px 18px; }
  .cta-primary{font-size: 16px;}
  .cta-outline{font-size: 16px;}
  .cta-title { font-size: clamp(24px, 3.6vw, 24px); }
  .cta-desc { font-size: 16px; text-align: justify;}
  .institutional-title { font-size: clamp(24px, 3.6vw, 24px); }

}
</style>
