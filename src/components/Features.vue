<template>
    <section class="features-wrapper">
        <div class="features-text">
            <h2>Features</h2>
            <p>Our aim is to make it quick and easy for you to access your favourite websites. 
    Your bookmarks sync between your devices so you can access them on the go.</p>
            <ul class="features-navigation">
                <li
                    v-for="(featureContent, index) in featuresContent" :key="index" @click="changeTab(index)" :class="{active: index == currentTab }"
                ><span>{{ featureContent.title }}</span></li>
            </ul>
        </div>
        <div class="feature">
            <FeatureComponent 
                v-for="(featureContent, index) in featuresContent" :feature="featureContent" v-show="currentTab === index"
            />
        </div>
    </section>
</template>

<script setup>
//imports of components, content and ref
import FeatureComponent from './FeatureComponent.vue';
import { featuresContent } from '../content/index.js'
import { ref } from 'vue';
// reactive variable for the current tab of the feature
const currentTab = ref(0)
//function used to change the current tab variable and thus the tab
const changeTab = (index) => {
    currentTab.value = index
}

</script>

<style scoped>
.features-wrapper {
    text-align: center;
}
.features-wrapper .features-text {
    padding: 0 2rem 4.5rem;
}
.features-wrapper .features-text h2 {
    color: var(--Very-Dark-Blue);
}
.features-wrapper .features-text p {
    color: var(--Grayish-Blue);
}
.features-wrapper .features-text ul {
    margin-top: 2.625rem;
    list-style-type: none;
}
.features-wrapper .features-text ul li {
    cursor: pointer;
    border-top: 1px solid var(--Grayish-Blue);
}
.features-wrapper .features-text ul li:last-child {
    border-bottom: 1px solid var(--Grayish-Blue);
}
.features-wrapper .features-text ul li span {
    padding: 1.25rem 0;
    display: block;
    max-width: max-content;
    margin: 0 auto;
    color: var(--Grayish-Blue);
    transition: color 0.5s ease;
}
.features-wrapper .features-text ul li span:hover {
    color: var(--Soft-Red)
}
.features-wrapper .features-text ul li.active span {
    border-bottom: 4px solid var(--Soft-Red);
    color: black;
}
@media screen and (min-width: 1280px) {
    .features-wrapper {
        padding: 3rem 2rem 3rem 0rem;
    }
    .features-wrapper .features-text {
        width: fit-content;
        margin-inline: auto;
    }
    .features-wrapper .features-text h2 {
        font-weight: 500;
        font-size: 2rem;
    }
    .features-wrapper .features-text p {
        margin-inline: 26rem;
        line-height: 1.5rem;
    }
    .features-wrapper ul  {
        display: flex;
        align-items: center;
        justify-content: center;
    }
    .features-wrapper .features-text ul li {
        border-top: none;
        border-bottom: 1px solid var(--Grayish-Blue);
    }
    .features-wrapper .features-text ul li span {
        padding-inline: 2.5rem;
    }
}
</style>