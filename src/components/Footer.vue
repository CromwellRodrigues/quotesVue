<script setup>
import { ref } from 'vue';

const jokes = [

  "Made with ☕ and mild panic.",
  "If this app breaks, it wasn't me. Probably.",
  "Feature-complete: adds charm, removes bugs (in your dreams).",
  "Legal: no robots were harmed in the making of this footer 🤖",
  "Debugging: where you spend hours to save minutes.",
  "I’m not a bug, I’m an undocumented feature.",
    "To err is human; to really foul things up requires a computer.",
    "Software and cathedrals are much the same — first we build them, then we pray.",
    "There are two ways to write error-free programs; only the third one works.",   
    "A user interface is like a joke. If you have to explain it, it’s not that good.",
    "Walking on water and developing software from a specification are easy if both are frozen.",

]

const i =  ref(Math.floor(Math.random() * jokes.length));
const joke = ref(jokes[i.value]);

function nextJoke() {
    i.value = (i.value + 1) % jokes.length;
    joke.value = jokes[i.value];
}


</script>


<template>
    <footer class="fun-footer"
    @click="nextJoke"
    role="button"
    title="Click me for more wisdom"
    >
    <span class="sparkle">✨</span>
    <span class = "text">{{ joke }}</span>
    <span class="sparkle">✨</span>
        

    </footer>

</template>


<style scoped>

    footer {
     position: fixed;
     margin: 0 auto;
     bottom: 0;
     text-align: center;
     color: white;
     padding-bottom: 20px;

    }

    span {
        color: white;
        font-weight: bold;
        font-family: cursive;
    }   
.fun-footer{
  position: fixed;
  left: 50%;
  transform: translateX(-50%);
  bottom: 20px;
  background: linear-gradient(90deg, navy, dodgerblue);
  color: white;
  padding: 10px 18px;
  border-radius: 999px;
  font-family: "Comic Sans MS", "Comic Neue", cursive, system-ui;
  box-shadow: 0 6px 18px rgba(0,0,0,0.25);
  display: inline-flex;
  gap: 10px;
  align-items: center;
  cursor: pointer;
  user-select: none;
  transition: transform .15s ease, box-shadow .15s ease;
}
.fun-footer:hover{
  transform: translateX(-50%) translateY(-4px) scale(1.102);
  box-shadow: 0 10px 26px rgba(0,0,0,0.32);
}
.fun-footer .sparkle{
  animation: twinkle 2s infinite;
  font-size: 1.1rem;
}
@keyframes twinkle {
  0%,
  100%{ opacity: .8; transform: translateY(0) rotate(0) }
  50%{ opacity: 1; transform: translateY(-4px) rotate(10deg) }
}
.fun-footer .text{
  font-weight: 600;
  font-size: 0.95rem;
  white-space: nowrap;
}
</style>