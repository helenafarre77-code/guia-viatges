<template>
  <article class="card">
    <div class="imatge-container">
      <img :src="imatge" :alt="nom" class="imatge" />
      <div class="overlay"></div>
      <span class="card-etiqueta">DESTINACIÓ</span>
    </div>

    <div class="card-contingut">
      <h2>{{ nom }}</h2>

      <div class="linia"></div>

      <div class="info">
        <p><strong>País</strong> {{ pais }}</p>
        <p><strong>Continent</strong> {{ continent }}</p>
      </div>

      <p class="descripcio">{{ descripcio }}</p>
    </div>
  </article>
</template>

<script setup>
import { computed } from 'vue'

const props = defineProps({
  nom: String,
  pais: String,
  continent: String,
  descripcio: String
})

const imatge = computed(() => {
  const fotos = {
    'París': 'https://images.unsplash.com/photo-1502602898657-3e91760cbb34?auto=format&fit=crop&w=1200&q=80',
    'Barcelona': 'https://images.unsplash.com/photo-1583422409516-2895a77efded?auto=format&fit=crop&w=1200&q=80',
    'Tòquio': 'https://images.unsplash.com/photo-1540959733332-eab4deabeeaf?auto=format&fit=crop&w=1200&q=80'
  }

  return fotos[props.nom] || 'https://images.unsplash.com/photo-1507525428034-b723cf961d3e?auto=format&fit=crop&w=1200&q=80'
})
</script>

<style scoped>
.card {
  background: #ffffff;
  border: 1px solid #e9e3d9;
  border-radius: 22px;
  overflow: hidden;
  box-shadow: 0 8px 30px rgba(51, 61, 53, 0.08);
  transition: transform 0.35s ease, box-shadow 0.35s ease;
  height: 100%;
  display: flex;
  flex-direction: column;
}

.card:hover {
  transform: translateY(-8px);
  box-shadow: 0 18px 40px rgba(51, 61, 53, 0.14);
}

.imatge-container {
  position: relative;
  height: 230px;
  overflow: hidden;
}

.imatge {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
  transition: transform 0.5s ease;
}

.card:hover .imatge {
  transform: scale(1.05);
}

.overlay {
  position: absolute;
  inset: 0;
  background: linear-gradient(
    to top,
    rgba(20, 30, 24, 0.55),
    rgba(20, 30, 24, 0.08)
  );
}

.card-etiqueta {
  position: absolute;
  top: 18px;
  left: 18px;
  background: rgba(246, 242, 235, 0.88);
  color: #7b664d;
  padding: 7px 12px;
  border-radius: 999px;
  font-size: 10px;
  font-weight: 700;
  letter-spacing: 2px;
}

.card-contingut {
  padding: 28px;
  display: flex;
  flex-direction: column;
  flex: 1;
}

h2 {
  font-family: 'Playfair Display', serif;
  font-size: 32px;
  font-weight: 500;
  color: #333d35;
  margin: 0 0 18px;
}

.linia {
  height: 2px;
  width: 38px;
  background: #b69a78;
  margin-bottom: 22px;
}

.info {
  margin-bottom: 20px;
}

.info p {
  display: flex;
  justify-content: space-between;
  gap: 12px;
  margin: 10px 0;
  color: #777568;
  font-size: 14px;
}

.info strong {
  color: #536356;
  font-weight: 600;
}

.descripcio {
  padding-top: 18px;
  border-top: 1px solid #eee9e1;
  font-size: 15px;
  line-height: 1.8;
  color: #777568;
  margin: 0;
}

@media (max-width: 600px) {
  .imatge-container {
    height: 210px;
  }

  .card-contingut {
    padding: 22px;
  }

  h2 {
    font-size: 28px;
  }
}
</style>


