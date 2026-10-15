# Guia de Viatges

## 1. Descripció del projecte

Guia de Viatges és una aplicació web desenvolupada amb Vue 3 que permet consultar informació sobre diferents destinacions turístiques del món.

L'aplicació mostra el nom de cada destinació, el país, el continent i una descripció, quan està disponible.

Les dades de les destinacions s'obtenen de Cloud Firestore, de manera que no estan escrites directament al codi de la pàgina.

## 2. Tecnologies utilitzades

- Vue 3: desenvolupament de la interfície i dels components.
- Vite: entorn de desenvolupament i generació de la versió de producció.
- Vue Router: navegació entre les diferents pàgines.
- Firebase Cloud Firestore: emmagatzematge i lectura de les destinacions.
- Firebase Hosting: publicació de l'aplicació a Internet.
- JavaScript i HTML.

## 3. Instal·lació i execució local

Per executar el projecte a l'ordinador, cal tenir instal·lats Node.js i npm.

Primer, descarregar o clonar el repositori i entrar a la carpeta del projecte.

Instal·lar les dependències:

```bash
npm install
```

Iniciar el servidor de desenvolupament:

```bash
npm run dev
```

Obrir al navegador l'adreça local que mostri la terminal, normalment http://localhost:5173/.

## 4. Generació i desplegament

Generar la versió de producció:

```bash
npm run build
```

Per publicar l'aplicació a Firebase Hosting, amb Firebase CLI i el projecte de Firebase configurats:

```bash
firebase deploy --only hosting
```

## 5. Components propis

L'aplicació utilitza tres components propis, a més d'App.vue:

- **SiteHeader.vue:** mostra la capçalera i el menú de navegació.
- **SiteFooter.vue:** mostra el peu de pàgina de l'aplicació.
- **DestinationCard.vue:** presenta la informació de cada destinació turística.

## 6. Comunicació entre components mitjançant props

A la vista **DestinacionsView.vue**, que actua com a component pare, es consulten les destinacions de Cloud Firestore.

Les dades obtingudes es passen al component fill **DestinationCard.vue** mitjançant props.

El component fill rep la informació de cada destinació i la utilitza per mostrar el nom, el país, el continent i la descripció, sense modificar directament les props.

D'aquesta manera es demostra la comunicació de pare a fill utilitzant dades reals de Firestore.

## 7. Navegació amb Vue Router

L'aplicació disposa de tres rutes principals:

- **Inici (/):** pàgina principal de benvinguda.
- **Destinacions (/destinacions):** mostra les destinacions turístiques obtingudes de Firestore.
- **Sobre (/sobre):** informació general sobre l'aplicació.

La navegació es gestiona amb Vue Router, utilitzant RouterLink i RouterView.

## 8. Connexió amb Cloud Firestore

L'aplicació utilitza una col·lecció anomenada **destinacions**.

Els documents contenen camps com:

- **nom:** nom de la destinació.
- **pais:** país on es troba.
- **continent:** continent de la destinació.
- **descripcio:** informació descriptiva.

La vista **DestinacionsView.vue** consulta aquesta col·lecció i mostra els resultats mitjançant el component DestinationCard.vue.

També es gestionen els estats de càrrega, els casos en què no hi ha dades i els possibles errors de lectura.

Les regles de seguretat de Firestore han de permetre les lectures necessàries sense habilitar escriptures públiques innecessàries.

## 9. Web publicada

https://guia-viatges-c17c5.firebaseapp.com/

## 10. Repositori GitHub

https://github.com/helenafarre77-code/guia-viatges
