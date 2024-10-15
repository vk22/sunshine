<script setup>
import { useReservationStore } from "@/store/reservation";
const reservationStore = useReservationStore();
const getFormModalStateToggle = () => {
  reservationStore.setFormModalState();
};
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <img class="logo" src="@/assets/logo.svg"/>
    <button class="btn" @click="getFormModalStateToggle">Get a quote</button>
  </header>
  <RouterView />
</template>

<style scoped>
header {
  font-family: 'Montserrat', sans-serif;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  z-index: 999;
  width: 100vw;
  padding: 2rem;
  top: 0;
  left: 0;
}

.logo {
  display: block;
  width: 145px;
}

.btn {
  font-family: 'Montserrat', sans-serif;
  font-size: 1em;
  font-weight: 400;
  border-radius: 100px;
  background: #fff;
  padding: .5rem .75rem;
  border: 1px solid #ddd;
  cursor: pointer;
  transition: all .3s ease-in-out;
}
.btn:hover {
  background: #e9e9e9;
}

@media (min-width: 1024px) {
  header {

  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {

  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>
