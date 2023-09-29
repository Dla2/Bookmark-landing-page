<template>
    <nav class="mobile-navbar-wrapper">
        <div class="mobile-navbar" :class="{dissapear: navbarIsActive}">
            <a href="#"><img src="../assets/logo-bookmark.svg" alt="" ></a>
            <button @click="navbarIsActive = !navbarIsActive"><img src="../assets/icon-hamburger.svg" alt=""></button>
        </div>
        <Transition name="fade-left" mode="out-in">
            <div class="mobile-navbar-active-wrapper" v-show="navbarIsActive">
                <div class="mobile-navbar-active">
                    <a href="#"><img src="../assets/logo-bookmark-white.svg" alt=""></a>
                    <button @click="navbarIsActive = !navbarIsActive"><img src="../assets/icon-close.svg" alt=""></button>
                </div>
                <div class="mobile-navbar-active-navigations">
                    <ul>
                        <li><a href="#">FEATURES</a></li>
                        <li><a href="#">PRICING</a></li>
                        <li><a href="#">CONTACT</a></li>
                        <li><button class="mobile-btn">LOGIN</button></li>
                    </ul>
                    <div class="social-icons">
                        <img src="../assets/icon-facebook.svg" alt="">
                        <img src="../assets/icon-twitter.svg" alt="">
                    </div>
                </div>
            </div>
        </Transition>
    </nav>
    <nav class="desktop-navbar">
        <a href="#"><img src="../assets/logo-bookmark.svg" alt=""></a>
        <ul>
            <li><a href="#">FEATURES</a></li>
            <li><a href="#">PRICING</a></li>
            <li><a href="#">CONTACT</a></li>
            <li class="btn">LOGIN</li>
        </ul>
    </nav>
</template>

<script setup>
import { ref } from 'vue';
//reactive variable for the mobile navbar 
const navbarIsActive = ref(false)
</script>

<style scoped>
.mobile-navbar-wrapper .mobile-navbar{
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 2.5rem 2rem;
    opacity: 1;
    transition: opacity 0.9s ease ;
}
.mobile-navbar-wrapper .mobile-navbar.dissapear {
    opacity: 0;
}
.mobile-navbar-wrapper .mobile-navbar button {
    background: none;
    border: none;
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper {
    background-color:  rgba(37, 43, 70, 0.95);
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    z-index: 10;
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper .mobile-navbar-active  {
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 2.5rem 2rem;
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper .mobile-navbar-active button {
    background: none;
    border: none;
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper .mobile-navbar-active-navigations {
    display: flex;
    flex-direction: column;
    gap: 13.75rem;
    position: absolute;
    z-index: 10;
    left: 0;
    right: 0;
    background-color:  rgba(37, 43, 70, 0.95);
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper .mobile-navbar-active-navigations ul {
    list-style-type: none;
    text-align: center;
    padding-inline: 2rem;
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper .mobile-navbar-active-navigations ul li {
    padding-top: 1.5rem;
    padding-bottom: 1.5rem;
    border-top: 1px solid var(--Grayish-Blue);
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper .mobile-navbar-active-navigations ul li a {
    text-decoration: none;
    color: white;
    letter-spacing: 0.25rem;
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper .mobile-navbar-active-navigations ul .mobile-btn {
    padding: 0.875rem 0rem;
    width: 100%;
    background-color: transparent;
    border: 2px solid white;
    border-radius: 0.35rem;
    color: white;
    font-weight: 500;
    font-size: large;
    letter-spacing: 0.25rem;
}
.mobile-navbar-wrapper .mobile-navbar-active-wrapper .mobile-navbar-active-navigations .social-icons {
    align-self: center;
    display: flex;
    gap: 2.5rem;
    margin-bottom: 3rem;
}

.fade-left-enter-from, .fade-left-leave-to {
    opacity: 0;
    transform: translateX(20px);
}
.fade-left-enter-to, .fade-left-leave-from {
    opacity: 1;
    transform: translateX(0);
}
.fade-left-enter-active, .fade-left-leave-active {
    transition: all 0.9s ease;
}

.desktop-navbar {
    padding: 3.5rem 10.625rem;
    display: none;
    align-items: center;
    justify-content: space-between;
}
.desktop-navbar ul {
    display: flex;
    gap: 3rem;
    list-style-type: none;
    align-items: center;
}
.desktop-navbar ul li a {
    text-decoration: none;
    color: var(--Very-Dark-Blue);
    transition: all 0.5s ease-in;
}
.desktop-navbar ul li a:hover {
    color: var(--Soft-Red);
}
.desktop-navbar ul .btn {
    border: 3px solid var(--Soft-Red);
    background-color: var(--Soft-Red);
    color: white;
    padding: 0.875rem 2rem;
    border-radius: 0.5rem;
    cursor: pointer;
    transition: all 0.5s ease-in;
}
.desktop-navbar ul li:hover {
    color: var(--Soft-Red);
    background-color: white;
}

@media screen and (min-width: 1280px) {
    .mobile-navbar-wrapper {
        display: none;
    }
    .desktop-navbar {
        display: flex;
    }
}
</style>