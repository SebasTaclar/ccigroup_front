<template>
  <section class="what-sets-us-apart">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Dónde marcamos la diferencia</h2>
        <p class="section-subtitle">Nuestra ventaja competitiva es su ventaja</p>
      </div>

      <div class="cards-grid">
        <div class="card" v-for="(card, index) in differentiators" :key="index">
          <div class="card-icon">
            <i :class="card.icon"></i>
          </div>
          <h3 class="card-title">{{ card.title }}</h3>
          <p class="card-description">{{ card.description }}</p>
          <div class="card-stat" v-if="card.stat">
            <span class="stat-number">{{ card.stat.number }}</span>
            <span class="stat-label">{{ card.stat.label }}</span>
          </div>
        </div>
      </div>

      <!-- Stats Section -->
      <div class="stats-section">
        <p class="stats-intro">Cifras de confianza que hablan por sí solas</p>
        <div class="stats-grid">
          <div class="stat-card" v-for="(stat, index) in stats" :key="index">
            <div class="stat-value">{{ stat.value }}</div>
            <div class="stat-text">{{ stat.text }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'WhatSetsUsApart' })

const differentiators = ref([
  {
    icon: 'fas fa-bolt',
    title: 'Respuesta Inmediata',
    description: 'Acceda a intérpretes en remoto en menos de 48 segundos: sin demoras ni incertidumbre. Nuestra tecnología de avanzada garantiza el acceso en tiempo real en cualquier momento y lugar.',
    stat: { number: '48s', label: 'Tiempo de conexión' }
  },
  {
    icon: 'fas fa-clock',
    title: 'Disponibilidad Total',
    description: 'Soporte las 24 horas, los 365 días del año. Sus necesidades lingüísticas no tienen horario, nosotros tampoco. Personas reales, listas para ayudar en cualquier momento.',
    stat: { number: '24/7/365', label: 'Disponibilidad global' }
  },
  {
    icon: 'fas fa-globe',
    title: '350+ Idiomas',
    description: 'Desde el árabe hasta la lengua de señas colombiana, ofrecemos servicios lingüísticos que respetan los matices culturales y facilitan una conexión humana auténtica.',
    stat: { number: '350+', label: 'Idiomas y dialectos' }
  }
])

const stats = ref([
  { value: '350+', text: 'Idiomas y dialectos' },
  { value: '98.9%', text: 'Conexiones exitosas' },
  { value: '48s', text: 'Tiempo promedio' },
  { value: '24/7/365', text: 'Disponibilidad global' },
  { value: '12+', text: 'Años de experiencia' },
  { value: '10M+', text: 'Minutos de servicio' }
])
</script>

<style scoped>
.what-sets-us-apart {
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
  font-size: clamp(16px, 3vw, 20px);
  color: #666;
  margin: 0;
  font-weight: 500;
}

.cards-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 40px;
  margin-bottom: 100px;
}

.card {
  background: white;
  padding: 40px;
  border-radius: 20px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  text-align: center;
  border-top: 4px solid #ec4899;
}

.card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
}

.card-icon {
  font-size: 48px;
  color: #ec4899;
  margin-bottom: 24px;
}

.card-title {
  font-size: 22px;
  font-weight: 700;
  color: #1e3a8a;
  margin: 0 0 16px 0;
}

.card-description {
  font-size: 14px;
  color: #666;
  line-height: 1.8;
  margin: 0 0 24px 0;
}

.card-stat {
  display: flex;
  flex-direction: column;
  gap: 8px;
  padding-top: 20px;
  border-top: 1px solid #eee;
}

.stat-number {
  font-size: 28px;
  font-weight: 800;
  color: #ec4899;
}

.stat-label {
  font-size: 12px;
  color: #999;
  text-transform: uppercase;
  letter-spacing: 1px;
}

.stats-section {
  background: linear-gradient(135deg, #1e3a8a 0%, #3b0764 100%);
  border-radius: 20px;
  padding: 80px clamp(30px, 5vw, 60px);
  color: white;
}

.stats-intro {
  text-align: center;
  font-size: clamp(24px, 4vw, 32px);
  font-weight: 700;
  margin: 0 0 60px 0;
}

.stats-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
  gap: 40px;
}

.stat-card {
  text-align: center;
  padding: 20px;
}

.stat-value {
  font-size: clamp(28px, 5vw, 42px);
  font-weight: 800;
  color: #ec4899;
  margin-bottom: 8px;
}

.stat-text {
  font-size: 14px;
  color: rgba(255, 255, 255, 0.9);
  line-height: 1.5;
}

@media (max-width: 768px) {
  .what-sets-us-apart {
    padding: 60px clamp(16px, 4vw, 40px);
  }

  .section-header {
    margin-bottom: 50px;
  }

  .cards-grid {
    gap: 24px;
    margin-bottom: 60px;
  }

  .card {
    padding: 24px;
  }

  .stats-section {
    padding: 40px clamp(20px, 4vw, 40px);
  }

  .stats-intro {
    margin-bottom: 40px;
  }

  .stats-grid {
    gap: 24px;
  }
}</style>
