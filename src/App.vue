<template>
  <div class="bg-gradient-to-b from-indigo-200 to-pink-300 aspect-auto absolute inset-0 flex flex-col items-center justify-center">
    <div class="bg-orange-300 rounded-md shadow-md w-96 p-20">
      <div>
        <h1>
          <div>
            <h2 v-if="images.length">{{images[index]}}</h2>
          </div>
          <div class="mt-2 mb-4">
            <button @click="decr" class="text-3xl font-bol class=my-7d"> &larr;</button>
            <button @click="incr" class="text-3xl font-bold">&rarr;</button>
          </div>

          <hr class="my-5 border-gray-700">

          <div class="flex space-x-4">
            <span v-for="(image, index1) in images" :key="index1"
                  :class="{
                        'fade rounded-full duration-200 bg-gray-700 text-white flex flex-col justify-center items-center w-7 h-7 p-3' : index === index1 ,
                   }"
            >
              {{ index1 }}</span>
          </div>
        </h1>
      </div>
    </div>
  </div>
</template>



<script setup>
import {ref, reactive, computed} from "vue"
  const images = reactive([
    "city",
    "arsenal",
    "tottenham",
    "chelsea",
    "everton",
    "liverpool"
  ]);

  const index = ref(0)
  const incr = ()=>{
    if(index.value < images.length-1){
      index.value++
    }
    else{
      index.value = 0;
    }
  };

  const decr = ()=>{
    if(index.value >0){
      index.value--
    }
    else{
      index.value = images.length-1;
    }
  };
</script>
