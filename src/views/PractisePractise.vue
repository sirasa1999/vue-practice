<template>
    <NewView name="Sita" age=19 address="Jnk"/>
  <div>
    {{ title.name }}
    {{ props.name }}
    </div>
    <br><hr><br>
    <div class="text-white text-center">
    <button
      @click="flash()"
      class="bg-gradient-to-r from-indigo-800 to-red-600 w-24 h-16 text-white border border-black-600 items-center rounded-2xl"
    >
      Click Me
    </button>
    </div>
    <br><hr><br>
    <div>
    <p>What is your address?<input type="text" v-model='address' @input="write('address',address)" class="border border-gray-800"></p>
    <p>What is your favourite food?<input type="text" v-model='food' @input="write('food',food)" class="border border-gray-800 mt-3"></p>
    
  </div>
  <!-- <img src="@/assets/img/8.gif" style="width:48px;height:48px;"> -->
</template>

<script setup>
import Swal from "sweetalert2";
import { ref, watch, defineProps } from "vue"


    let address=localStorage.getItem('address')
    let food=localStorage.getItem('food')

    watch(food, (val) => {
        write('food',val)
    });

    function write(key, val){
            localStorage.setItem(key,val)
        }

    setTimeout(() => {
        food.value = 'wow';
    },2000);

    const title = ref({name: 'happy'});
    
    const props = defineProps({
        name: {type: String, default:"happy"},
    })
   
    function flash() {
        const imagePath = require("@/assets/img/rainbow.gif");
        Swal.fire({
            title: "WOW!!",
            text: "Such an amazing rainbow.",
            // icon: "success",
            // confirmButtonText: "Cool",
            imageUrl: imagePath,
            imageWidth: 400,
            imageHeight: 300,
        });
    }
</script>
