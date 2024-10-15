<template>
  <div class="item">
    <div class="project-img">
      <a :href="link" target="_blank">
        <slot name="image"></slot>
      </a>
    </div>
    <div class="project-details">
      <div class="title">
        <slot name="title"></slot>
      </div>
      <div class="subtitle">
        <slot name="subtitle"></slot>
      </div>
    </div>
  </div>
</template>

<script setup>

const props = defineProps({
  link: String,
})
</script>

<style scoped>

.item {
  margin-top: 2rem;
  display: flex;
  flex-direction: column;
  position: relative;
}

.project-img {
  width: 100%;
  margin-bottom: 0.5rem;
}

.project-img a{
  opacity: .85;
}

.project-img a:hover{
  opacity: 1;
}

.project-details {
  flex: 1;
}

.project-details .title {
  font-size: 1em;
  font-weight: 600;
}

.project-details .subtitle {
  font-size: 1em;
  font-weight: 300;
}



h3 {
  font-size: 1.2rem;
  font-weight: 500;
  margin-bottom: 0.4rem;
  color: var(--color-heading);
}

@media (min-width: 1024px) {

}
</style>
