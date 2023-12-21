<script setup>
import { ref } from 'vue'
import ModalCV from '@/components/ModalCV.vue'
import ModalProjects from './components/ModalProjects.vue';


const Resume = ref(false);
const DisplayedResume = ref(false);
const Projects = ref(false);

const displayResume = () => {
  if (DisplayedResume.value == false) {
    Resume.value = true;
    DisplayedResume.value = true;
  } else {
    Resume.value = false;
    DisplayedResume.value = false;
  };
}

const displayProjects = () => {
  if (Projects.value == false) {
    Projects.value = true;
  } else {
    Projects.value = false;
  };
}

// If on clique a côté d'une des images de ModalProjects, on ferme le modal

window.addEventListener('click', function (event) {
  if (event.target == document.querySelector('section')) {
    Projects.value = false;
  }
})

</script>

<template>
  <ModalCV @click="displayResume()" v-if="Resume" />
  <ModalProjects v-if="Projects" />
  <main>
    <header>
      <img src="/logo/Sebastienmerv.png" alt="Logo de Sébastien Merveille" class="logo">
      <div class="content">
        <h1>Sébastien Merveille</h1>
        <h2>Web Developer</h2>
        <p>Passionate web developer, I am currently in the 2nd year of a work-study program with <br><a target="_blank"
            href="https://andenne.be">Ville d'Andenne</a></p>
        <div class="actions">
          <button @click="displayResume()">Resume</button>
          <button @click="displayProjects()">Projects</button>
        </div>
        <div class="socials">
          <a target="_blank" href="https://github.com/SebastienMerv"><i class="fa-brands fa-github"></i></a>
          <a target="_blank" href="https://linkedin.com/in/SebastienMerv"><i class="fa-brands fa-linkedin"></i></a>
          <a target="_blank" href="https://twitter.com/SebastienMerv"><i class="fa-brands fa-twitter"></i></a>
          <a target="_blank" href="https://instagram.com/SebastienMerv"><i class="fa-brands fa-instagram"></i></a>
          <a href="tel:+32470287582"><i class="fa-solid fa-phone"></i></a>
          <a href="mailto:info@sebastienmerv.be"><i class="fa-solid fa-envelope"></i></a>
        </div>
      </div>
    </header>
  </main>
</template>

<style scoped>
@font-face {
  font-family: 'Doodle';
  src: url('@/assets/Doodle.ttf') format('truetype');
}

@font-face {
  font-family: 'Lato';
  src: url('@/assets/Lato.ttf') format('truetype');
}

header {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 2rem;
  /* Réduire la marge pour les écrans plus petits */
  animation: slideIn 0.5s ease-in-out;
}

@keyframes slideIn {
  0% {
    transform: translateY(-20%);
  }

  100% {
    transform: translateY(0);
  }
}

/* Ajouter une media query pour les écrans plus petits */
@media only screen and (max-width: 900px) {
  header {
    flex-direction: column;
    /* Aligner les éléments en colonne pour les écrans plus petits */
    text-align: center;
    /* Centrer le texte */
  }

  header img {
    margin-right: 0;
    width: 200px;
    /* Supprimer la marge à droite pour les écrans plus petits */
    margin-bottom: 1rem;
    /* Ajouter une marge en bas pour les écrans plus petits */
  }

  header button {
    margin-right: 0;
    /* Supprimer la marge à droite pour les écrans plus petits */
    margin-bottom: 1rem;
    /* Ajouter une marge en bas pour les écrans plus petits */
  }

  header .socials {
    justify-content: center;
  }
}

header h1,
header h2 {
  font-family: 'Doodle';
}

header p {
  font-size: 1.2rem;
  margin-bottom: 20px;
  font-family: 'Lato';
}

header img {
  border-radius: 100%;
  margin-right: 50px;
  box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.75);
}

header button {
  background-color: #f5f5f5;
  border: 1px solid #f5f5f5;
  border-radius: 5px;
  padding: 10px 20px;
  margin-right: 20px;
  font-size: 1.2rem;
  font-weight: bold;
  cursor: pointer;
}

header .socials {
  margin-top: 20px;
  display: flex;
  flex-direction: row;
}

header .socials i {
  font-size: 3rem;
  margin-right: 20px;
  color: black;
  cursor: pointer;
}
</style>
