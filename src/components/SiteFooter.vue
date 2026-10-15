<template>
  <footer class="footer">
    <div class="footer-contingut">
      <h2>Guia de Viatges</h2>

      <span class="footer-etiqueta">
        DESCOBREIX · EXPLORA · VIATJA
      </span>

      <div class="footer-linia"></div>

      <p class="footer-descripcio">
        Descobreix destinacions extraordinàries arreu del món.
      </p>

      <div class="footer-separador"></div>

      <p class="footer-copyright">
        © 2026 Guia de Viatges · Web creada amb Vue i Firebase
      </p>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  background: #333d35;
  color: #f6f2eb;
  text-align: center;
  padding: 65px 25px 25px;
  margin-top: 30px;
}

.footer-contingut {
  max-width: 1000px;
  margin: 0 auto;
}

h2 {
  font-family: 'Playfair Display', serif;
  font-size: 34px;
  font-weight: 500;
  color: #f6f2eb;
  margin: 0 0 12px;
}

.footer-etiqueta {
  display: block;
  color: #d9ba91;
  font-size: 11px;
  font-weight: 600;
  letter-spacing: 3px;
}

.footer-linia {
  width: 45px;
  height: 2px;
  background: #b69a78;
  margin: 25px auto;
}

.footer-descripcio {
  color: #e4ded2;
  font-size: 15px;
  line-height: 1.8;
}

.footer-separador {
  height: 1px;
  background: rgba(255, 255, 255, 0.15);
  margin: 45px 0 20px;
}

.footer-copyright {
  color: #c9c4ba;
  font-size: 12px;
  letter-spacing: 0.3px;
  margin: 0;
}

@media (max-width: 600px) {
  .footer {
    padding: 45px 20px 25px;
  }

  h2 {
    font-size: 28px;
  }

  .footer-etiqueta {
    font-size: 9px;
    letter-spacing: 2px;
  }
}
</style>
