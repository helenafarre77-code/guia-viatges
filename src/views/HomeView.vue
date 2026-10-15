<template>
  <section class="home">

    <div class="portada">
      <img
        src="https://images.unsplash.com/photo-1533105079780-92b9be482077?auto=format&fit=crop&w=1600&q=85"
        alt="Paisatge mediterrani amb vistes al mar"
        class="portada-imatge"
      />
      <div class="portada-overlay">
        <span class="portada-etiqueta">
          DESCOBREIX · EXPLORA · VIATJA
        </span>
        <h1>El món t'espera.</h1>
        <p>Hi ha llocs que es visiten i llocs que es recorden.</p>
      </div>
    </div>

    <div class="presentacio">
      <span class="etiqueta">UNA NOVA MANERA DE DESCOBRIR</span>

      <h2>Viatjar és descobrir.</h2>

      <div class="linia"></div>

      <p>
        Explora destinacions extraordinàries, descobreix noves cultures
        i deixa't inspirar per al teu pròxim viatge.
        Cada destinació és una història que espera ser viscuda.
      </p>

      <RouterLink to="/destinacions" class="btn">
        Explora destinacions
        <span aria-hidden="true">→</span>
      </RouterLink>
    </div>

  </section>
</template>

<style scoped>
.home {
  width: 100%;
}

.portada {
  position: relative;
  height: 460px;
  border-radius: 22px;
  overflow: hidden;
}

.portada-imatge {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.portada::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(20, 30, 24, 0.75),
    rgba(20, 30, 24, 0.05)
  );
}

.portada-overlay {
  position: absolute;
  z-index: 1;
  bottom: 48px;
  left: 50px;
  right: 40px;
  color: white;
}

.portada-etiqueta {
  font-size: 11px;
  letter-spacing: 3px;
  font-weight: 700;
  color: #e5c8a0;
}

.portada h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(38px, 6vw, 70px);
  font-weight: 500;
  color: white;
  margin: 12px 0;
}

.portada p {
  color: #f6f2eb;
  font-size: 16px;
}

.presentacio {
  max-width: 750px;
  margin: 75px auto 35px;
  text-align: center;
}

.etiqueta {
  color: #b69a78;
  font-size: 11px;
  font-weight: 700;
  letter-spacing: 3px;
}

.presentacio h2 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(34px, 5vw, 50px);
  font-weight: 500;
  color: #333d35;
  margin: 18px 0;
}

.linia {
  height: 2px;
  width: 55px;
  background: #b69a78;
  margin: 25px auto;
}

.presentacio p {
  color: #777568;
  font-size: 16px;
  line-height: 1.9;
  margin-bottom: 30px;
}

.btn {
  display: inline-flex;
  align-items: center;
  gap: 18px;
  background: #333d35;
  color: #f6f2eb;
  padding: 15px 28px;
  border-radius: 50px;
  text-decoration: none;
  font-weight: 600;
  font-size: 14px;
  transition: background 0.3s, transform 0.3s;
}

.btn:hover {
  background: #536356;
  transform: translateY(-3px);
}

@media (max-width: 600px) {
  .portada {
    height: 380px;
    border-radius: 15px;
  }

  .portada-overlay {
    left: 25px;
    right: 20px;
    bottom: 30px;
  }

  .portada p {
    font-size: 14px;
  }

  .presentacio {
    margin: 55px auto 20px;
  }
}
</style>
