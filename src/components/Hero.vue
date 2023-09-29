<template>
    <section class="hero-wrapper">
        <div class="hero-img">
            <div class="hero-img-background"></div>
            <img src="../assets/illustration-hero.svg" alt="">
        </div>
        <div class="hero-text">
            <h1>A Simple Bookmark Manager</h1>
            <p>A clean and simple interface to organize your favourite websites. Open a new 
  browser tab and see your sites load instantly. Try it for free.</p>
            <div class="hero-text-btns">
                <button>Get it on Chrome</button>
                <button>Get it on Firefox</button>
            </div>
        </div>
    </section>
</template>

<script setup>

</script>

<style scoped>
section {
    padding: 3rem 0rem 3rem 2rem;
}
section .hero-img {
    position: relative;
    display: flex;
    align-items: center;justify-content: center;
}
section .hero-img .hero-img-background {
    position: absolute;
    width: 18.125rem;
    height: 12.75rem;
    z-index: -1;
    bottom: 0;
    right: 0;
    background-color: var(--Soft-Blue);
    border-bottom-left-radius: 4.5rem;
}
section .hero-img img {
    max-width: 100%;
    margin: 0 2rem 0 0;
}
section .hero-text {
    padding-right: 2rem;
    margin-top: 3.5rem;
    text-align: center;
}
section .hero-text h1 {
    color: var(--Very-Dark-Blue);
    line-height: 1.5;
    margin-bottom: 1.75rem;
}
section .hero-text p {
    color: var(--Grayish-Blue);
    margin-bottom: 2rem;
}
section .hero-text .hero-text-btns {
    display: flex;
    justify-content: space-between;
}
section .hero-text .hero-text-btns button{
    padding: 1.125rem;
    border: none;
    border-radius: 0.5rem;
    font-weight: 500;
    font-family: 'Rubik', sans-serif;
    cursor: pointer;
}
section .hero-text .hero-text-btns button:first-child {
    background-color: var(--Soft-Blue);
    color: white;
    transition: all 0.5s ease;
    border: 2px solid var(--Soft-Blue);
    box-shadow: 0px 5px 10px rgba(83, 104, 223, 0.2);
}
section .hero-text .hero-text-btns button:first-child:hover {
    background-color: transparent;
    color: var(--Soft-Blue);
}
section .hero-text .hero-text-btns button:last-child {
    box-shadow: 0 5px 5px rgba(0, 0, 0,0.2);
    border: 2px solid #E9E9ED;
    color: var(--Grayish-Blue);
    transition: all 0.5s ease;
}
section .hero-text .hero-text-btns button:last-child:hover {
    background-color: transparent;
    border-color: var(--Grayish-Blue);
}
@media screen and (min-width: 500px) {
    section .hero-text .hero-text-btns {
        justify-content: center;
        gap: 1rem;
    }
}
@media screen and (min-width: 1280px) {
    section {
        display: flex;
        flex-direction: row-reverse;
    }
    section .hero-text {
        text-align: left;
        padding-left: 8.625rem;
        padding-right: 0;
    }
    section .hero-text .hero-text-btns {
        justify-content: flex-start;
        gap: 1rem;
    }
    section .hero-img img {
        min-width: 657px;
    }
    section .hero-img .hero-img-background {
        height: 22.125rem;
        width: 31.125rem;
    }
    section .hero-text h1 {
        font-size: 3rem;
    }
    section .hero-text p {
        font-size: 1.25rem;
    }
}
</style>