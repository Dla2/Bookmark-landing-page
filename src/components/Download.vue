<template>
    <section class="download-wrapper">
        <h2>Download the extension</h2>
        <p>We’ve got more browsers in the pipeline. Please do let us know if you’ve 
  got a favourite you’d like us to prioritize.</p>
        <div class="browser-cards">
            <DownloadComponent
                v-for="(content, index) in downloadSectionContent" :download-content="content" :key="index" 
            />
        </div>
    </section>
</template>

<script setup>
//import of component and content
import { downloadSectionContent } from '../content';
import DownloadComponent from './DownloadComponent.vue';
</script>

<style scoped>
.download-wrapper {
    padding: 7rem 2rem 0;
    text-align: center;
}
.download-wrapper h2 {
    color: var(--Very-Dark-Blue);
    margin-bottom: 1.5rem;
    font-weight: 500;
}
.download-wrapper p {
    color: var(--Grayish-Blue);
    margin-bottom: 3.625rem;
}
.download-wrapper .browser-cards {
    display: flex;
    flex-direction: column;
    gap: 3rem;
}
@media screen and (min-width: 800px) {
    .download-wrapper .browser-cards {
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
    }
}
@media screen and (min-width: 1280px) {
    .download-wrapper h2 {
        font-size: 2rem;
    }
    .download-wrapper p {
        margin-inline: 26rem;
        line-height: 1.5rem;
    }
    .download-wrapper .browser-cards {
        flex-direction: row;
        justify-content: center;
        gap: 2rem;
        position: relative;
    }
    .download-wrapper .browser-cards .browser-card:nth-child(2) {
        position: relative;
        top: 2.5rem;
    }
    .download-wrapper .browser-cards .browser-card:nth-child(3) {
        position: relative;
        top: 5rem;
    }
}
</style>