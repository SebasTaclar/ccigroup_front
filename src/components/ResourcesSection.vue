<template>
  <section class="resources-section">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">Últimas noticias y recursos</h2>
        <p class="section-subtitle">Manténgase informado con artículos, consejos y noticias del sector sobre traducción, interpretación, accesibilidad y comunicación multilingüe. Aprenda a optimizar las soluciones lingüísticas para su organización.</p>
        <a href="#" class="blog-button">LEE NUESTRO BLOG →</a>
      </div>

      <div class="resources-grid">
        <!-- Podcast Featured Section -->
        <div class="resource-card podcast-card">
          <div class="card-header podcast-header">
            <h3 class="card-title">Podcast destacado</h3>
          </div>
          <div class="podcast-content">
            <h4 class="podcast-main-title">El podcast de LanguageVerse</h4>
            <p class="podcast-tagline">"Rompiendo barreras lingüísticas en la respuesta a emergencias"</p>
            <p class="podcast-description">Explora el fascinante mundo de los idiomas y la comunicación intercultural con expertos del sector.</p>
            <a href="#" class="podcast-button">
              <span class="spotify-icon">●</span>
              ESCÚCHALO AHORA EN SPOTIFY
            </a>
          </div>
        </div>

        <!-- Publications Featured Section -->
        <div class="resource-card publications-card">
          <div class="card-header publications-header">
            <h3 class="card-title">Publicaciones destacadas</h3>
          </div>
          <div class="publications-list">
            <article class="publication-item">
              <div class="publication-image">
                <img src="/images/cliente1.png" alt="Publicación 1">
              </div>
              <div class="publication-info">
                <h5>My take on Surviving One of the Government Shutdown (And Counting)</h5>
                <div class="publication-meta">📅 10 de febrero de 2023</div>
              </div>
              <span class="publication-badge">Entrenador</span>
            </article>

            <article class="publication-item">
              <div class="publication-image">
                <img src="/images/cliente2.png" alt="Publicación 2">
              </div>
              <div class="publication-info">
                <h5>Ir a un juzgado en los Estados Unidos por primera vez</h5>
                <div class="publication-meta">📅 10 de febrero de 2023</div>
              </div>
              <span class="publication-badge">Entrenador</span>
            </article>
          </div>
        </div>

        <!-- Additional Resource -->
        <div class="resource-card extra-card">
          <div class="card-header extra-header">
            <h3 class="card-title">Recursos útiles</h3>
          </div>
          <div class="extra-content">
            <p class="extra-description">Accede a nuestras guías, webinars y herramientas prácticas para mejorar tus procesos de comunicación multilingüe.</p>
            <a href="#" class="extra-button">Explorar recursos →</a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
defineOptions({ name: 'ResourcesSection' })
</script>

<style scoped>
.resources-section {
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
  font-size: clamp(14px, 3vw, 16px);
  color: #667eea;
  margin: 0 0 32px 0;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.6;
}

.blog-button {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: linear-gradient(135deg, #d946ef 0%, #c2185b 100%);
  color: white;
  padding: 14px 28px;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 700;
  font-size: 14px;
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(217, 70, 239, 0.3);
}

.blog-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(217, 70, 239, 0.4);
}

.resources-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 32px;
}

.resource-card {
  background: white;
  border-radius: 16px;
  overflow: hidden;
  border: 1px solid #f0f0f0;
  transition: all 0.3s ease;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
}

.resource-card:hover {
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.1);
  transform: translateY(-4px);
}

.card-header {
  padding: 24px;
  border-bottom: 1px solid #f0f0f0;
}

.podcast-header {
  background: #2d2d2d;
  border-bottom: none;
}

.publications-header {
  background: #f8f9fa;
}

.extra-header {
  background: linear-gradient(135deg, #f3f4f6 0%, #e5e7eb 100%);
}

.card-title {
  font-size: 18px;
  font-weight: 700;
  margin: 0;
  color: #1e3a8a;
}

.podcast-header .card-title {
  color: white;
}

/* Podcast Card */
.podcast-card {
  background: #2d2d2d;
  color: white;
}

.podcast-content {
  padding: 32px 24px;
}

.podcast-main-title {
  font-size: 22px;
  font-weight: 800;
  margin: 0 0 12px 0;
  color: #a78bfa;
}

.podcast-tagline {
  font-size: 14px;
  color: rgba(255, 255, 255, 0.7);
  margin: 0 0 16px 0;
  font-style: italic;
}

.podcast-description {
  font-size: 14px;
  line-height: 1.6;
  color: rgba(255, 255, 255, 0.85);
  margin: 0 0 24px 0;
}

.podcast-button {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: linear-gradient(135deg, #d946ef 0%, #c2185b 100%);
  color: white;
  padding: 12px 24px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 700;
  font-size: 12px;
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
}

.podcast-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(217, 70, 239, 0.3);
}

.spotify-icon {
  font-size: 16px;
}

/* Publications Card */
.publications-list {
  padding: 24px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.publication-item {
  display: flex;
  gap: 16px;
  padding-bottom: 20px;
  border-bottom: 1px solid #f0f0f0;
  position: relative;
}

.publication-item:last-child {
  border-bottom: none;
  padding-bottom: 0;
}

.publication-image {
  width: 80px;
  height: 80px;
  border-radius: 8px;
  overflow: hidden;
  flex-shrink: 0;
}

.publication-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.publication-info {
  flex: 1;
}

.publication-item h5 {
  font-size: 14px;
  font-weight: 700;
  color: #1e3a8a;
  margin: 0 0 8px 0;
  line-height: 1.4;
}

.publication-meta {
  font-size: 12px;
  color: #999;
  margin: 0;
}

.publication-badge {
  position: absolute;
  top: 0;
  right: 0;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 10px;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

/* Extra Card */
.extra-content {
  padding: 32px 24px;
}

.extra-description {
  font-size: 14px;
  line-height: 1.6;
  color: #666;
  margin: 0 0 24px 0;
}

.extra-button {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  text-decoration: none;
  font-weight: 700;
  font-size: 14px;
  transition: all 0.3s ease;
}

.extra-button:hover {
  gap: 12px;
}

/* Responsive */
@media (max-width: 768px) {
  .resources-section {
    padding: 60px clamp(20px, 5vw, 40px);
  }

  .section-header {
    margin-bottom: 60px;
  }

  .section-title {
    font-size: 28px;
  }

  .resources-grid {
    grid-template-columns: 1fr;
  }

  .podcast-content {
    padding: 24px 16px;
  }

  .publication-image {
    width: 70px;
    height: 70px;
  }

  .blog-button {
    width: 100%;
    justify-content: center;
  }
}


.articles-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 32px;
}

.article-card {
  background: #f8f9fb;
  padding: 32px;
  border-radius: 16px;
  border-left: 4px solid #ec4899;
  transition: all 0.3s ease;
}

.article-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 50px rgba(0, 0, 0, 0.1);
}

.article-date {
  font-size: 12px;
  color: #999;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  margin-bottom: 12px;
}

.article-title {
  font-size: 18px;
  font-weight: 700;
  color: #1e3a8a;
  margin: 0 0 8px 0;
  line-height: 1.4;
}

.article-author {
  font-size: 13px;
  color: #666;
  margin: 0 0 16px 0;
}

.article-link {
  display: inline-flex;
  align-items: center;
  gap: 6px;
  color: #ec4899;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.article-link:hover {
  gap: 12px;
}

@media (max-width: 1024px) {
  .featured-podcast {
    grid-template-columns: 1fr;
    gap: 40px;
  }

  .podcast-visual {
    display: none;
  }
}

@media (max-width: 768px) {
  .resources-section {
    padding: 60px clamp(16px, 4vw, 40px);
  }

  .section-header {
    margin-bottom: 50px;
  }

  .featured-podcast {
    padding: 40px clamp(20px, 4vw, 40px);
    margin-bottom: 50px;
  }

  .podcast-title {
    margin-bottom: 8px;
  }

  .blog-section {
    margin-top: 50px;
  }

  .articles-grid {
    gap: 24px;
  }
}
</style>
