<script setup>
import { ref } from 'vue'
import Card from './components/Card.vue'
import Accordion from './components/Accordion.vue'

const faqs = [
  {
    id: 1,
    question: 'What is Frontend Mentor, and how will it help me?',
    answer: 'Frontend Mentor offers realistic coding challenges to help developers improve their frontend coding skills with projects in HTML, CSS, and JavaScript. It\'s suitable for all levels and ideal for portfolio building.'
  },
    {
      id: 2,
      question: 'Is Frontend Mentor free?',
      answer: 'Yes, Frontend Mentor offers both free and premium coding challenges, with the free option providing access to a range of projects suitable for all skill levels.'
    },
    {
      id: 3,
      question: 'Can I use Frontend Mentor projects in my portfolio?',
      answer: 'Yes, you can use projects completed on Frontend Mentor in your portfolio. It\'s an excellent way to showcase your skills to potential employers!'
    },
    {
      id: 4,
      question: 'How can I get help if I\'m stuck on a challenge?',
      answer: 'The best place to get help is inside Frontend Mentor\'s Discord community. There\'s a help channel where you can ask questions and seek support from other community members.'
    }
]
</script>

<template>
  <div class="backdrop">
    <Card>
      <h1>
        <img src="/images/icon-star.svg" alt="icon star">
        <span>FAQs</span>
      </h1>

      <Accordion v-for="faq in faqs" :key="faq.id" :data="faq" />
    </Card>
  </div>
</template>

<style scoped>
.backdrop {
  width: 100%;
  min-height: 100vh;
  background-color: var(--Light-pink);
  background-image: url('/images/background-pattern-mobile.svg');
  background-repeat: no-repeat;
  background-position: top;
  background-size: contain;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 4rem 1.5rem;
}

h1 {
  font-size: 2rem;
  font-weight: 700;
  margin-bottom: 2rem;
  display: flex;
  align-items: center;
  gap: 1rem;
}

@media screen and (min-width: 768px) {
  .backdrop {
    background-image: url('/images/background-pattern-desktop.svg');
  }
}
</style>
