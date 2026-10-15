<template>
  <header class="hero">
    <div class="hero-content">
      <span class="hero-etiqueta">✦ EXPLORE THE WORLD ✦</span>

      <h1>Guia de Viatges</h1>

      <div class="hero-linia"></div>

      <p>Descobreix destinacions increïbles arreu del món</p>
    </div>
  </header>
</template>

<style scoped>
.hero {
  background: linear-gradient(
    135deg,
    #333d35 0%,
    #4c5a49 60%,
    #677461 100%
  );
  color: #f6f2eb;
  text-align: center;
  padding: 85px 25px;
}

.hero-content {
  max-width: 900px;
  margin: 0 auto;
}

.hero-etiqueta {
  display: block;
  font-size: 12px;
  font-weight: 600;
  letter-spacing: 4px;
  color: #d9ba91;
  margin-bottom: 24px;
}

h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(42px, 6vw, 76px);
  font-weight: 500;
  letter-spacing: -1px;
  color: #f6f2eb;
  margin: 0 0 25px;
}

.hero-linia {
  width: 65px;
  height: 2px;
  background: #b69a78;
  margin: 0 auto 25px;
}

p {
  font-family: 'DM Sans', sans-serif;
  font-size: 17px;
  font-weight: 400;
  color: #e4ded2;
  margin: 0;
}

@media (max-width: 600px) {
  .hero {
    padding: 65px 20px;
  }

  .hero-etiqueta {
    font-size: 10px;
    letter-spacing: 2px;
  }

  p {
    font-size: 15px;
  }
}
</style>
