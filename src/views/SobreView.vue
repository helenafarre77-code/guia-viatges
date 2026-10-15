<template>
  <section class="sobre">

    <div class="sobre-capcalera">
      <span class="etiqueta">EL NOSTRE PROJECTE</span>

      <h1>Molt més que destinacions.</h1>

      <div class="linia"></div>

      <p class="introduccio">
        Una guia creada per descobrir llocs extraordinaris,
        explorar noves cultures i inspirar la teva pròxima aventura.
      </p>
    </div>

    <div class="sobre-contingut">
      <h2>Descobreix la nostra guia</h2>

      <p>
        Guia de Viatges és una aplicació web que permet
        explorar diferents destinacions turístiques del món.
      </p>

      <p>
        El projecte ha estat desenvolupat amb Vue 3 i Vue Router,
        que permeten crear una experiència de navegació
        senzilla i dinàmica.
      </p>

      <p>
        Les destinacions es carreguen directament des de
        Cloud Firestore i l'aplicació està publicada
        a Internet mitjançant Firebase Hosting.
      </p>
    </div>

    <div class="tecnologies">
      <div class="tecnologia">
        <h3>Vue 3</h3>
        <p>Interfície dinàmica</p>
      </div>

      <div class="tecnologia">
        <h3>Cloud Firestore</h3>
        <p>Gestió de dades</p>
      </div>

      <div class="tecnologia">
        <h3>Firebase Hosting</h3>
        <p>Publicació web</p>
      </div>
    </div>

    <RouterLink to="/destinacions" class="boto">
      Descobreix les destinacions
      <span aria-hidden="true">→</span>
    </RouterLink>

  </section>
</template>

<style scoped>
.sobre {
  background: #ffffff;
  border: 1px solid #e9e3d9;
  padding: 65px 55px;
  border-radius: 22px;
  box-shadow: 0 10px 35px rgba(51, 61, 53, 0.06);
}

.sobre-capcalera {
  text-align: center;
  max-width: 750px;
  margin: 0 auto 55px;
}

.etiqueta {
  font-size: 11px;
  letter-spacing: 3px;
  font-weight: 700;
  color: #b69a78;
}

h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(34px, 5vw, 52px);
  font-weight: 500;
  color: #333d35;
  margin: 18px 0;
}

.linia {
  width: 55px;
  height: 2px;
  background: #b69a78;
  margin: 25px auto;
}

.introduccio {
  color: #777568;
  font-size: 17px;
  line-height: 1.9;
}

.sobre-contingut {
  max-width: 750px;
  margin: 0 auto 45px;
}

h2 {
  font-family: 'Playfair Display', serif;
  color: #333d35;
  font-size: 30px;
  font-weight: 500;
}

.sobre-contingut p {
  color: #777568;
  font-size: 15px;
  line-height: 1.9;
}

.tecnologies {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 20px;
  margin: 45px 0;
}

.tecnologia {
  background: #f6f2eb;
  border-radius: 14px;
  padding: 25px 15px;
  text-align: center;
}

.tecnologia h3 {
  color: #333d35;
  font-family: 'Playfair Display', serif;
  font-size: 22px;
  font-weight: 500;
  margin: 0 0 8px;
}

.tecnologia p {
  color: #777568;
  font-size: 13px;
  margin: 0;
}

.boto {
  display: flex;
  width: fit-content;
  margin: 0 auto;
  align-items: center;
  gap: 15px;
  padding: 15px 28px;
  background: #333d35;
  color: #f6f2eb;
  text-decoration: none;
  border-radius: 50px;
  font-size: 14px;
  font-weight: 600;
  transition: background 0.3s, transform 0.3s;
}

.boto:hover {
  background: #536356;
  transform: translateY(-3px);
}

@media (max-width: 700px) {
  .sobre {
    padding: 40px 22px;
  }

  .tecnologies {
    grid-template-columns: 1fr;
    gap: 12px;
  }

  .sobre-capcalera {
    margin-bottom: 35px;
  }
}
</style>
