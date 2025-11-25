<script setup lang="ts">
import NavHeader from './components/NavHeader.vue'
import AppCard from './components/AppCard.vue'
import QuickAccessCard from './components/QuickAccessCard.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <div class="app-container">
    <NavHeader />
    
    <main class="main-content">
      <!-- Hero Section -->
      <section class="hero-section">
        <h1 class="hero-title">App Resources & Documentation</h1>
        <p class="hero-subtitle">Privacy policies, configuration guides, and FAQs for our apps</p>
        <span class="preview-badge">Preview</span>
      </section>

      <!-- Our Apps Section -->
      <section id="apps" class="apps-section">
        <div class="section-header">
          <h2 class="section-title">Our Apps</h2>
          <p class="section-subtitle">Select an app to access its documentation</p>
        </div>
        
        <div class="apps-grid">
          <AppCard
            title="VaultTrak"
            description="Secure time tracking for professionals"
            :links="[
              { label: 'Privacy Policy', url: '/contentvault_app-docs/docs/VaultTrak/PrivacyPolicy.html' },
              { label: 'Terms & Conditions', url: '/contentvault_app-docs/docs/VaultTrak/TermsAndConditions.html' },
              { label: 'Configuration Guide', url: '/contentvault_app-docs/docs/VaultTrak/ConfigurationGuide.html' },
              { label: 'FAQ', url: '/contentvault_app-docs/docs/VaultTrak/FAQ.html' },
              { label: 'Support', url: '/contentvault_app-docs/docs/VaultTrak/Support.html' }
            ]"
          />
          
          <AppCard
            title="Porch Plates"
            description="Local home-cooked meal marketplace and family meal planning"
            :links="[
              { label: 'Privacy Policy', url: '/contentvault_app-docs/docs/PorchPlates/PrivacyPolicy.html' }
            ]"
          />
          
          <AppCard
            title="More Coming Soon"
            description="Additional apps in development"
            :links="['More apps coming soon']"
            :is-beta="true"
          />
        </div>
      </section>

      <!-- Quick Access Section -->
      <section class="quick-access-section">
        <div class="section-header">
          <h2 class="section-title">Quick Access</h2>
          <p class="section-subtitle">Browse documentation by category</p>
        </div>
        
        <div class="quick-access-grid">
          <QuickAccessCard
            title="All Privacy Policies"
            description="View privacy policies for all apps"
            icon="privacy"
          />
          
          <QuickAccessCard
            title="Terms of Service"
            description="Consolidated terms and agreements"
            icon="terms"
          />
          
          <QuickAccessCard
            title="Configuration Guides"
            description="Setup and configuration instructions"
            icon="config"
          />
          
          <QuickAccessCard
            title="FAQs"
            description="Searchable knowledge base"
            icon="faq"
          />
        </div>
      </section>
    </main>

    <FooterSection />
  </div>
</template>

<style scoped>
.app-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background-color: #0a0a0a;
}

.main-content {
  flex: 1;
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 2rem;
  width: 100%;
}

.hero-section {
  text-align: center;
  padding: 4rem 0 3rem;
  position: relative;
}

.hero-title {
  font-size: 3rem;
  font-weight: 700;
  color: #fff;
  margin: 0 0 1rem 0;
  letter-spacing: -0.02em;
}

.hero-subtitle {
  font-size: 1.125rem;
  color: #6b7280;
  margin: 0 0 1.5rem 0;
}

.preview-badge {
  display: inline-block;
  padding: 0.375rem 1rem;
  background-color: #fff;
  color: #0a0a0a;
  font-size: 0.875rem;
  font-weight: 600;
  border-radius: 6px;
}

.apps-section,
.quick-access-section {
  padding: 3rem 0;
}

.section-header {
  text-align: center;
  margin-bottom: 2.5rem;
}

.section-title {
  font-size: 1.875rem;
  font-weight: 600;
  color: #fff;
  margin: 0 0 0.5rem 0;
}

.section-subtitle {
  color: #6b7280;
  font-size: 1rem;
  margin: 0;
}

.apps-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  gap: 1.5rem;
  margin-bottom: 2rem;
}

.quick-access-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
}

@media (max-width: 768px) {
  .hero-title {
    font-size: 2rem;
  }
  
  .hero-subtitle {
    font-size: 1rem;
  }
  
  .apps-grid,
  .quick-access-grid {
    grid-template-columns: 1fr;
  }
  
  .main-content {
    padding: 0 1rem;
  }
}
</style>
