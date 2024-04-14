<template>
  <div :class="open ? 'faq open' : 'faq'" @click="$emit('toggleOpen', index)">
    <div class="question">{{ faq.question }}</div>
    <div class="answer">
      <p>{{ faq.answer }}</p>
      <!-- Anchor tag with the link -->
      <a v-if="faq.link" :href="faq.link" target="_blank" class="accordionLink"
        >Click here to open!</a
      >
      <a v-if="faq.link2" :href="faq.link2" target="_blank" class="accordionLink"
        >Click here to open low fidelity prototype!</a
      >
      <a v-if="faq.link3" :href="faq.link3" target="_blank" class="accordionLink"
        ><br /><br />Click here to open high fidelity prototype!</a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: 'FAQ',
  props: ['faq', 'index', 'open']
}
</script>

<style>
.answer {
  /* Match styling with question */
  font-family: 'Inter', sans-serif;
  color: #374e37;
}

.accordionLink {
  /* Match styling with other links */
  color: #374e37;
  text-decoration: underline;
  font-weight: bold;
  font-style: italic;
}

.accordionLink:hover {
  color: #89c997; /* Change color on hover */
}
</style>
