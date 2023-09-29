<template>
    <div class="browser-card">
        <img :src="`src/assets/${downloadContent.imgSrc}`" :alt="downloadContent.altText">
        <h3>{{ downloadContent.title }}</h3>
        <p>{{ downloadContent.content }}</p>
        <button>{{ downloadContent.btnText }}</button>
    </div>
</template>

<script setup>
//gets props from parent
defineProps({
    downloadContent: {
        type: Object,
        required: true
    }
})
</script>

<style scoped>
.browser-card {
    text-align: center;
    box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
    border-radius: 0.5rem;
    padding: 1.5rem 0;
    background: url(../assets/bg-dots.svg);
    background-repeat: no-repeat;
    background-size: contain;
    background-position: center 16rem;
}
.browser-card img {
    margin-bottom: 2.25rem;
}
.browser-card h3 {
    margin-bottom: 1rem;
    color: var(--Very-Dark-Blue);
    font-weight: 500;
}
.browser-card p {
    margin-bottom: 4.25rem;
    color: var(--Grayish-Blue);
}
.browser-card button {
    cursor: pointer;
    color: white;
    background-color: var(--Soft-Blue);
    font-family: "Rubik", sans-serif;
    font-weight: 500;
    border: 2px solid var(--Soft-Blue);
    padding: 1rem 2rem;
    border-radius: 0.5rem;
    transition: all 0.5s ease;
}
.browser-card button:hover {
    color: var(--Soft-Blue);
    background-color: transparent;
}
@media screen and (min-width: 800px) {
    .browser-card {
        padding-inline: 1.75rem;
    }
}
</style>