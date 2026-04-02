<template>
  <section class="main-banner">
    <div class="banner-background">
      <img
        src="https://images.unsplash.com/photo-1552664730-d307ca884978?w=1920&h=1080&fit=crop&q=80"
        alt="Profesionales"
        class="banner-image"
      >
      <div class="banner-overlay"></div>
    </div>

    <div class="banner-content">
      <h1 class="banner-title"><span class="title-line"></span>Soluciones lingüísticas innovadoras</h1>
      <p class="banner-subtitle">Conectando al mundo a través de la comunicación centrada en el ser humano.</p>

      <p class="banner-description">
        CCI Group transforma los desafíos de la comunicación en conexiones humanas, brindando servicios a gobiernos, instituciones de salud, educación e industria con experiencia certificada en más de 350 idiomas. Desde interpretación en tiempo real hasta notarización remota y soluciones de personal, eliminamos las barreras lingüísticas para que su organización pueda conectarse, comunicarse y alcanzar el éxito.
      </p>

      <div class="banner-buttons">
        <button class="btn btn-primary" @click="handleCTA">
          LLAMADA ESTRATÉGICA PARA RESERVAR <span class="arrow">→</span>
        </button>
        <button class="btn btn-secondary" @click="exploreSolutions">
          EXPLORAR SOLUCIONES
        </button>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({
  name: 'MainBanner'
})

const handleCTA = () => {
  const contactSection = document.querySelector('.contact-section')
  if (contactSection) {
    contactSection.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}

const exploreSolutions = () => {
  const solutionsSection = document.querySelector('.distinguish-section')
  if (solutionsSection) {
    solutionsSection.scrollIntoView({ behavior: 'smooth', block: 'start' })
  }
}
</script>

<style scoped>
.main-banner {
  position: relative;
  width: 100%;
  height: 115vh;
  min-height: 600px;
  margin-top: 75px;
  display: flex;
  align-items: flex-start;
  justify-content: flex-start;
  overflow: hidden;
  padding-top: 60px;
}

.banner-background {
  position: absolute;
  inset: 0;
  z-index: 1;
}

.banner-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

.banner-overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, rgba(30, 58, 138, 0.75) 0%, rgba(59, 7, 100, 0.75) 50%, rgba(107, 27, 107, 0.75) 100%);
  z-index: 2;
}

.banner-content {
  position: relative;
  z-index: 3;
  max-width: 1000px;
  padding-left: 170px;
  color: #ffffff;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.banner-title {
  font-size: clamp(36px, 8vw, 64px);
  font-weight: 900;
  line-height: 1.2;
  margin: 0;
  letter-spacing: -1px;
  text-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
  display: flex;
  align-items: center;
  gap: 20px;
}

.title-line {
  display: inline-block;
  width: 4px;
  height: clamp(40px, 8vw, 80px);
  background: #ffffff;
  border-radius: 2px;
  flex-shrink: 0;
}

.banner-subtitle {
  font-size: clamp(18px, 4vw, 24px);
  font-weight: 300;
  font-style: italic;
  margin: 0;
  color: rgba(255, 255, 255, 0.95);
  line-height: 1.5;
  letter-spacing: 0.5px;
}

.banner-description {
  font-size: 16px;
  color: rgba(255, 255, 255, 0.9);
  line-height: 1.8;
  margin: 0;
  max-width: 750px;
  font-weight: 400;
  text-align: justify;
}

.banner-buttons {
  display: flex;
  gap: 16px;
  align-items: center;
  flex-wrap: wrap;
  margin-top: 16px;
}

.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
  padding: 14px 32px;
  border-radius: 30px;
  border: none;
  font-size: 14px;
  font-weight: 700;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  white-space: nowrap;
}

.btn-primary {
  background: var(--brand-secondary-red, #EE2A31);  /* Rojo CCI */
  color: #ffffff;
  box-shadow: 0 20px 40px rgba(238, 42, 49, 0.4);
  display: flex;
  align-items: center;
  gap: 8px;
}

.btn-primary .arrow {
  font-size: 16px;
  transition: transform 0.3s ease;
}

.btn-primary:hover {
  background: #D41F26;  /* Rojo más oscuro */
  transform: translateY(-3px);
  box-shadow: 0 30px 50px rgba(238, 42, 49, 0.6);
}

.btn-primary:hover .arrow {
  transform: translateX(4px);
}

.btn-primary:active {
  transform: translateY(-1px);
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.15);
  color: #ffffff;
  border: 2px solid rgba(255, 255, 255, 0.4);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.2);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.7);
  color: var(--brand-secondary-red, #EE2A31);  /* Rojo CCI */
  transform: translateY(-3px);
  box-shadow: 0 12px 30px rgba(0, 0, 0, 0.3);
}

.btn-secondary:active {
  transform: translateY(-1px);
}



  .banner-content {
    padding-left: 170px;
    padding-top: 70px;
    padding-right: 70px;
    gap: 20px;
  }

  .banner-buttons {
    flex-direction: column;
  }

  .btn {
    width: 100%;
    padding: 12px 24px;
    font-size: 13px;
  }


@media (max-width: 480px) {
  .main-banner {
    min-height: 400px;
  }

  .banner-content {
    padding: 40px clamp(15px, 5vw, 30px);
    gap: 16px;
  }

  .banner-title {
    font-size: 28px;
  }

  .banner-subtitle {
    font-size: 16px;
  }

  .banner-description {
    font-size: 14px;
    line-height: 1.6;
  }

  .btn {
    padding: 10px 20px;
    font-size: 12px;
  }
}
</style>
