<script>
  import { navigate } from "svelte-routing";

    const goBack = () => {
      navigate("/", { replace: true });
    }

  let component = "Nested";

</script>

<p>This is the {component} component</p>
<button on:click={goBack}>
Hello click me
</button>