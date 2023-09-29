<template>
    <section class="signup-wrapper">
        <p>35,000+ ALREADY JOINED</p>
        <h2>Stay up-to-date with what we’re doing</h2>
        <div class="signup">
            <div class="input-wrapper" :class="{ error : hasError}">
                <div>
                    <input type="email" v-bind="email" placeholder="Enter your email address">
                    <img src="../assets/icon-error.svg" alt="">
                </div>
                <span v-show="errors">{{ errors.email }}</span>
            </div>
            <button>Contact Us</button>
        </div>
    </section>
</template>

<script setup>
import { useForm } from 'vee-validate';
import { computed } from 'vue';
import * as yup from 'yup';

const { values, defineInputBinds, errors }= useForm({
    validationSchema: yup.object({
        email: yup.string().required().email()
    })
});
const email = defineInputBinds('email')

const hasError = computed(() => {
    if(errors.value.email) {
        return true
    } else {
        return false
    }
})
</script>

<style scoped>
.signup-wrapper {
    background-color: var(--Soft-Blue);
    text-align: center;
    padding-block: 4.625rem 3.75rem;
    color: white;
}
.signup-wrapper p {
    letter-spacing: .35rem;
    text-transform: uppercase;
}
.signup-wrapper h2 {
    margin-block: 1.25rem 2rem;
    font-weight: 500;
    font-size: 2rem;
}
.signup-wrapper .signup {
    display: flex;
    flex-direction: column;
    padding-inline: 2rem;
}
.signup-wrapper .signup .input-wrapper {
    margin-bottom: 1rem;
}
.signup-wrapper .signup .input-wrapper div {
    width: 100%;
}
.signup-wrapper .signup .input-wrapper div img {
    display: none;
    transition: all 5s ease;
}
.signup-wrapper .signup .input-wrapper.error div {
    position: relative;
}
.signup-wrapper .signup .input-wrapper div input {
    padding-block: 1.375rem;
    border: none;
    border-radius: 0.25rem;
    padding-left: 1.25rem;
    font-size: 1rem;
    font-weight: 500;
    font-family: 'Rubik', sans-serif;
    width: 100%;
}
.signup-wrapper .signup .input-wrapper div input:focus {
    outline: none;
}
.signup-wrapper .signup .input-wrapper.error div img {
    display: block;
    position: absolute;
    right: 15px;
    top: 21.5px;
    bottom: 21.5px;
}
.signup-wrapper .signup .input-wrapper.error {
    background-color: var(--Soft-Red);
    padding: 3px 3px 4px;
    text-align: left;
    border-radius: 0.25rem;
}
.signup-wrapper .signup .input-wrapper.error span {
    font-size: 0.75rem;
    margin-left: 0.75rem;
}
.signup-wrapper .signup button {
    padding-block: 1.375rem;
    border: 2px solid var(--Soft-Red);
    border-radius: 0.25rem;
    background-color: var(--Soft-Red);
    color: white;
    font-family: 'Rubik', sans-serif;
    font-weight: 500;
    transition: all 0.5s ease;
    cursor: pointer;
}
.signup-wrapper .signup button:hover {
    color: var(--Soft-Red);
    background-color: white;
}
@media screen and (min-width: 1280px) {
    .signup-wrapper h2 {
        margin-inline: 30rem;
    }
    .signup-wrapper .signup {
        flex-direction: row;
        align-items: center;
        justify-content: center;
        gap: 1rem;
        padding-inline: 30rem;
    }
    .signup-wrapper .signup .input-wrapper {
        flex-grow: 2;
    }
    .signup-wrapper .signup .input-wrapper {
        margin-bottom: 0;
    }
    .signup-wrapper .signup button {
        padding-inline: 1.5rem;
        flex-grow: 1;
    }
}
</style>