<template>
    <div>
        <p>jcrois c'est full guez</p>
        <canvas id="ecranJeu" width="200" height="400"></canvas>
    </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
const canvas = ref(null)
const context = ref(null)
const scale = 10
onMounted(() => {
    canvas.value = document.getElementById("ecranJeu")
    // console.log(canvas)
    const context = ref(canvas.value.getContext('2d'))
    console.log(context)
    function drawSquare(context, x, y, color)
 {
	  context.value.fillStyle = color;
	  context.value.fillRect(x * scale, y * scale, scale, scale);
	  context.value.strokeStyle = 'black';
	  context.value.strokeRect(x * scale, y * scale, scale, scale);
	}

    drawSquare(context,1,1,"red")
    drawSquare(context,1,2,"red")
    drawSquare(context,1,3,"red")
})


console.log(context)



</script>


<style scoped>
canvas{
    border: solid;
    border-color: white;
    border-width: 5px;
}

</style>