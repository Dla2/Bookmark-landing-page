<template>
    <div class="faq-wrapper" >
        <div class="faq-question" :class="{active: answerDisplay}">
            <p>{{ faq.question }}</p>
            <img src="../assets/icon-arrow.svg" alt="" @click="answerDisplay = !answerDisplay">
        </div>
        <Transition name="slide-down" mode="out-in">
            <div class="faq-answer" v-show="answerDisplay">
                <p>{{ faq.answer }}</p>
            </div>
        </Transition>
    </div>
</template>

<script setup>
//ref import
import { ref } from 'vue';
//reactive variable for displaying answer
const answerDisplay = ref(false)
//gets props from parent
defineProps({
    faq: {
        type: Object,
        required: true
    }
})
</script>

<style scoped>
.faq-wrapper {
    padding: 1.5rem 0rem;
    border-bottom: 1px solid var(--Grayish-Blue);
}
.faq-question {
    display: flex;
    align-items: center;
    justify-content: space-between;
    cursor: pointer;
}
.faq-question.active img {
    transform: rotateZ(180deg);
}
.faq-question p:hover {
    color: var(--Soft-Red);
}
.faq-question img {
    cursor: pointer;
    transition: transform 0.5s ease;
}

.faq-wrapper .faq-answer {
    margin-top: 1.5rem;
    text-align: left;
    color: var(--Grayish-Blue);
}

.slide-down-enter-from {
  opacity: 0;
  transform: translateY(-20px);
}
.slide-down-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}
.slide-down-enter-active,.slide-down-leave-active {
  transition: opacity 0.5s ease;
  transition: transform 0.5s ease;
}
.slide-down-enter-to {
    opacity: 1;
    transform: translateY(0px);
}
.slide-down-leave-from {
    opacity: 1;
    transform: translateY(0px);
}

</style>