<template>
    <div class="feature-wrapper">
        <div class="feature-img">
            <div class="feature-img-background"></div>
            <img :src="`src/assets/${feature.imgSrc}`" :alt="feature.altText">
        </div>
        <div class="feature-text">
            <h2>{{ feature.title }}</h2>
            <p>{{ feature.content }}</p>
            <button>{{ feature.btnText }}</button>
        </div>
    </div>
</template>

<script setup>
//gets the props(content) from the parent
defineProps({
    feature: {
        type: Object,
        required: true
    }
})
</script>

<style scoped>
.feature-wrapper .feature-img {
    position: relative;
    padding: 0 2rem 2.35rem;
}
.feature-wrapper .feature-img img {
    max-width: 100%;
}
.feature-wrapper .feature-img .feature-img-background {
    position: absolute;
    background-color: var(--Soft-Blue);
    height: 12.75rem;
    width: 17.875rem;
    bottom: 0;
    left: 0;
    z-index: -1;
    border-bottom-right-radius: 4.5rem;
}
.feature-wrapper .feature-text {
    padding: 3rem 2rem;
    text-align: center;
}
.feature-wrapper .feature-text h2 {
    margin-bottom: 1.5rem;
    color: var(--Very-Dark-Blue);
}
.feature-wrapper .feature-text p {
    color: var(--Grayish-Blue);
}
.feature-wrapper .feature-text button {
    display: none;
    padding: 1rem 1.5rem;
    background-color: var(--Soft-Blue);
    color: white;
    font-family: 'Rubik', sans-serif;
    border: 2px solid var(--Soft-Blue);
    border-radius: 0.5rem;
    cursor: pointer;
    transition: all 0.5s ease;
}
.feature-wrapper .feature-text button:hover {
    color: var(--Soft-Blue);
    background-color: transparent;
}
@media screen and (min-width: 1280px) {
    .feature-wrapper {
        display: flex;
        gap: 2.375rem;
    }
    .feature-wrapper .feature-img {
        padding-left: 8.625rem;
        padding-right: 0;
        min-width: max-content;
    }
    .feature-wrapper .feature-img .feature-img-background {
        min-height: 19.5rem;
        min-width: 33rem;
        border-bottom-right-radius: 5rem;
    }
    .feature-wrapper .feature-text {
        text-align: left;
        padding-left: 4rem;
        padding-right: 8.625rem;
    }
    .feature-wrapper .feature-text h2 {
        font-weight: 500;
        font-size: 2rem;
    }
    .feature-wrapper .feature-text p {
        line-height: 1.5rem;
        margin-bottom: 2rem;
    }
    .feature-wrapper .feature-text button {
        display: block;
    }
}
</style>