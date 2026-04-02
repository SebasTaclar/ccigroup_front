<template>
  <div class="floating-whatsapp-right">
    <a
      :href="whatsappLink"
      target="_blank"
      rel="noopener"
      class="whatsapp-btn"
      title="Contáctanos por WhatsApp"
    >
      <img
        src="https://cdn-icons-png.flaticon.com/512/733/733585.png"
        alt="WhatsApp"
        class="whatsapp-icon"
      >
      <span class="tooltip">Contáctanos por WhatsApp</span>
    </a>
  </div>
</template>

<script setup lang="ts">
// Número en formato internacional (sin '+')
const rawNumber = '573209860099'
// Normaliza a solo dígitos
const whatsappNumber = rawNumber.replace(/[^\d]/g, '')

// Validación mínima: debe empezar por 57 y tener al menos 12 dígitos (57 + 10)
const isValidWhatsAppNumber = /^57\d{10}$/.test(whatsappNumber)

const defaultMessage = 'Hola! Me interesa conocer más sobre los servicios de CCI Group. ¿Me pueden brindar más información?'
// Endpoint alternativo más tolerante que wa.me
const whatsappLink = isValidWhatsAppNumber
  ? `https://api.whatsapp.com/send?phone=${whatsappNumber}&text=${encodeURIComponent(defaultMessage)}`
  : '#'

defineOptions({ name: 'WhatsAppFloating' })
</script>

<style scoped>
@keyframes pulse-whatsapp {
  0% {
    box-shadow: 0 0 0 0 rgba(37, 211, 102, 0.7);
  }
  70% {
    box-shadow: 0 0 0 15px rgba(37, 211, 102, 0);
  }
  100% {
    box-shadow: 0 0 0 0 rgba(37, 211, 102, 0);
  }
}

@keyframes bounce-whatsapp {
  0%, 100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-8px);
  }
}

.floating-whatsapp-right {
  position: fixed;
  bottom: 30px;
  right: 30px;
  z-index: 1000;
  animation: bounce-whatsapp 3s infinite;
}

.whatsapp-btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 65px;
  height: 65px;
  background: linear-gradient(135deg, #25d366 0%, #20b858 100%);
  border-radius: 50%;
  color: #ffffff;
  text-decoration: none;
  box-shadow: 0 8px 24px rgba(37, 211, 102, 0.4);
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  animation: pulse-whatsapp 2s infinite;
}

.whatsapp-btn:hover {
  background: linear-gradient(135deg, #20b858 0%, #1aa84d 100%);
  box-shadow: 0 16px 40px rgba(37, 211, 102, 0.8), inset 0 0 20px rgba(255, 255, 255, 0.2);
  transform: scale(1.2) translateY(-4px);
  animation: none;
}

.whatsapp-btn svg {
  width: 28px;
  height: 28px;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.15));
}

.whatsapp-icon {
  width: 32px;
  height: 32px;
  object-fit: contain;
  filter: drop-shadow(0 2px 4px rgba(0, 0, 0, 0.2));
}

.tooltip {
  position: absolute;
  bottom: -40px;
  right: 50%;
  transform: translateX(50%);
  background: rgba(0, 0, 0, 0.9);
  color: #25d366;
  padding: 10px 16px;
  border-radius: 8px;
  font-size: 13px;
  white-space: nowrap;
  opacity: 0;
  transition: opacity 0.3s ease, transform 0.3s ease;
  pointer-events: none;
  font-weight: 600;
  letter-spacing: 0.3px;
  border: 1px solid rgba(37, 211, 102, 0.3);
}

.whatsapp-btn:hover .tooltip {
  opacity: 1;
  transform: translateX(50%) translateY(0);
}

@media (max-width: 768px) {
  .floating-whatsapp-right {
    bottom: 20px;
    right: 20px;
  }

  .whatsapp-btn {
    width: 60px;
    height: 60px;
  }

  .whatsapp-btn svg {
    width: 26px;
    height: 26px;
  }
}

@media (max-width: 480px) {
  .floating-whatsapp-right {
    bottom: 15px;
    right: 15px;
  }

  .whatsapp-btn {
    width: 55px;
    height: 55px;
  }

  .whatsapp-btn svg {
    width: 24px;
    height: 24px;
  }

  .tooltip {
    font-size: 12px;
    padding: 8px 12px;
    bottom: -35px;
  }
}
</style>
