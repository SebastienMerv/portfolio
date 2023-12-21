<script setup>


function downloadResume() {
    window.open("/CV.jpg", "_blank");
}

</script>

<template>
    <section>
        <img src="/CV.jpg" alt="Resume of Sébastien Merveille">
        <button @click="downloadResume()">Télécharger</button>
    </section>
</template>

<style scoped>
section {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(255, 255, 255, 0.9);
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    z-index: 100;
    animation: slideIn 0.5s ease-in-out;
    transition: display 0.5s ease-in-out;
}

section img {
    width: 50%;
    max-width: 500px;
    margin-bottom: 20px;
    box-shadow: 0px 0px 10px 0px rgba(0, 0, 0, 0.75);
}

@keyframes slideIn {
    from {
        transform: translateY(20%);
    }

    to {
        transform: translateY(0);
    }
}

@keyframes slideOut {
    from {
        transform: translateY(0);
    }

    to {
        transform: translateY(20%);
    }
}
</style>