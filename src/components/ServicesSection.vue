<template>
  <section class="services-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Servicios esenciales para impulsar la comunicación global</h2>
        <p class="section-subtitle">A través de nuestros intérpretes certificados, expertos en localización y notarios profesionales, diseñamos servicios para satisfacer sus necesidades lingüísticas urgentes y de alto impacto.</p>
      </div>

      <div class="services-grid">
        <div class="service-card" v-for="(service, index) in services" :key="index" :style="{ '--index': index }">
          <div class="service-icon">
            <i :class="service.icon"></i>
          </div>
          <h3 class="service-title">{{ service.title }}</h3>
          <p class="service-description">{{ service.description }}</p>
          <ul class="service-features">
            <li v-for="(feature, fIndex) in service.features" :key="fIndex">
              <i class="fas fa-check-circle"></i>
              {{ feature }}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'ServicesSection' })

const services = ref([
  {
    icon: 'fas fa-headset',
    title: 'Servicios de Interpretación',
    description: 'Servicios sin barreras, rápidos, flexibles y profesionales, disponibles de manera presencial, remota o telefónica.',
    features: [
      'Disponibles 24/7',
      'Más de 350 idiomas',
      'Intérpretes certificados',
      'Conexión en 48 segundos'
    ]
  },
  {
    icon: 'fas fa-file-alt',
    title: 'Servicios de Traducción',
    description: 'Precisión en todo tipo de documentos, industrias y plataformas con lingüistas expertos.',
    features: [
      'Traducciones certificadas',
      'Servicios técnicos',
      'Traducciones creativas',
      'Procesos optimizados con IA'
    ]
  },
  {
    icon: 'fas fa-users',
    title: 'Gestión de Talento Global',
    description: 'Selección de personal multilingüe y multicultural para todas las industrias.',
    features: [
      'Personal multilingüe',
      'Contratación flexible',
      'Presencial o remota',
      'Profesionales multidisciplinarios'
    ]
  },
  {
    icon: 'fas fa-sign-language',
    title: 'Lengua de Señas y Accesibilidad',
    description: 'Inclusión total para la comunidad sorda y con discapacidad auditiva.',
    features: [
      'Interpretación ASL',
      'Subtitulado en tiempo real',
      'Cumplimiento ADA',
      'Asesoría normativa'
    ]
  },
  {
    icon: 'fas fa-certificate',
    title: 'Notarización Remota y Apostilla',
    description: 'Soporte notarial multilingüe y autenticación segura desde cualquier lugar.',
    features: [
      'Disponible 24/7',
      'Soporte multilingüe',
      'Autenticación segura',
      'Validación en el extranjero'
    ]
  },
  {
    icon: 'fas fa-globe-americas',
    title: 'Localización y Multimedia',
    description: 'Adaptamos contenido, diseño y UX para cualquier mercado global.',
    features: [
      'Localización web',
      'Adaptación de software',
      'SEO multilingüe',
      'Pruebas culturales'
    ]
  }
])
</script>

<style scoped>
.services-section {
  padding: 100px clamp(20px, 5vw, 80px);
  background: white;
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
  margin: 0 0 20px 0;
  letter-spacing: -0.5px;
}

.section-subtitle {
  font-size: clamp(14px, 3vw, 18px);
  color: #666;
  margin: 0;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.7;
}

.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(340px, 1fr));
  gap: 32px;
}

.service-card {
  background: #f8f9fb;
  border: 1px solid #e5e7eb;
  padding: 40px;
  border-radius: 16px;
  transition: all 0.3s ease;
  border-left: 4px solid #ec4899;
  position: relative;
  overflow: hidden;
}

.service-card::before {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  width: 120px;
  height: 120px;
  background: linear-gradient(135deg, rgba(236, 72, 153, 0.05) 0%, rgba(217, 70, 239, 0.05) 100%);
  border-radius: 50%;
  transform: translate(40%, -40%);
}

.service-card:hover {
  transform: translateY(-8px);
  border-color: #ec4899;
  box-shadow: 0 20px 50px rgba(236, 72, 153, 0.15);
}

.service-icon {
  font-size: 42px;
  color: #ec4899;
  margin-bottom: 20px;
}

.service-title {
  font-size: 20px;
  font-weight: 700;
  color: #1e3a8a;
  margin: 0 0 12px 0;
}

.service-description {
  font-size: 14px;
  color: #666;
  line-height: 1.7;
  margin: 0 0 24px 0;
}

.service-features {
  list-style: none;
  padding: 0;
  margin: 0;
}

.service-features li {
  font-size: 13px;
  color: #555;
  padding: 8px 0;
  display: flex;
  align-items: center;
  gap: 10px;
  border-bottom: 1px solid rgba(0, 0, 0, 0.05);
}

.service-features li:last-child {
  border-bottom: none;
}

.service-features i {
  color: #ec4899;
  font-size: 12px;
}

@media (max-width: 768px) {
  .services-section {
    padding: 60px clamp(16px, 4vw, 40px);
  }

  .section-header {
    margin-bottom: 50px;
  }

  .services-grid {
    grid-template-columns: 1fr;
    gap: 24px;
  }

  .service-card {
    padding: 24px;
  }
}</style>
