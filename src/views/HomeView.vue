<script setup lang="ts">
/**
 * HomeView.vue
 * Main landing page for Fruta Bar.
 * Focuses on premium aesthetics and mandatory legal information.
 */
import logoUrl from '@/assets/image.png';
</script>

<template>
  <main class="home-view">
    <!-- Hero Section -->
    <section class="hero">
      <div class="hero__content">
        <img :src="logoUrl" alt="Fruta Bar Logo" class="hero__logo" />
        <h1 class="hero__title">El mejor restaurante de Guayaquil</h1>
        <p class="hero__subtitle">Sabor, frescura y tradición en cada bocado.</p>
        <div class="hero__badge">Premium Experience</div>
      </div>
      <div class="hero__background-overlay"></div>
    </section>

    <!-- Footer Section (Mandatory Legal Information) -->
    <footer class="footer">
      <div class="footer__container">
        <div class="footer__legal">
          <h2 class="footer__legal-title">Información Legal</h2>
          <ul class="footer__legal-list">
            <li>
              <span class="label">Nombre Legal:</span> 
              <span class="value">FRUTA BAR S.A. BARFRUIT</span>
            </li>
            <li>
              <span class="label">RUC:</span> 
              <span class="value">0992353260001</span>
            </li>
            <li>
              <span class="label">Dirección:</span> 
              <span class="value">CALLE AV.V.E.ESTRADA NÚMERO 0608 INTERSECCIÓN LAS MONJAS, GUAYAQUIL</span>
            </li>
            <li>
              <span class="label">Correo:</span> 
              <a href="mailto:jzamora@frutabar.com" class="value link">jzamora@frutabar.com</a>
            </li>
          </ul>
        </div>
        <div class="footer__copyright">
          &copy; {{ new Date().getFullYear() }} Fruta Bar. All rights reserved.
        </div>
      </div>
    </footer>
  </main>
</template>

<style lang="scss" scoped>
.home-view {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  background-color: $white;
}

.hero {
  position: relative;
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem 1.5rem;
  overflow: hidden;
  text-align: center;
  background: linear-gradient(135deg, rgba($primary, 0.05) 0%, rgba($secondary, 0.05) 100%);

  &__content {
    position: relative;
    z-index: 2;
    max-width: 800px;
    animation: fadeIn 1s ease-out;
  }

  &__logo {
    width: 180px;
    height: auto;
    margin-bottom: 2.5rem;
    filter: drop-shadow(0 10px 15px rgba(0, 0, 0, 0.1));
    transition: transform 0.3s ease;

    &:hover {
      transform: scale(1.05);
    }
  }

  &__title {
    font-family: $font-principal;
    font-size: clamp(2.5rem, 8vw, 4.5rem);
    font-weight: 800;
    line-height: 1.1;
    color: $primary-dark;
    margin-bottom: 1.5rem;
    letter-spacing: -0.02em;
  }

  &__subtitle {
    font-family: $font-secondary;
    font-size: clamp(1.1rem, 3vw, 1.5rem);
    color: $text-secondary;
    max-width: 600px;
    margin: 0 auto 2.5rem;
    line-height: 1.6;
  }

  &__badge {
    display: inline-block;
    padding: 0.5rem 1.25rem;
    background-color: rgba($secondary, 0.1);
    color: $secondary;
    font-family: $font-secondary;
    font-weight: 600;
    font-size: 0.875rem;
    text-transform: uppercase;
    letter-spacing: 0.1em;
    border-radius: 100px;
    border: 1px solid rgba($secondary, 0.2);
  }

  &__background-overlay {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-image: radial-gradient(circle at 20% 30%, rgba($primary, 0.03) 0%, transparent 50%),
                      radial-gradient(circle at 80% 70%, rgba($secondary, 0.03) 0%, transparent 50%);
    pointer-events: none;
  }
}

.footer {
  background-color: $primary-dark;
  color: $text-light;
  padding: 4rem 1.5rem 2rem;
  border-top: 1px solid rgba($white, 0.1);

  &__container {
    max-width: 1200px;
    margin: 0 auto;
  }

  &__legal {
    margin-bottom: 3rem;

    &-title {
      font-family: $font-principal;
      font-size: 1.25rem;
      font-weight: 700;
      margin-bottom: 2rem;
      color: $secondary;
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }

    &-list {
      list-style: none;
      display: grid;
      grid-template-columns: 1fr;
      gap: 1.5rem;

      li {
        display: flex;
        flex-direction: column;
        gap: 0.25rem;
      }

      .label {
        font-family: $font-secondary;
        font-size: 0.75rem;
        font-weight: 700;
        color: rgba($text-light, 0.5);
        text-transform: uppercase;
        letter-spacing: 0.05em;
      }

      .value {
        font-family: $font-secondary;
        font-size: 1rem;
        line-height: 1.5;

        &.link {
          color: $primary;
          text-decoration: none;
          transition: color 0.2s ease;

          &:hover {
            color: lighten($primary, 10%);
          }
        }
      }
    }
  }

  &__copyright {
    padding-top: 2rem;
    border-top: 1px solid rgba($white, 0.05);
    font-family: $font-secondary;
    font-size: 0.875rem;
    color: rgba($text-light, 0.4);
    text-align: center;
  }
}

// Media Queries for Desktop layout
@media (min-width: 768px) {
  .footer__legal-list {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .footer__legal-list {
    grid-template-columns: repeat(4, 1fr);
  }
}

// Animations
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
