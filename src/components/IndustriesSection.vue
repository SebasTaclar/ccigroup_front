<template>
  <section class="industries-section">
    <div class="container">
      <div class="industries-layout">
        <div class="copy-column">

          <h2 class="section-title">Sectores que atendemos</h2>
          <p class="section-subtitle">
            Nuestros servicios pueden adaptarse a diferentes industrias y entornos donde la comunicación clara y profesional es fundamental.
          </p>

          <div class="industries-lists">
            <ul class="industry-list" v-for="(column, cIndex) in industryColumns" :key="cIndex">
              <li v-for="(industry, index) in column" :key="index">
                <span class="bullet"></span>
                <span class="industry-label">{{ industry }}</span>
              </li>
            </ul>
          </div>

          <p class="section-subtitle1">
            Cada sector tiene su propio lenguaje, sus propios procesos y su propio nivel de exigencia. Por eso adaptamos cada servicio al contexto operativo, cultural y profesional de cada interacción.
          </p>

          <!-- <button class="view-all-btn" type="button">
            <span>Vea todas las industrias</span>
            <i class="fas fa-arrow-right"></i>
          </button> -->
        </div>

        <div class="image-column">
          <div class="industries-image-wrapper">
            <img
              src="https://a7oqb2wb89ps4x.projectwebtec9.com/wp-content/uploads/2026/04/strategy-2.jpg"
              alt="Profesionales colaborando en una mesa de trabajo"
              class="industries-image"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { computed, ref } from 'vue'

defineOptions({ name: 'IndustriesSection' })

const industries = ref<string[]>([
  'Legal e institucional ',
  'Salud',
  'Corporativo y empresarial',
  'Educación',
  'Eventos y conferencias',
  'Servicios al ciudadano',
  'Comercio internacional',
  'Procesos administrativos y documentales'
])

const industryColumns = computed(() => {
  const midpoint = Math.ceil(industries.value.length / 2)
  return [industries.value.slice(0, midpoint), industries.value.slice(midpoint)]
})
</script>

<style scoped>
.industries-section {
  padding: 100px clamp(20px, 5vw, 80px);
  background: linear-gradient(135deg, #ffffff 0%, #f7f7f7 100%);
}

.container {
  max-width: 1400px;
  margin: 0 auto;
}

.industries-layout {
  display: flex;
  align-items: stretch;
  gap: 48px;
}

.copy-column {
  flex: 1.1;
}

.image-column {
  flex: 0.9;
  display: flex;
  justify-content: center;
}

.eyebrow {
  font-size: 13px;
  text-transform: uppercase;
  letter-spacing: 0.16em;
  color: #be009f;
  margin-bottom: 12px;
}

.section-title {
  font-size: clamp(32px, 6vw, 32px);
  font-weight: 400;
  color: #282828;
  margin: 0 0 16px 0;
  letter-spacing: 1px;
}

.section-subtitle {
  font-size: 18px;
  color: #757575;
  margin: 0 0 28px 0;
  max-width: 620px;
  line-height: 1.8;
  font-weight: 400;
  text-align: justify;
}

.section-subtitle1 {
  font-size: 16px;
  color: #757575;
  margin: 0 0 28px 0;
  max-width: 620px;
  line-height: 1.8;
  font-weight: 400;
  text-align: justify;
}

.industries-lists {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 8px 40px;
  margin-bottom: 32px;
}

.industry-list {
  list-style: none;
  padding: 0;
  margin: 0;
  border-top: 1px solid rgba(148, 163, 184, 0.4);
}

.industry-list li {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 10px 0;
  font-size: 16px;
  color: var(--slate-700);
  border-bottom: 1px solid rgba(226, 232, 240, 0.8);
}

.bullet {
  width: 6px;
  height: 6px;
  border-radius: 999px;
  background: #be009f;
}

.industry-label {
  white-space: normal;
  line-height: 1.6;
  color: var(--medium-gray);
}

.view-all-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: linear-gradient(135deg, #be009f 0%, #be009f 100%);
  color: white;
  padding: 14px 32px;
  border: none;
  border-radius: 30px;
  font-size: 14px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.view-all-btn:hover {
  transform: translateY(-3px);
  box-shadow: 0 15px 40px rgba(236, 72, 153, 0.4);
}

.view-all-btn i {
  transition: transform 0.3s ease;
}

.view-all-btn:hover i {
  transform: translateX(4px);
}

.industries-image-wrapper {
  width: 100%;
  max-width: 480px;
  border-radius: 32px;
  overflow: hidden;

}

.industries-image {
  width: 100%;
  height: 100%;
  display: block;
  object-fit: cover;
}

@media (max-width: 768px) {
  .industries-section {
    padding: 60px clamp(16px, 4vw, 40px);
  }

  .industries-layout {
    flex-direction: column;
  }

  .industries-lists {
    grid-template-columns: 1fr;
  }

  .industries-image-wrapper {
    max-width: 100%;
  }

  .section-title {
    font-size: clamp(24px, 5vw, 24px);
  }

  .section-subtitle {
    font-size: 16px;
    text-align: justify;
  }

}
</style>
