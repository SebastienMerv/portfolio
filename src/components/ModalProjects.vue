<template>
    <section>
        <img class="logo" src="/logo/Sebastienmerv.png" alt="Logo">
        <img src="/website/oxiz.png" alt="Oxiz Studio">
        <img src="/website/old-portfolio.png" alt="Ancien portfolio">
        <img src="/website/caa.png" alt="Cercle Adapté Andennais ASBL">
        <img src="/website/wallonie.png" alt="Fêtes de Wallonie">
    </section>
</template>

<style scoped>
/* On fait que le section soit un modal, et qu'il affiche les images en grid avec .logo qui s'afiche au milieux des images */

section {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(255, 255, 255, 0.9);
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, 1fr);
    justify-items: center;
    align-items: center;
    z-index: 100;
    animation: slideIn 0.5s ease-in-out;
    transition: display 0.5s ease-in-out;
}

@keyframes slideIn {
    0% {
        transform: translateY(-20%);
    }

    100% {
        transform: translateY(0);
    }
}

section img {
    width: 60%;
    max-width: 500px;
    margin-bottom: 20px;
    box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.75);
}

section .logo {
    grid-column: 2;
    grid-row: 1;
    border-radius: 100%;
}
</style>