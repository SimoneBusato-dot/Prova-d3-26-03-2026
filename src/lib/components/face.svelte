<script>
import * as d3 from 'd3';
import { onMount } from 'svelte';
    import { transform } from 'typescript';

let svgElement;

onMount(() => {
  const svg= d3.select(svgElement);
  const box = svgElement.getBoundingClientRect()
  const width= box.width;
  const height= box.height;
  const eyeSpaing = 50;
  const eyeOffste = 70;
  const arcGenerator = d3.arc()
  .innerRadius(80)
  .outerRadius(100)
  .startAngle(Math.PI/2)
  .endAngle(Math.PI*3/2);
  
  const circle = svg.append("circle")
  .attr('r', 200)
  .attr('cx', width/2)
  .attr('cy', height/2)
  .attr('fill', 'yellow')
  .attr('stroke', 'black')

  const lftEye = svg.append("circle")
  .attr('r', 20)
  .attr('cx', width/2 - eyeSpaing)
  .attr('cy', height/2 - eyeOffste)
  .attr('fill', 'black')
  .attr('stroke', 'black')
  .transition().duration(2000)
  .attr('cy', height/2 - eyeOffste -40)
  .transition().duration(2000)
  .attr('cy', height/2 - eyeOffste)
  
  const rgtEye = svg.append("circle")
  .attr('r', 20)
  .attr('cx', width/2 + eyeSpaing)
  .attr('cy', height/2 - eyeOffste)
  .attr('fill', 'black')
  .attr('stroke', 'black')

  const smile = svg.append('path')
  .attr('d', arcGenerator)
  .attr('transform', `translate(${width/2}, ${height/2})`)
  
  
  
})
</script>

<svg bind:this={svgElement} width="90vw" height="90vh"></svg>