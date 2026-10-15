<template>
  <section class="destinacions-page">

    <div class="seccio-titol">
      <span class="etiqueta">✦ EXPLORA EL MÓN ✦</span>
      <h1>Les nostres destinacions</h1>
      <p>
        Descobreix racons extraordinaris i deixa't inspirar
        per al teu pròxim viatge.
      </p>
      <div class="linia-decorativa"></div>
    </div>

    <p v-if="loading" class="missatge">
      Carregant destinacions...
    </p>

    <p v-else-if="error" class="missatge">
      No s'han pogut carregar les destinacions.
    </p>

    <p v-else-if="destinacions.length === 0" class="missatge">
      Encara no hi ha destinacions disponibles.
    </p>

    <div v-else class="destinacions-grid">
      <DestinationCard
        v-for="dest in destinacions"
        :key="dest.id"
        :nom="dest.nom"
        :pais="dest.pais"
        :continent="dest.continent"
        :descripcio="dest.descripcio"
      />
    </div>

  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { collection, getDocs } from 'firebase/firestore'
import { db } from '../firebase'
import DestinationCard from '../components/DestinationCard.vue'

const destinacions = ref([])
const loading = ref(true)
const error = ref(false)

onMounted(async () => {
  try {
    const snapshot = await getDocs(collection(db, 'destinacions'))

    destinacions.value = snapshot.docs.map(doc => ({
      id: doc.id,
      ...doc.data()
    }))
  } catch (err) {
    console.error(err)
    error.value = true
  } finally {
    loading.value = false
  }
})
</script>

<style scoped>
.destinacions-page {
  width: 100%;
}

.seccio-titol {
  text-align: center;
  margin-bottom: 55px;
}

.etiqueta {
  color: #b69a78;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 3px;
}

h1 {
  font-family: 'Playfair Display', serif;
  font-size: clamp(32px, 5vw, 52px);
  font-weight: 500;
  color: #333d35;
  margin: 15px 0;
}

.seccio-titol p {
  font-size: 16px;
  color: #777568;
  max-width: 550px;
  margin: 0 auto;
  line-height: 1.8;
}

.linia-decorativa {
  width: 55px;
  height: 2px;
  background: #b69a78;
  margin: 28px auto 0;
}

.destinacions-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 28px;
  align-items: stretch;
}

.missatge {
  text-align: center;
  padding: 40px;
  background: #ffffff;
  color: #333d35;
  border-radius: 16px;
}

@media (max-width: 900px) {
  .destinacions-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 600px) {
  .destinacions-grid {
    grid-template-columns: 1fr;
    gap: 20px;
  }

  .seccio-titol {
    margin-bottom: 35px;
  }
}
</style>

