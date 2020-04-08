<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();
  let component = "Nested";
  export let count = 0;
  let [x, y] = [0, 0];
  const handleClick = () => {
      count += 1
  }

  const wellPrivetik = () => {
    dispatch('hello', {
      text: "HELLOUUU!"
    });
  }

  const handleMouseMove = (event) => {
    x = event.clientX;
    y = event.clientY;
  }

  $: doubled = count * 2;
  $: if (count > 30) {
    count = 5;
  }
  const dogs = ['Dzhulka', 'Karamelka', 'Jenny'];

</script>

<p>This is the {component} component</p>
<button on:click={wellPrivetik}>
Hello click me
</button>
<div on:mousemove|once={handleMouseMove}>
The mouse position is {x} and {y}
</div>