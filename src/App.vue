
<script setup>
import SiteHeader from './components/SiteHeader.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
  <div class="app">
    <SiteHeader />

    <nav class="menu-principal">
      <RouterLink to="/">Inici</RouterLink>
      <RouterLink to="/destinacions">Destinacions</RouterLink>
      <RouterLink to="/sobre">Sobre</RouterLink>
    </nav>

    <main class="container">
      <RouterView />
    </main>

    <SiteFooter />
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Playfair+Display:wght@400;500;600;700&display=swap');

:root {
  font-family: 'DM Sans', sans-serif;
  color: #333d35;
  background: #f6f2eb;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  background: #f6f2eb;
  color: #333d35;
  font-family: 'DM Sans', sans-serif;
  line-height: 1.7;
}

.app {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

h1, h2, h3 {
  font-family: 'Playfair Display', serif;
  color: #333d35;
  line-height: 1.25;
}

.menu-principal {
  background: #333d35;
  padding: 20px 24px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 45px;
  flex-wrap: wrap;
}

.menu-principal a {
  color: #f6f2eb;
  text-decoration: none;
  font-size: 14px;
  font-weight: 600;
  letter-spacing: 1px;
  transition: color 0.3s ease;
}

.menu-principal a:hover,
.menu-principal a.router-link-exact-active {
  color: #d9ba91;
}

.container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 65px 30px;
  flex: 1;
}

button {
  font-family: 'DM Sans', sans-serif;
  cursor: pointer;
}

@media (max-width: 600px) {
  .menu-principal {
    gap: 22px;
    padding: 18px 12px;
  }

  .menu-principal a {
    font-size: 12px;
  }

  .container {
    padding: 40px 20px;
  }
}
</style>
