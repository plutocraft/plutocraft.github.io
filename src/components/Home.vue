<template>
  <div class="flex center hero">
    <img class="wordmark" src="@/assets/logo.svg"/>
    <div class="flex product">
      <div class="view"><img class="productimage" src="@/assets/pk87-small.png"/></div>
      <div class="title">pk87.0 interest check</div>
      <div class="viewbutton" @click="store('pk87.0')">see more</div>
    </div>
  </div>
</template>

<script>
import anime from "animejs";

export default {
  name: "Home",
  mounted: function() {
    anime({
      targets: ".wordmark path",
      loop: true,
      strokeDashoffset: [anime.setDashoffset, 0],
      easing: "easeInOutSine",
      duration: 1500,
      delay: function(el, i) {
        return i * 250;
      },
      direction: "alternate"
    });
  },
  methods: {
    store: function(val) {
      window.location.href = "https://plutocraft.store/#/" + val;
    }
  }
};
</script>

<style scoped>
@keyframes shift {
  0% {
    filter: hue-rotate(0deg);
  }
  100% {
    filter: hue-rotate(360deg);
  }
}
.hero {
  padding: 100px;
  background: white;
  flex-flow: column nowrap;
}
.hero .wordmark {
  width: 300px;
}
.product {
  width: 400px;
  margin-top: 100px;
  height: 300px;
  background: black;
  color: white;
  border-radius: 10px;
  justify-content: flex-start;
  align-items: center;
  flex-flow: column nowrap;
  box-shadow: 0 10px 20px rgba(0,0,0,0.19), 0 6px 6px rgba(0,0,0,0.23);
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
}
.productimage {
  height: 100px;
  animation: 25s shift infinite;
}
.product:hover {
  transform: scale(1.05);
}
.view {
  background: white;
  height: 50%;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 22px;
}
.title {
  font-family: Circular;
  font-size: 2.25em;
  animation: 25s shift infinite;
  color: #e429fe;
}
.viewbutton {
  margin-top: 22.5px;
  font-family: Circular;
  font-size: 1.5em;
  padding: 10px;
  color: #e429fe;
  border: 2px solid #e429fe;
  border-radius: 5px;
  animation: 25s shift infinite;
  cursor: pointer;
  transition: all 0.2s ease;
}
.viewbutton:hover {
  background: #e429fe;
  color: black;
}
</style>
