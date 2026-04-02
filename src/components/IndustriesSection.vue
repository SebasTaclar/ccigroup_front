<template>
  <section class="industries-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Brindamos servicios a aquellos sectores en los que la precisión es clave</h2>
        <p class="section-subtitle">Personalizamos nuestros servicios según su entorno operativo, normativas de cumplimiento y necesidades culturales</p>
      </div>

      <div class="industries-grid">
        <div class="industry-card" v-for="(industry, index) in industries" :key="index">
          <div class="industry-icon">
            <i :class="industry.icon"></i>
          </div>
          <h3 class="industry-name">{{ industry.name }}</h3>
        </div>
      </div>

      <div class="industries-info">
        <p class="info-text">
          Ya sea en agencias federales como FEMA y USAID, o en el ámbito universitario y hospitalario, personalizamos nuestros servicios según su entorno operativo, normativas de cumplimiento y necesidades culturales.
        </p>
        <button class="view-all-btn">
          <span>Vea todas las industrias</span>
          <i class="fas fa-arrow-right"></i>
        </button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'IndustriesSection' })

const industries = ref([
  { name: 'Gobierno', icon: 'fas fa-landmark' },
  { name: 'Salud', icon: 'fas fa-hospital' },
  { name: 'Educación', icon: 'fas fa-graduation-cap' },
  { name: 'Legal y Judicial', icon: 'fas fa-gavel' },
  { name: 'Corporativo', icon: 'fas fa-building' },
  { name: 'Tecnología y SaaS', icon: 'fas fa-laptop-code' },
  { name: 'ONGs', icon: 'fas fa-hands-helping' },
  { name: 'Medios y Eventos', icon: 'fas fa-film' }
])
</script>

<style scoped>
.industries-section {
  padding: 100px clamp(20px, 5vw, 80px);
  background: linear-gradient(135deg, #f8f9fb 0%, #f5f7fc 100%);
}

.container {
  max-width: 1400px;
  margin: 0 auto;
}

.section-header {
  text-align: center;
  margin-bottom: 80px;
}

.section-title {
  font-size: clamp(32px, 6vw, 48px);
  font-weight: 800;
  color: #1e3a8a;
  margin: 0 0 16px 0;
  letter-spacing: -0.5px;
}

.section-subtitle {
  font-size: clamp(14px, 3vw, 18px);
  color: #666;
  margin: 0;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

.industries-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 24px;
  margin-bottom: 60px;
}

.industry-card {
  background: white;
  padding: 32px;
  border-radius: 16px;
  text-align: center;
  border: 2px solid transparent;
  transition: all 0.3s ease;
  cursor: pointer;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.05);
}

.industry-card:hover {
  border-color: #ec4899;
  transform: translateY(-8px);
  box-shadow: 0 15px 40px rgba(236, 72, 153, 0.15);
}

.industry-icon {
  font-size: 40px;
  color: #1e3a8a;
  margin-bottom: 16px;
  transition: color 0.3s ease;
}

.industry-card:hover .industry-icon {
  color: #ec4899;
}

.industry-name {
  font-size: 16px;
  font-weight: 600;
  color: #1e3a8a;
  margin: 0;
}

.industries-info {
  background: white;
  padding: 60px;
  border-radius: 16px;
  text-align: center;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
}

.info-text {
  font-size: 16px;
  color: #666;
  line-height: 1.8;
  margin: 0 0 30px 0;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
}

.view-all-btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: linear-gradient(135deg, #ec4899 0%, #d946ef 100%);
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

@media (max-width: 768px) {
  .industries-section {
    padding: 60px clamp(16px, 4vw, 40px);
  }

  .section-header {
    margin-bottom: 50px;
  }

  .industries-grid {
    gap: 16px;
    margin-bottom: 40px;
  }

  .industry-card {
    padding: 20px;
  }

  .industries-info {
    padding: 40px;
  }
}</style>
