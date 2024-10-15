<template>
  <div class="index" ref="main" :class="{'blur': formModalOpened}">
    <!-- <Sunrise></Sunrise> -->
    <div class="hero-main">
      <AnimatedComponent delay="0" animation-type="slideup">
        <div class="hero-text-wrap">
          <h1>Development of digital products</h1>
          <p>We create websites, apps and branding. Our primary focus are start-ups, real estate and eCommerce projects.
          </p>
        </div>
      </AnimatedComponent>
    </div>
    <div class="projects-index">
      <AnimatedComponent delay="250" animation-type="slideup" v-for="(project, index) in projects" :key="index"
        :index="index">
        <ProjectItem :link="project.link">
            <template #image>
              <img :src="'/' + project.img" alt="">
            </template>
            <template #title>{{ project.title }}</template>
            <template #subtitle>{{ project.subtitle }}</template>
        </ProjectItem>
      </AnimatedComponent>
    </div>

  </div>
</template>


<script setup>
import { onMounted, computed, ref } from 'vue';
import AnimatedComponent from './AnimatedComponent.vue';
import ProjectItem from './ProjectItem.vue'
import Sunrise from './Sunrise.vue'
import { useReservationStore } from "../store/reservation";
const store = useReservationStore();
const formModalOpened = computed(() => store.getFormModalState)
// import gsap from 'gsap-trial';
// import { ScrollTrigger } from 'gsap-trial/ScrollTrigger';
// import { ScrollSmoother } from 'gsap-trial/ScrollSmoother';

// gsap.registerPlugin(ScrollTrigger, ScrollSmoother);


const projects = [
  {
    img: 'project-img.jpg',
    title: 'OyOy Restaurant',
    subtitle: 'UX/UI. Develoment.',
    link: 'https://oyoyrestaurant.com/'
  },
  {
    img: 'project-img2.jpg',
    title: 'Revibed',
    subtitle: 'UX/UI. Develoment.',
    link: 'https://revibed.com/'
  },
  {
    img: 'project-img8.jpg',
    title: 'UploaderX',
    subtitle: 'UX/UI. Develoment.',
    link: 'https://uploader-x.com/'
  },
  {
    img: 'project-img6.jpg',
    title: 'Neva Yali',
    subtitle: 'UX/UI. Develoment.',
    link: 'https://nevaizmir.ru/'
  },
  {
    img: 'project-img5.jpg',
    title: 'Neva Management',
    subtitle: 'UX/UI. Develoment.',
    link: 'https://nevamanagement.ru/'
  },
  {
    img: 'project-img10.jpg',
    title: 'VRV Global Logistics',
    subtitle: 'UX/UI. Develoment.',
    link: 'http://topcarhauler.com/'
  },
  {
    img: 'project-img3.jpg',
    title: 'Asyst Visualizator',
    subtitle: 'UX/UI. Develoment.',
    link: 'http://visual.asyst.ru/'
  },
  {
    img: 'project-img4.jpg',
    title: 'Villa Tahalassa',
    subtitle: 'UX/UI. Develoment.',
    link: 'https://villathalassa.co.uk/'
  },
  {
    img: 'project-img7.jpg',
    title: 'Desna Development',
    subtitle: 'UX/UI. Develoment.',
    link: 'https://desnadev.ru/'
  },
  {
    img: 'project-img9.jpg',
    title: 'Birds Development',
    subtitle: 'UX/UI. Develoment.',
    link: 'https://birds.ru/'
  }
]
// const main = ref();
// let smoother;
// let ctx;

// onMounted(() => {
//   ctx = gsap.context(() => {
//     // create the smooth scroller FIRST!
//     // smoother = ScrollSmoother.create({
//     //   smooth: 2, // seconds it takes to "catch up" to native scroll position
//     //   effects: true, // look for data-speed and data-lag attributes on elements and animate accordingly
//     // });
//     // ScrollTrigger.create({
//     //   trigger: '.circle',
//     //   pin: false,
//     //   // start: 'center center',
//     //   // end: '+=300',
//     //   markers: false,
//     // });

//     // let tl = gsap.timeline({
//     //   // yes, we can add it to an entire timeline!
//     //   scrollTrigger: {
//     //     trigger: '.index',
//     //     pin: true, // pin the trigger element while active
//     //     start: 'top top', // when the top of the trigger hits the top of the viewport
//     //     end: '+=500', // end after scrolling 500px beyond the start
//     //     scrub: 1, // smooth scrubbing, takes 1 second to "catch up" to the scrollbar
//     //     snap: {
//     //       snapTo: 'labels', // snap to the closest label in the timeline
//     //       duration: { min: 0.2, max: 3 }, // the snap animation should be at least 0.2 seconds, but no more than 3 seconds (determined by velocity)
//     //       delay: 0.2, // wait 0.2 seconds from the last scroll event before doing the snapping
//     //       ease: 'power1.inOut' // the ease of the snap animation ("power3" by default)
//     //     }
//     //   }
//     // });

//     // add animations and labels to the timeline
//     tl
//     .addLabel('start')
//     .from('.circle', { scale: 0.3, rotation: 45, autoAlpha: 0 })



//   }, main.value);
//   // 
// });

</script>

<style>
.blur {
  opacity: .5;
}

.hero-main {
  position: relative;
  height: 60vh;
  width: 100%;
  padding: 2rem 0;
  display: flex;
  align-items: flex-end;
}

h1 {
  font-size: 2.5em;
  line-height: 1.25em;
  margin-bottom: 1rem;
  font-weight: 600;
}

.projects-index {
  margin-top: 2rem;
  position: relative;
  background: #fff;
  z-index: 99;
}

@media (min-width: 1024px) {
  h1 {
    font-size: 3em;
  }
  .projects-index {
    margin-top: 8rem;
  }
}
</style>
