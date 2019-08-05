<script>
  import { onMount } from "svelte";
  import Balloon from "./Balloon.svelte";

  let popButton;
  let revealText;

  function pop() {
    popButton.classList.add("hidden");
    setTimeout(() => {
        revealText.classList.toggle("hidden");
        for (let i = 1; i < 100; i += 1) {
        new Balloon({
            target: document.body,
            props: {
            size: "lg",
            colour: "pink",
            }
        });
        }
    }, 2000)
  }

  onMount(() => {
    popButton.classList.add("pink")
    setInterval(()=> {
        popButton.classList.toggle("pink");
        popButton.classList.toggle("blue");
    }, 500)
  });

</script>

<div on:click={pop} bind:this={popButton} class="inline-block px-32">
What is it?
</div>

<div class="hidden text-6xl font-black text-pink-500" bind:this={revealText} style="z-index: 1;">
IT'S A GIRL
</div>