<script setup lang="ts">
import { computed, onMounted, ref, watch, } from "vue";
import { useCounter } from "../composables/useCounter";
  
  const props = defineProps({
    message: {
      type: String,
      required: true
    }
  })
    const { counter, increment } = useCounter();
    const { counter: counter2, increment: increment2 } = useCounter();
      
    const nom = ref('');
    const prenom = ref('');

    const nomComplet = computed(() => `${nom.value} ${prenom.value}` )

    onMounted(() => {
      console.log(props.message)
    })
    watch(nomComplet, (newValue) => {
      console.log("Nouvelle valeur : ", newValue)
    })
</script>
<template>
  <p> {{ message }} </p>
  <div>
    <label for="">
      Nom : <input type="text" v-model="nom">
    </label>
  <label for="">
      Prenom : <input type="text" v-model="prenom">
    </label> 
  </div>
  <div>
    <p> Nom Complet : {{ nomComplet }}</p>
  </div>
  <button @click="increment">
    Counter : {{ counter }}
  </button>    
  <button @click="increment2">
    Counter Deux : {{ counter2 }}
  </button>  
</template>