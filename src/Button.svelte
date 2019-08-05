<script>
  import { onMount } from "svelte";
  import Balloon from "./Balloon.svelte";

  let popButton;
  let revealText;
  let text = "Princess";

  const trumpet = new Audio('http://www.trumpetsandbrassincostume.com/fanfares/04%20-%20Rondeau.mp3');

  function pop() {
  trumpet.play();
    popButton.classList.add("hidden");
    setTimeout(() => {
        revealText.classList.toggle("hidden");
        for (let i = 1; i < 50; i += 1) {
        new Balloon({
            target: document.body,
            props: {
            size: "lg",
            colour: "blue",
            }
        });
        }
    }, 2000)
  }

  onMount(() => {
    popButton.classList.add("pink")
    setInterval(() => {
        if (text === "Princess") {
            text = "Prince";
        } else {
            text = "Princess"
        }

        popButton.classList.toggle("pink");
        popButton.classList.toggle("blue");
    }, 500)
  });

</script>



<div on:click={pop} bind:this={popButton} class="inline-block px-16 text-2xl mx-16">
{text}
</div>

<div class="hidden text-6xl font-black text-pink-500 text-center" bind:this={revealText} style="z-index: 1;">
IT'S A<br>PRINCESS<br>👸
</div>