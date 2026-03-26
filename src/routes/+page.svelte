<script>
import * as d3 from 'd3';
import { onMount } from 'svelte';

let svgElement;

onMount(() => {
  const svg= d3.select(svgElement);
  const box = svgElement.getBoundingClientRect()
  const width= box.width;
  const height= box.height;
  const circle = svg.append("circle");
  circle.attr('r', 200)
  .attr('cx', width/2)
  .attr('cy', height/2)
  
  
  
})
</script>
<div class="container">
 <svg bind:this={svgElement} width="90vw" height="90vh"></svg>
</div>

<style>
   .container{
    width: 90vw;
    height: 90vh;
    border: solid 2px grey;
    border-radius: 30px;
   }
</style>