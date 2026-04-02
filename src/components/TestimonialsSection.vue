<template>
  <section class="testimonials-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Testimonios: Nuestra experiencia es su ventaja</h2>
        <p class="section-subtitle">Lo que dicen nuestros clientes sobre nuestros servicios</p>
      </div>

      <div class="testimonials-grid">
        <div class="testimonial-card" v-for="(testimonial, index) in testimonials" :key="index">
          <div class="stars">
            <i v-for="n in 5" :key="n" class="fas fa-star"></i>
          </div>

          <p class="testimonial-text">{{ testimonial.quote }}</p>

          <div class="testimonial-author">
            <div class="author-info">
              <p class="author-name">{{ testimonial.name }}</p>
              <p class="author-position">{{ testimonial.position }}</p>
            </div>
          </div>
        </div>
      </div>

      <div class="rating-info">
        <div class="rating-badge">
          <span class="rating-stars">⭐ 4.9/5</span>
          <span class="rating-text">según 47 reseñas</span>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

defineOptions({ name: 'TestimonialsSection' })

const testimonials = ref([
  {
    quote: '¡No tengo palabras para expresar lo satisfecho que estoy con el servicio excepcional de CCI Group! Desde la consulta inicial hasta las actualizaciones constantes, esta empresa ha superado mis expectativas en todo momento.',
    name: 'John Doe',
    position: 'Director de Marketing'
  },
  {
    quote: 'Con CCI Group, todo ha sido excelente desde el primer momento. El conocimiento de los profesionales para entender nuestras necesidades es inigualable; la paciencia que tuvieron con todo nuestro equipo fue increíble y el producto final es mejor de lo que podríamos haber pedido.',
    name: 'Herman Miller',
    position: 'Director de Operaciones (COO)'
  },
  {
    quote: 'Recomiendo totalmente trabajar con CCI Group. El personal es muy atento y la gerencia se involucra al máximo en el apoyo a los clientes. Sus profesionales siempre estuvieron al tanto de todo y fueron muy flexibles con nuestras solicitudes y personalizaciones.',
    name: 'Isabel Gabalis',
    position: 'Directora Ejecutiva (CEO)'
  },
  {
    quote: 'Estamos encantados con los servicios recibidos de CCI Group. El equipo tuvo una gran visión para llevar nuestras necesidades lingüísticas al siguiente nivel y ejecutó todo perfectamente. Trabajar con ellos fue un placer. ¡Recomiendo mucho a este equipo!',
    name: 'Ashley Jones',
    position: 'Directora Ejecutiva (CEO)'
  }
])
</script>

<style scoped>
.testimonials-section {
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
}

.testimonials-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 32px;
  margin-bottom: 60px;
}

.testimonial-card {
  background: white;
  padding: 40px;
  border-radius: 16px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  display: flex;
  flex-direction: column;
  gap: 20px;
  border-top: 4px solid #ec4899;
}

.testimonial-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.15);
}

.stars {
  display: flex;
  gap: 6px;
}

.stars i {
  color: #fbbf24;
  font-size: 14px;
}

.testimonial-text {
  font-size: 15px;
  color: #333;
  line-height: 1.8;
  margin: 0;
  font-style: italic;
}

.testimonial-author {
  display: flex;
  align-items: center;
  gap: 16px;
  padding-top: 16px;
  border-top: 1px solid #eee;
}

.author-info {
  flex: 1;
}

.author-name {
  font-size: 14px;
  font-weight: 700;
  color: #1e3a8a;
  margin: 0;
}

.author-position {
  font-size: 12px;
  color: #999;
  margin: 4px 0 0 0;
}

.rating-info {
  text-align: center;
  padding: 40px;
  background: white;
  border-radius: 16px;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.08);
}

.rating-badge {
  display: flex;
  flex-direction: column;
  gap: 8px;
  align-items: center;
}

.rating-stars {
  font-size: 32px;
  font-weight: 800;
  color: #1e3a8a;
}

.rating-text {
  font-size: 14px;
  color: #666;
}

@media (max-width: 768px) {
  .testimonials-section {
    padding: 60px clamp(16px, 4vw, 40px);
  }

  .section-header {
    margin-bottom: 50px;
  }

  .testimonials-grid {
    gap: 24px;
    margin-bottom: 40px;
  }

  .testimonial-card {
    padding: 24px;
  }
}</style>
