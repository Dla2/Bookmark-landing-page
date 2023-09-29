<template>
    <section class="footer">
        <img src="../assets/logo-bookmark-white-2.svg" alt="">
        <ul>
            <li>FEATURES</li>
            <li>PRICING</li>
            <li>CONTACT</li>
        </ul>
        <div class="icons-wrapper">
            <img src="../assets/icon-twitter.svg" alt="" class="icon">
            <img src="../assets/icon-facebook.svg" alt="" class="icon">
        </div>
    </section>
</template>

<script setup>

</script>

<style scoped>
.footer {
    background-color: var(--Very-Dark-Blue);
    text-align: center;
    padding-block: 2.5rem;
    color: white;
}
.footer img {
    margin-bottom: 2.5rem;
}
.footer ul {
    display: flex;
    flex-direction: column;
    gap: 2.375rem;
    margin-bottom: 3.125rem;
    list-style-type: none
}
.footer ul li {
    letter-spacing: 0.2rem;
    cursor: pointer;
    transition: color 0.5s ease;
}
.footer ul li:hover {
    color: var(--Soft-Red);
}
.footer .icons-wrapper .icon:nth-child(1) {
    margin-right: 2.5rem;
}
@media screen and (min-width: 1280px) {
    .footer {
        display: flex;
        padding-inline: 10.625rem;
    }
    .footer img {
        margin-bottom: 0;
        margin-right: 4rem;
    }
    .footer ul {
        flex-direction: row;
        margin-bottom: 0;
        align-items: center;
    }
    .footer .icons-wrapper {
        margin-left: auto;
        display: flex;
    }
    .footer .icons-wrapper .icon:nth-child(2) {
        margin-right: 0;
    }
}
</style>