<template>
  <section class="process-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">De la solicitud a la solución</h2>
        <p class="section-subtitle">Agilidad, rigor y garantía legal en cada paso</p>
      </div>

      <div class="process-timeline">
        <div class="process-step" v-for="(step, index) in steps" :key="index">
          <div class="step-connector" v-if="index < steps.length - 1"></div>

          <div class="step-number">{{ String(index + 1).padStart(2, '0') }}</div>

          <div class="step-content">
            <h3 class="step-title">{{ step.title }}</h3>
            <p class="step-description">{{ step.description }}</p>
          </div>
        </div>
      </div>

      <div class="process-cta">
        <p>¿Listo para comenzar? Envía tu solicitud y conecta con nuestros expertos hoy mismo.</p>
        <button class="cta-button">
          Enviar solicitud <span class="arrow">→</span>
        </button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'ProcessSection' })

const steps = ref([
  {
    title: 'Envíe su solicitud',
    description: 'Háganos llegar sus documentos o los detalles de su evento a través de nuestra plataforma segura.'
  },
  {
    title: 'Conecte con expertos',
    description: 'Seleccionamos a los lingüistas e intérpretes certificados que mejor se ajustan a los requisitos específicos de su proyecto.'
  },
  {
    title: 'Reciba la solución',
    description: 'Obtenga sus traducciones, servicios de interpretación o notarizaciones con rapidez y exactitud.'
  },
  {
    title: 'Revise y confirme',
    description: 'Asegúrese de que el servicio cumple con sus estándares, mediante nuestros procesos de garantía de calidad.'
  }
])
</script>

<style scoped>
.process-section {
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
  margin: 0 0 16px 0;
  letter-spacing: -0.5px;
}

.section-subtitle {
  font-size: clamp(14px, 3vw, 18px);
  color: #666;
  margin: 0;
}

.process-timeline {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 40px;
  margin-bottom: 80px;
  position: relative;
}

.process-step {
  position: relative;
  padding-left: 100px;
  min-height: 200px;
}

.step-number {
  position: absolute;
  left: 0;
  top: 0;
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, #ec4899 0%, #d946ef 100%);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 32px;
  font-weight: 800;
  color: white;
  box-shadow: 0 10px 30px rgba(236, 72, 153, 0.3);
}

.step-connector {
  position: absolute;
  left: 40px;
  top: 80px;
  width: 2px;
  height: 120px;
  background: linear-gradient(180deg, #ec4899 0%, transparent 100%);
}

.step-content {
  padding-top: 0;
}

.step-title {
  font-size: 18px;
  font-weight: 700;
  color: #1e3a8a;
  margin: 0 0 12px 0;
}

.step-description {
  font-size: 14px;
  color: #666;
  line-height: 1.7;
  margin: 0;
}

.process-cta {
  text-align: center;
  background: linear-gradient(135deg, #f8f9fb 0%, #f5f7fc 100%);
  padding: 60px;
  border-radius: 16px;
  border: 2px solid #e5e7eb;
}

.process-cta p {
  font-size: 18px;
  color: #333;
  margin: 0 0 24px 0;
  font-weight: 500;
}

.cta-button {
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

.cta-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 15px 40px rgba(236, 72, 153, 0.4);
}

.cta-button .arrow {
  transition: transform 0.3s ease;
}

.cta-button:hover .arrow {
  transform: translateX(4px);
}

@media (max-width: 1024px) {
  .process-timeline {
    gap: 30px;
  }

  .step-connector {
    display: none;
  }
}

@media (max-width: 768px) {
  .process-section {
    padding: 60px clamp(16px, 4vw, 40px);
  }

  .section-header {
    margin-bottom: 50px;
  }

  .process-timeline {
    gap: 24px;
    margin-bottom: 50px;
  }

  .process-step {
    padding-left: 80px;
    min-height: 160px;
  }

  .step-number {
    width: 60px;
    height: 60px;
    font-size: 24px;
  }

  .process-cta {
    padding: 40px;
  }

  .process-cta p {
    font-size: 16px;
  }
}</style>
