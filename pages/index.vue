<template>
  <div class="container">
    <h1 class="js-splitme">homepage!!!!</h1>
  </div>
</template>

<script>
import {TimelineMax} from 'gsap';
import Splitter from 'split-html-to-chars';

export default {
  mounted() {
    let els = document.querySelectorAll(".js-splitme");
    [].forEach.call(els, function(el) {
        el.outerHTML = Splitter(el.outerHTML, '<span class="letter">$</span>');
    });
  },
  transition: {
    name: 'test',
    mode: 'out-in',
    css: false,
    enter: function(el, done) {
      let tl = new TimelineMax({onComplete: done})
      let els = document.querySelectorAll(".letter");
      tl.fromTo(els, 0, {y:-100, opacity: 0}, {y: -30, opacity: 0})
      tl.staggerTo(els, 0.5, {y:0, opacity: 1}, 0.1)
      
      // tl.fromTo(el, 0.3, {y: -100, opacity: 0, rotation: 30}, {y: 0, opacity: 1, rotation: 0})
    },
    leave: function(el, done) {
      let tl = new TimelineMax({onComplete: done})
      tl.fromTo(el, 0.3, {y: 0, opacity: 1}, {y: 100, opacity: 0})
    }
  }
}
</script>

<style>
  /* .slide-enter-active{
    transition: all .3s ease-in-out;
  }
  .slide-leave-active{
    transition: all .3s ease-in-out;
  }

  .slide-enter{
    transform: translateY(-100%);
    opacity: 0;
  }
  .slide-enter-to{
    transform: translateY(0%);
    opacity: 1;
  }

  .slide-leave{
    transform: translateY(0%);
    opacity: 1;
  }
  .slide-leave-to{
    transform: translateY(100%);
    opacity: 0;
  } */
</style>