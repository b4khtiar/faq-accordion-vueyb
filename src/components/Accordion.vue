<script setup>
import { ref } from 'vue'
const props = defineProps({
    data: Object
})

const isOpen = ref(false)
</script>

<template>
    <div class="accordion">
        <div @click="isOpen = !isOpen" @keyup.enter="isOpen = !isOpen" role="button" tabindex="0" class="accordion__header">
            <h2>{{ data.question }}</h2>
            <div>
                <span v-if="isOpen">
                    <img src="/images/icon-minus.svg" alt="minimize">
                </span>
                <span v-else>
                    <img src="/images/icon-plus.svg" alt="expand">
                </span>
            </div>
        </div>
        <Transition name="slide-fade">
        <div class="accordion__content" v-show="isOpen">
            <p>{{ data.answer }}</p>
        </div>
        </Transition>
    </div>
</template>

<style scoped>
.accordion {
    width: 100%;
}
accordion:focus h2 {
    color: var(--Purple);
}
.accordion:not(:last-of-type) {
    border-bottom: 1px solid var(--Light-pink);
    padding-bottom: 1rem;
}
.accordion:not(:first-of-type) {
    margin-top: 1rem;
}
.accordion__header {
    display: flex;
    justify-content: space-between;
    gap: 1.5rem;
    align-items: center;
    cursor: pointer;
}
h2 {
    margin: 0;
    font-size: 1rem;
    font-weight: 700;
    color: var(--Dark-purple);
}

h2:hover {
    color: var(--Purple);
}

.accordion__content {
    margin-top: 1rem;
    font-size: 0.9rem;
    color: var(--Grayish-purple);

}

.slide-fade-enter-active {
  transition: all 0.25s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.1s ease-out;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}

@keyframes drop {
  0% {
    opacity: 0;
    transform: scaleY(0);
  }
  100% {
    opacity: 1;
    transform: scaleY(1);
  }
}
</style>