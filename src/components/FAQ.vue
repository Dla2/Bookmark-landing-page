<template>
    <section class="faqs-wrapper">
        <h2>Frequently Asked Questions</h2>
        <p>Here are some of our FAQs. If you have any other questions you’d like 
  answered please feel free to email us.</p>
        <div class="faq-question">
            <FAQComponent v-for="(faq, index) in faqSectionContent" :faq="faq" :key="index"/>
        </div>
        <button>More Info</button>
    </section>
</template>

<script setup>
//imports of components and content
import FAQComponent from './FAQComponent.vue';
import { faqSectionContent } from '../content';

</script>

<style scoped>
.faqs-wrapper {
    text-align: center;
    padding: 9.125rem 2rem 7.75rem;
}
.faqs-wrapper h2 {
    color: var(--Very-Dark-Blue);
    margin-bottom: 2rem;
    font-weight: 500;
}
.faqs-wrapper p {
    color: var(--Grayish-Blue);
    margin-bottom: 3.5rem;
}
.faqs-wrapper .faq-question {
    margin-bottom: 3rem;
}
.faqs-wrapper button {
    background-color: var(--Soft-Blue);
    border: 2px solid var(--Soft-Blue);
    color: white;
    border-radius: 0.5rem;
    padding: 1.125rem 1.5rem;
    font-weight: 500;
    font-family: 'Rubik', sans-serif;
    transition: all 0.5s ease;
}
.faqs-wrapper button:hover {
    color: var(--Soft-Blue);
    background-color: transparent;
}
@media screen and (min-width: 1280px) {
    .faqs-wrapper {
        padding-top: 14.125rem;
    }
    .faqs-wrapper h2 {
        font-size: 2rem;
    }
    .faqs-wrapper p {
        margin-inline: 28rem;
        line-height: 1.5rem;
    }
    .faqs-wrapper .faq-question {
        margin-inline: 28rem;
    }
    .faqs-wrapper .faq-question .faq-wrapper:first-child {
        border-top: 1px solid var(--Grayish-Blue);
    }
}
</style>