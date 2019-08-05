<script>
  import { onMount } from "svelte";
  let self;

  let sizes = {
    sm: {
      width: 52,
      height: 70
    },
    md: {
      width: 78,
      height: 105
    },
    lg: {
      width: 104,
      height: 140
    },
    xl: {
      width: 156,
      height: 210
    }
  };

  let colours = {
    pink: ["#ff78bb", "#ff87c3", "#ff96ca", "#ffa5d2", "#ffb4d9", "#ffc3e1"],
    blue: ["#5ea2e5", "#6eabe7", "#7eb4ea", "#8ebdec", "#9ec7ef", "#aed0f2"]
  };
  export let colour = "pink";
  export let size = "md";
  export let y = window.innerHeight / 2.5;
  console.log(y)
  export let x = Math.floor(Math.random() * window.innerWidth / 2) + window.innerWidth / 4;
  export let speed = Math.floor(Math.random() * 20) + 5;

  let shadeColour =
    colours[colour][Math.floor(Math.random() * colours[colour].length)];

  onMount(() => {
    setTimeout(()=> {
      self.parentNode.removeChild(self);
    }, 30000)
  });
</script>

<div class="float" style="--speed: {speed}s" bind:this={self}>
  <div
    class="balloon "
    style="--colour: {shadeColour}; width: {sizes[size].width}px; height: {sizes[size].height}px;
    --size: {sizes[size].width / 2}px; --top: {y}px; --left: {x}px;" />
</div>

<style>
  .float {
    animation: float var(--speed) ease-in-out forwards;
  }

  .style1 {
    -webkit-animation: balloon1 2s ease-in-out infinite;
    -moz-animation: balloon1 2s ease-in-out infinite;
    -o-animation: balloon1 2s ease-in-out infinite;
    animation: balloon1 2s ease-in-out infinite;
  }
  .style2 {
    -webkit-animation: balloon2 2s ease-in-out infinite;
    -moz-animation: balloon2 2s ease-in-out infinite;
    -o-animation: balloon2 2s ease-in-out infinite;
    animation: balloon2 2s ease-in-out infinite;
  }
  .style3 {
    -webkit-animation: balloon3 2s ease-in-out infinite;
    -moz-animation: balloon3 2s ease-in-out infinite;
    -o-animation: balloon3 2s ease-in-out infinite;
    animation: balloon3 2s ease-in-out infinite;
  }
  .style4 {
    -webkit-animation: balloon4 2s ease-in-out infinite;
    -moz-animation: balloon4 2s ease-in-out infinite;
    -o-animation: balloon4 2s ease-in-out infinite;
    animation: balloon4 2s ease-in-out infinite;
  }

  .balloon {
    top: var(--top);
    left: var(--left);
    background: var(--colour);
    border-radius: 0;
    border-radius: 80% 80% 80% 80%;
    margin: 0 auto;
    position: absolute;
    padding: 10px;
    -webkit-transform-origin: bottom center;
  }

  .balloon:before {
    color: var(--colour);
    position: absolute;
    bottom: -11px;
    left: var(--size);
    content: "▲";
    font-size: 1em;
  }

  /*FLOAT AWAY*/
  @-webkit-keyframes float {
    100% {
      -webkit-transform: translateY(-190vh);
    }
  }
  @-moz-keyframes float {
    100% {
      -moz-transform: translateX(-190vh);
    }
  }
  @-o-keyframes float {
    100% {
      -o-transform: translateX(-190vh);
    }
  }
  @keyframes float {
    100% {
      transform: translateY(-190vh);
    }
  }

  /*BALLOON 1 4*/
  @-webkit-keyframes balloon1 {
    0%,
    100% {
      -webkit-transform: translateY(0) rotate(-6deg);
    }
    50% {
      -webkit-transform: translateY(-20px) rotate(8deg);
    }
  }
  @-moz-keyframes balloon1 {
    0%,
    100% {
      -moz-transform: translateY(0) rotate(-6deg);
    }
    50% {
      -moz-transform: translateY(-20px) rotate(8deg);
    }
  }
  @-o-keyframes balloon1 {
    0%,
    100% {
      -o-transform: translateY(0) rotate(-6deg);
    }
    50% {
      -o-transform: translateY(-20px) rotate(8deg);
    }
  }
  @keyframes balloon1 {
    0%,
    100% {
      transform: translateY(0) rotate(-6deg);
    }
    50% {
      transform: translateY(-20px) rotate(8deg);
    }
  }

  /* BAllOON 2 5*/
  @-webkit-keyframes balloon2 {
    0%,
    100% {
      -webkit-transform: translateY(0) rotate(6eg);
    }
    50% {
      -webkit-transform: translateY(-30px) rotate(-8deg);
    }
  }
  @-moz-keyframes balloon2 {
    0%,
    100% {
      -moz-transform: translateY(0) rotate(6deg);
    }
    50% {
      -moz-transform: translateY(-30px) rotate(-8deg);
    }
  }
  @-o-keyframes balloon2 {
    0%,
    100% {
      -o-transform: translateY(0) rotate(6deg);
    }
    50% {
      -o-transform: translateY(-30px) rotate(-8deg);
    }
  }
  @keyframes balloon2 {
    0%,
    100% {
      transform: translateY(0) rotate(6deg);
    }
    50% {
      transform: translateY(-30px) rotate(-8deg);
    }
  }

  /* BAllOON 0*/
  @-webkit-keyframes balloon3 {
    0%,
    100% {
      -webkit-transform: translate(0, -10px) rotate(6eg);
    }
    50% {
      -webkit-transform: translate(-20px, 30px) rotate(-8deg);
    }
  }
  @-moz-keyframes balloon3 {
    0%,
    100% {
      -moz-transform: translate(0, -10px) rotate(6eg);
    }
    50% {
      -moz-transform: translate(-20px, 30px) rotate(-8deg);
    }
  }
  @-o-keyframes balloon3 {
    0%,
    100% {
      -o-transform: translate(0, -10px) rotate(6eg);
    }
    50% {
      -o-transform: translate(-20px, 30px) rotate(-8deg);
    }
  }
  @keyframes balloon3 {
    0%,
    100% {
      transform: translate(0, -10px) rotate(6eg);
    }
    50% {
      transform: translate(-20px, 30px) rotate(-8deg);
    }
  }

  /* BAllOON 3*/
  @-webkit-keyframes balloon4 {
    0%,
    100% {
      -webkit-transform: translate(10px, -10px) rotate(-8eg);
    }
    50% {
      -webkit-transform: translate(-15px, 20px) rotate(10deg);
    }
  }
  @-moz-keyframes balloon4 {
    0%,
    100% {
      -moz-transform: translate(10px, -10px) rotate(-8eg);
    }
    50% {
      -moz-transform: translate(-15px, 10px) rotate(10deg);
    }
  }
  @-o-keyframes balloon4 {
    0%,
    100% {
      -o-transform: translate(10px, -10px) rotate(-8eg);
    }
    50% {
      -o-transform: translate(-15px, 10px) rotate(10deg);
    }
  }
  @keyframes balloon4 {
    0%,
    100% {
      transform: translate(10px, -10px) rotate(-8eg);
    }
    50% {
      transform: translate(-15px, 10px) rotate(10deg);
    }
  }
</style>
