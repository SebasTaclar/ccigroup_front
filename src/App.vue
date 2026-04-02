<template>
  <header>
    <nav class="navbar">
      <!-- Logo y marca CCI Group -->
      <RouterLink class="link-navbar home" to="/" @click="closeMobileMenu">
        <div class="brand-container">
          <img src="/images/logo.png" alt="CCI Group" class="brand-logo">
        </div>
      </RouterLink>

      <!-- Navegación principal -->
      <div class="nav-menu desktop-nav">
        <a href="#about" class="nav-link" @click="closeMobileMenu">Acerca de</a>
        <a href="#solutions" class="nav-link" @click="closeMobileMenu">Soluciones</a>
        <a href="#industries" class="nav-link" @click="closeMobileMenu">Industrias</a>
        <a href="#fogonadua" class="nav-link" @click="closeMobileMenu">Fogonadua</a>
        <a href="#notarization" class="nav-link" @click="closeMobileMenu">Notarización</a>
        <a href="#resources" class="nav-link" @click="closeMobileMenu">Recursos</a>
      </div>

      <!-- Botón de contacto y página principal -->
      <div class="nav-controls desktop-nav">
        <a href="https://a7oqb2wb89ps4x.projectwebtec9.com/" target="_blank" rel="noopener" class="btn main-page-btn">Ir a página principal</a>
        <button class="btn contact-btn" @click="handleContact">Contáctanos <span class="arrow">›</span></button>
      </div>

      <!-- Menu hamburguesa para mobile -->
      <button class="hamburger-menu" @click="toggleMobileMenu" :class="{ 'active': isMobileMenuOpen }">
        <span></span>
        <span></span>
        <span></span>
      </button>

      <!-- Menu mobile desplegable -->
      <div class="mobile-menu" :class="{ 'active': isMobileMenuOpen }">
        <div class="mobile-menu-content">
          <div class="mobile-nav-links">
            <a href="#home" class="mobile-link" @click="closeMobileMenu">HOGAR</a>
            <a href="#about" class="mobile-link" @click="closeMobileMenu">ACERCA DE</a>
            <a href="#solutions" class="mobile-link" @click="closeMobileMenu">SOLUCIONES</a>
            <a href="#industries" class="mobile-link" @click="closeMobileMenu">INDUSTRIAS</a>
            <a href="#fogonadua" class="mobile-link" @click="closeMobileMenu">FOGONADUA</a>
            <a href="#notarization" class="mobile-link" @click="closeMobileMenu">NOTARIZACIÓN</a>
            <a href="#resources" class="mobile-link" @click="closeMobileMenu">RECURSOS</a>
          </div>

          <div class="mobile-controls">
            <a href="https://a7oqb2wb89ps4x.projectwebtec9.com/" target="_blank" rel="noopener" class="mobile-btn main-page-btn" @click="closeMobileMenu">PÁGINA PRINCIPAL</a>
            <button class="mobile-btn contact-btn" @click="handleContact; closeMobileMenu()">
              CONTACTO
            </button>
          </div>
        </div>
      </div>
    </nav>
  </header>

  <!-- Main Banner -->
  <MainBanner @showRules="openRulesModal" />

  <!-- Clientes/Socios Section -->
  <ClientsSection />

  <!-- Distinguish Section -->
  <DistinguishSection />

  <!-- What Sets Us Apart Section -->
  <WhatSetsUsApart />

  <!-- Core Services Section -->
  <ServicesSection />

  <!-- Industries Section -->
  <IndustriesSection />

  <!-- Process Section -->
  <ProcessSection />

  <!-- Testimonials Section -->
  <TestimonialsSection />

  <!-- Resources and Blog Section -->
  <ResourcesSection />

  <!-- Botón flotante de WhatsApp -->
  <WhatsAppFloating />

  <!-- Contact Section -->
  <ContactSection />

  <!-- Footer -->
  <Footer_ />
</template>

<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router';
import { authService } from '@/services/api';
import { onMounted, ref, watch } from 'vue';
import router from './router';
import MainBanner from '@/components/MainBanner.vue';
import WhatsAppFloating from '@/components/WhatsAppFloating.vue';
import ClientsSection from '@/components/ClientsSection.vue';
import DistinguishSection from '@/components/DistinguishSection.vue';
import WhatSetsUsApart from '@/components/WhatSetsUsApart.vue';
import ServicesSection from '@/components/ServicesSection.vue';
import IndustriesSection from '@/components/IndustriesSection.vue';
import ProcessSection from '@/components/ProcessSection.vue';
import TestimonialsSection from '@/components/TestimonialsSection.vue';
import ResourcesSection from '@/components/ResourcesSection.vue';
import ContactSection from '@/components/ContactSection.vue';
import Footer_ from '@/components/Footer_.vue';

const isLoggedIn = ref(false);
const username = ref('');
const isMobileMenuOpen = ref(false);
const showRulesModal = ref(false);

// Funciones para el menú hamburguesa
const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false;
};

// Funciones para el modal de reglas
const openRulesModal = () => {
  showRulesModal.value = true;
};



// Función para hacer scroll a la sección de productos
/* const scrollToProductStore = () => {
  const productStoreSection = document.querySelector('.product-store');
  if (productStoreSection) {
    productStoreSection.scrollIntoView({
      behavior: 'smooth',
      block: 'start'
    });
  }
}; */

// Función para hacer scroll a la sección de contacto
/* const scrollToContact = () => {
  const contactSection = document.querySelector('.contact-section');
  if (contactSection) {
    contactSection.scrollIntoView({
      behavior: 'smooth',
      block: 'start'
    });
  }
}; */

const checkAuthStatus = () => {
  isLoggedIn.value = authService.isAuthenticated();
  if (isLoggedIn.value) {
    const currentUser = authService.getCurrentUser();
    username.value = currentUser?.name || '';
  } else {
    username.value = '';
  }
};

// const _handleMobileLogout = () => {
//   closeMobileMenu();
//   logout();
// };

// Función para ir a la sección de contacto
const handleContact = () => {
  closeMobileMenu();
  router.push({ name: 'contacto' }).catch(() => {
    // Si no existe la ruta, hacer scroll a la sección
    scrollToSection('#contact');
  });
};

// Función para hacer scroll suave a una sección
const scrollToSection = (selector: string) => {
  const element = document.querySelector(selector);
  if (element) {
    element.scrollIntoView({ behavior: 'smooth', block: 'start' });
  } else {
    // Si el selector es '#solutions', navegar a la página de soluciones
    if (selector === '#solutions') {
      router.push({ name: 'soluciones' }).catch(() => {});
    }
  }
};

onMounted(() => {
  checkAuthStatus();
});

const route = useRoute();
watch(route, () => {
  checkAuthStatus();
});
</script>

<style scoped>
.navbar {
  background: #f5f5f5;
  margin: 0;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1000;
  height: auto;
  padding: 12px clamp(20px, 5vw, 60px);
  min-height: 75px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
  border-bottom: 1px solid #e5e7eb;
}

.brand-container {
  display: flex;
  align-items: center;
  gap: 8px;
  flex-shrink: 0;
}

/* Logo creativo */
.creative-logo {
  position: relative;
  width: 50px;
  height: 50px;
}

.logo-circle {
  width: 50px;
  height: 50px;
  background: linear-gradient(135deg, #EE2A31 0%, #001A70 100%);
  border-radius: 20%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
  border: 2px solid #EE2A31;
  box-shadow: none;
  transition: all 0.3s ease;
}

.logo-circle::before {
  content: '';
  position: absolute;
  inset: -3px;
  background: linear-gradient(135deg, #EE2A31 0%, #001A70 100%);
  border-radius: 20%;
  z-index: 0;
}

.logo-circle::after {
  content: '';
  position: absolute;
  inset: 3px;
  background: linear-gradient(135deg, rgba(238, 42, 49, 0.95) 0%, rgba(0, 26, 112, 0.95) 100%);
  border-radius: 15%;
  z-index: 1;
}

.logo-letter {
  position: relative;
  z-index: 2;
  font-weight: 900;
  font-size: 16px;
  color: #ffffff;
  text-shadow: none;
  letter-spacing: -1px;
}

.logo-letter:first-child::after {
  content: '•';
  margin: 0 1px;
  font-size: 8px;
  opacity: 0.6;
}

.logo-glow {
  position: absolute;
  inset: -10px;
  background: radial-gradient(circle, rgba(238, 42, 49, 0.2) 0%, transparent 70%);
  border-radius: 20%;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s ease;
}

.creative-logo:hover .logo-circle {
  transform: scale(1.05);
  box-shadow: 0 4px 12px rgba(238, 42, 49, 0.3);
}

.creative-logo:hover .logo-glow {
  opacity: 1;
}

@keyframes logoFloat {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-4px) rotate(2deg); }
}

.brand-logo {
  height: 4rem;
  width: 12rem;
  object-fit: contain;
  display: block;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.05));
}

.logo-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0;
  min-width: 70px;
  padding: 5px;
}

.brand-info {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  gap: 0px;
  justify-content: center;
  flex-shrink: 0;
}

.brand-title {
  font-size: 18px;
  font-weight: 700;
  line-height: 1;
  margin: 0;
  letter-spacing: 0.5px;
  color: #000000;
  white-space: nowrap;
}

.brand-title .highlight {
  background: linear-gradient(135deg, var(--white) 0%, var(--primary-red) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-shadow: 0 2px 8px rgba(220, 38, 38, 0.3);
  filter: drop-shadow(0 2px 8px rgba(220, 38, 38, 0.3));
}

.brand-tagline {
  font-size: 10px;
  color: #666666;
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin: 0;
}

.brand-subtitle {
  font-size: 10px;
  color: #999999;
  font-weight: 400;
  line-height: 1.2;
  margin: 0;
}

/* Navegación principal */
.nav-menu {
  display: flex;
  align-items: center;
  gap: 25px;
  margin: 0;
  flex: 1;
  justify-content: center;
}

.nav-link {
  color: #333333;
  text-decoration: none;
  font-weight: 400;
  font-size: 14px;
  padding: 8px 12px;
  border-radius: 0;
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  letter-spacing: 0;
  white-space: nowrap;
}

.nav-link::after {
  content: '';
  position: absolute;
  bottom: 4px;
  left: 50%;
  transform: translateX(-50%);
  width: 0;
  height: 2px;
  background: #EE2A31;
  transition: width 0.3s ease;
}

.nav-link:hover {
  color: #EE2A31;
  background-color: rgba(238, 42, 49, 0.05);
  transform: translateY(-2px);
}

.nav-link:hover::after {
  width: 70%;
}

.nav-link.active {
  color: var(--primary-red);
  background: rgba(220, 38, 38, 0.15);
}

.nav-link.active::after {
  width: 70%;
}

.share-btn {
  background: linear-gradient(135deg, #22d3ee 0%, #0891b2 100%);
  color: #ffffff !important;
  font-weight: 600;
  box-shadow: 0 2px 10px rgba(34, 211, 238, 0.3);
}

.share-btn:hover {
  background: linear-gradient(135deg, #0891b2 0%, #0e7490 100%);
  box-shadow: 0 4px 15px rgba(34, 211, 238, 0.5);
  transform: translateY(-2px);
}

/* Controles de usuario */
.nav-controls {
  display: flex;
  align-items: center;
  gap: 12px;
  margin-left: auto;
  flex-shrink: 0;
}

.btn {
  padding: 8px 18px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
  font-size: 13px;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  white-space: nowrap;
  text-transform: uppercase;
  letter-spacing: 0.3px;
}

.access-btn {
  background: linear-gradient(135deg, var(--primary-red) 0%, var(--dark-red) 100%);
  color: #ffffff;
  box-shadow: 0 4px 12px rgba(220, 38, 38, 0.3);
  font-weight: 700;
}

.access-btn:hover {
  background: linear-gradient(135deg, var(--dark-red) 0%, var(--tertiary-red) 100%);
  box-shadow: 0 6px 18px rgba(220, 38, 38, 0.4);
  transform: translateY(-2px);
}

.contact-btn {
  background: #001A70;
  color: #ffffff;
  box-shadow: 0 2px 8px rgba(0, 26, 112, 0.2);
  font-weight: 600;
  padding: 10px 22px;
  border-radius: 6px;
  font-size: 14px;
  text-transform: none;
  display: flex;
  align-items: center;
  gap: 6px;
}

.contact-btn .arrow {
  font-size: 18px;
  font-weight: 300;
  margin-left: 2px;
}

.contact-btn:hover {
  background: #000f47;
  box-shadow: 0 4px 12px rgba(0, 26, 112, 0.3);
  transform: translateY(-2px);
}

.main-page-btn {
  background: linear-gradient(135deg, #EE2A31 0%, #D32F2F 100%);
  color: #ffffff;
  box-shadow: 0 2px 8px rgba(238, 42, 49, 0.2);
  font-weight: 600;
  padding: 10px 22px;
  border-radius: 6px;
  font-size: 14px;
  text-decoration: none;
  display: flex;
  align-items: center;
  gap: 6px;
  transition: all 0.3s ease;
}

.main-page-btn:hover {
  background: linear-gradient(135deg, #D32F2F 0%, #B71C1C 100%);
  box-shadow: 0 4px 12px rgba(238, 42, 49, 0.3);
  transform: translateY(-2px);
}

.logout-btn {
  background: rgba(248, 113, 113, 0.1);
  color: #f87171;
  border: 1px solid rgba(248, 113, 113, 0.3);
}

.logout-btn:hover {
  background: rgba(248, 113, 113, 0.2);
  border-color: rgba(248, 113, 113, 0.5);
  transform: translateY(-1px);
}

.admin-btn {
  background: linear-gradient(135deg, var(--black) 0%, #1a1a1a 100%);
  color: var(--primary-red);
  box-shadow: 0 4px 16px rgba(0, 0, 0, 0.4);
  border: 1px solid rgba(220, 38, 38, 0.3);
  font-weight: 700;
}

.admin-btn:hover {
  background: linear-gradient(135deg, #1a1a1a 0%, var(--black) 100%);
  box-shadow: 0 6px 24px rgba(220, 38, 38, 0.4);
  transform: translateY(-3px);
  border-color: var(--primary-red);
}

.purchases-btn {
  background: var(--brand-accent-gradient);
  color: #ffffff;
  box-shadow: 0 2px 10px var(--brand-accent-glow);
}

.purchases-btn:hover {
  background: var(--brand-accent-gradient);
  filter: brightness(1.1);
  box-shadow: 0 4px 15px var(--brand-accent-glow);
  transform: translateY(-2px);
}

.user-greeting {
  color: #333333;
  font-weight: 700;
  font-size: 14px;
  padding: 10px 16px;
  background: rgba(238, 42, 49, 0.08);
  border-radius: 8px;
  border: 1px solid rgba(238, 42, 49, 0.2);
  letter-spacing: 0.3px;
}

/* Menu hamburguesa */
.hamburger-menu {
  display: none;
  flex-direction: column;
  width: 30px;
  height: 30px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  justify-content: space-around;
  align-items: center;
  z-index: 1001;
}

.hamburger-menu span {
  display: block;
  height: 3px;
  width: 100%;
  background-color: #333333;
  border-radius: 3px;
  transition: all 0.3s ease;
}

.hamburger-menu.active span:nth-child(1) {
  transform: rotate(45deg) translate(8px, 8px);
}

.hamburger-menu.active span:nth-child(2) {
  opacity: 0;
}

.hamburger-menu.active span:nth-child(3) {
  transform: rotate(-45deg) translate(7px, -6px);
}

/* Menu mobile */
.mobile-menu {
  display: none;
  position: fixed;
  top: 75px;
  left: 0;
  width: 100%;
  height: calc(100vh - 75px);
  background: #ffffff;
  transform: translateX(-100%);
  transition: transform 0.3s ease;
  z-index: 999;
  overflow-y: auto;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.mobile-menu.active {
  transform: translateX(0);
}

.mobile-menu-content {
  padding: 30px 20px;
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.mobile-nav-links {
  display: flex;
  flex-direction: column;
  gap: 15px;
}

.mobile-link {
  color: #333333;
  text-decoration: none;
  padding: 15px 20px;
  font-size: 16px;
  font-weight: 500;
  border-radius: 8px;
  transition: all 0.3s ease;
  text-align: center;
  background: rgba(238, 42, 49, 0.05);
  border: 1px solid rgba(238, 42, 49, 0.1);
}

.mobile-link:hover {
  background: rgba(238, 42, 49, 0.1);
  color: #EE2A31;
  transform: translateY(-2px);
}

.mobile-controls {
  display: flex;
  flex-direction: column;
  gap: 15px;
  padding-top: 20px;
  border-top: 1px solid #e5e7eb;
}

.mobile-btn {
  padding: 15px 20px;
  border-radius: 12px;
  text-decoration: none;
  font-weight: 600;
  font-size: 16px;
  text-align: center;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
  width: 100%;
  font-family: inherit;
}

.mobile-btn.access-btn {
  background: #001A70;
  color: #ffffff;
  box-shadow: 0 2px 8px rgba(0, 26, 112, 0.2);
}

.mobile-btn.logout-btn {
  background: rgba(248, 113, 113, 0.1);
  color: #f87171;
  border: 1px solid rgba(248, 113, 113, 0.3);
}

.mobile-btn.admin-btn {
  background: linear-gradient(135deg, #06b6d4 0%, #0891b2 100%);
  color: #ffffff;
  box-shadow: 0 4px 15px rgba(6, 182, 212, 0.3);
}

.mobile-btn.purchases-btn {
  background: linear-gradient(135deg, #60a5fa 0%, #3b82f6 100%);
  color: #ffffff;
  box-shadow: 0 4px 15px rgba(96, 165, 250, 0.3);
}

.mobile-btn.main-page-btn {
  background: linear-gradient(135deg, #EE2A31 0%, #D32F2F 100%);
  color: #ffffff;
  box-shadow: 0 2px 8px rgba(238, 42, 49, 0.2);
}

.mobile-btn.main-page-btn:active {
  background: linear-gradient(135deg, #D32F2F 0%, #B71C1C 100%);
  box-shadow: 0 4px 12px rgba(238, 42, 49, 0.3);
  transform: translateY(-2px);
}

.mobile-user-greeting {
  color: #333333;
  text-align: center;
  padding: 15px 20px;
  font-weight: 600;
  font-size: 15px;
  background: rgba(238, 42, 49, 0.05);
  border-radius: 8px;
  border: 1px solid rgba(238, 42, 49, 0.1);
}

/* Responsive */
@media (max-width: 768px) {
  .navbar {
    min-height: 70px;
    padding: 10px 15px;
  }

  .desktop-nav {
    display: none;
  }

  .hamburger-menu {
    display: flex;
  }

  .mobile-menu {
    display: block;
  }

  .brand-title {
    font-size: 16px;
    letter-spacing: 0.5px;
  }

  .brand-logo {
    width: 3.5rem;
    height: 3.5rem;
  }

  .brand-subtitle {
    font-size: 10px;
  }

  .brand-tagline {
    font-size: 9px;
  }

  .nav-controls {
    gap: 8px;
  }

  .btn {
    padding: 7px 14px;
    font-size: 12px;
  }

  .logo-circle {
    width: 45px;
    height: 45px;
    font-size: 12px;
  }
}

@media (max-width: 480px) {
  .navbar {
    min-height: 65px;
    padding: 10px 12px;
  }

  .brand-container {
    gap: 8px;
  }

  .brand-title {
    font-size: 14px;
    letter-spacing: 0.3px;
  }

  .brand-logo {
    width: 3rem;
    height: 3rem;
  }

  .brand-subtitle {
    font-size: 9px;
  }

  .logo-circle {
    width: 40px;
    height: 40px;
    font-size: 11px;
  }

  .nav-controls {
    gap: 6px;
  }

  .btn {
    padding: 6px 12px;
    font-size: 11px;
  }
}

/* Quitar subrayado del link principal */
.link-navbar {
  text-decoration: none !important;
}

/* Estilos para enlaces activos */
.nav-link.active,
.mobile-link.active {
  color: #0071e3;
  font-weight: 600;
  position: relative;
}

.nav-link.active::after,
.mobile-link.active::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: #0071e3;
  border-radius: 2px;
  animation: fadeIn 0.3s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scaleX(0.5);
  }
  to {
    opacity: 1;
    transform: scaleX(1);
  }
}

.link-navbar:hover {
  text-decoration: none !important;
}

/* Estilos para enlaces activos */
.nav-link.active,
.mobile-link.active {
  color: #0071e3;
  font-weight: 600;
  position: relative;
}

.nav-link.active::after,
.mobile-link.active::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: 0;
  width: 100%;
  height: 2px;
  background-color: #0071e3;
  border-radius: 2px;
  animation: fadeIn 0.3s ease-in-out;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scaleX(0.5);
  }
  to {
    opacity: 1;
    transform: scaleX(1);
  }
}
</style>
