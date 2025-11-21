<script setup>
import { ref } from 'vue';

const sayings = [
    { quote: "If at first you don't succeed, hide all the evidence that you ever tried.", author: "Wally" },
    { quote: "I could agree with you, but then we’d both be wrong.", author: "Dilbert" },
    { quote: "Hard work never killed anybody, but why take a chance?", author: "Alice" },
    { quote: "The problem with the gene pool is that there is no lifeguard.", author: "Dogbert" },
    { quote: "I’m not lazy, I’m on energy-saving mode.", author: "Wally" },
    { quote: "I’m not arguing, I’m just explaining why I’m right.", author: "Dilbert" },
    { quote: "It’s not a bug – it’s an undocumented feature.", author: "Dilbert" },
    { quote: "I intend to live forever. So far, so good.", author: "Alice" },
    { quote: "If you think nobody cares if you’re alive, try missing a couple of payments.", author: "Dogbert" },
    { quote: "I’m on a seafood diet. I see food and I eat it.", author: "Wally" },
    { quote: "Why do they call it rush hour when nothing moves?", author: "Dilbert" },
    { quote: "I used to think I was indecisive, but now I’m not so sure.", author: "Alice" },
    { quote: "I’m not great at the advice. Can I interest you in a sarcastic comment?", author: "Dogbert" },
    { quote: "I’m multitasking: I can listen, ignore and forget at the same time.", author: "Wally" },
    { quote: "Some people graduate with honors, I am just honored to graduate.", author: "Dilbert" },
    { quote: "I’m not procrastinating. I’m doing side quests.", author: "Alice" },
    { quote: "If at first you don’t succeed, skydiving is not for you.", author: "Dogbert" },
    { quote: "I put the 'pro' in procrastinate.", author: "Wally" },
    { quote: "Experience is something you don’t get until just after you need it.", author: "Dilbert" },
    { quote: "I’m on a 30-day diet. So far, I’ve lost 15 days.", author: "Alice" },
    { quote: "I’m not lazy, I’m just very relaxed.", author: "Dogbert" }
];


const index = ref(0);
const nextSaying = () => {
    index.value = (index.value + 1) % sayings.length;
};
</script>


<template>
    <main>

        <section>
        
        <p> {{ sayings[index].quote }}
        </p>
        <span>{{sayings[index].author}}</span>
        </section>

        <button @click="nextSaying">Another Quote</button>

    </main>

</template>

<style scoped>


    main {
    background: #ccd5d9;
    max-width: 90%;
    border-radius: 0 15px 0 15px;
    padding: 35px;
    display:flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
    }

    section {
        display: flex;
        width: 100%;
        flex-direction: column;
        gap: 10px;
        margin-bottom: 25px;
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    p {
        font-weight: bold;
        font-style: italic;
        font-size: 2rem;
        text-align: left;

     }

    p::before {
    content: '"';
    font-size: 30px;
    
    }

    p::after {
    content: '"';
    font-size: 30px;
   
    }

    span {
        font-weight: bold;
        align-self: end;
        font-style: italic;
        color : #406473;
    }

    span::before {
        content: "— ";
    }

    button {
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        background-color: navy;
        color: white;
        font-size: 16px;
        cursor: pointer;
        font-weight : bold;
        margin-top: 20px;
        cursor: pointer;
        transition: 0.3s;
    }

    button:hover {
        background-color: darkblue;
        transform : scale(1.05);
    }   
 
</style>