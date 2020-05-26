<template>
  <div class="container">
    <div class="logo">
      <img src="~@/assets/images/eshaa.svg" alt="eshaa" />
    </div>
    <main class="main">
      <h1>Hello,&#128075;&#127996;</h1>
      <h1>I'm Aisha, a Frontend Engineer.</h1>
      <h1>
        <span class="typing-words">
          <span>I love exploring...</span>
          <span>I love building stuffs...</span>
        </span>
      </h1>
    </main>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  methods: {}
};
</script>
<style lang="scss">
@import "@/assets/scss/_variables.scss";
.container {
  height: 100vh;
  background: $black;

  .logo {
    width: 200px;
    height: auto;
    cursor: pointer;
  }
  .main {
    display: flex;
    flex-direction: column;
    padding-left: $base-gap * 3;

    h1 {
      font-family: "Piedra", cursive;
      color: $white;
      color: #fff;
      font-size: $base-font + 3;
      overflow: hidden;
      white-space: nowrap;
      letter-spacing: 0.15em;
      border-right: 4px solid #d3d3d3;
      border-bottom: 10px solid #d3d3d3;

      &:nth-child(1) {
        width: 20rem;
        animation: type1 2s steps(40, end) forwards;
        margin-bottom: $base-gap * 2;
        margin-top: $base-gap * 5;
      }
      &:nth-child(2) {
        margin-top: $base-gap;
        width: 70rem;
        opacity: 0;
        animation: type2 2s steps(40, end) 2s forwards;
      }
      &:nth-child(3) {
        border-bottom: none;
      }
    }

    .typing-words span {
      position: absolute;
      overflow: hidden;
      white-space: nowrap;
      color: $white;
      border-right: 4px solid transparent;
      visibility: hidden;
      margin-top: $base-gap * 2;

      &:nth-child(1) {
        max-width: 38rem;
        animation: typing 0.7s steps(40) 4.5s, typingReverse 0.7s steps(40) 5.2s,
          blink-wait 1s step-end 1 6.2s, blink-caret 0.6s step-end infinite;
      }

      &:nth-child(2) {
        max-width: 49rem;
        animation: blink-caret 0.6s step-end 7 7.2s,
          typing 0.7s steps(40) 7.2s forwards;
      }
    }

    /* typing effect */
    @keyframes type1 {
      0% {
        width: 0;
      }
      99.9% {
        border-right: 0.15em solid #d3d3d3;
        border-bottom: 10px solid #d3d3d3;
      }
      100% {
        border: none;
      }
    }
    @keyframes type2 {
      0% {
        width: 0;
      }
      1% {
        opacity: 1;
      }
      99.9% {
        border-right: 0.15em solid #d3d3d3;
        border-bottom: 10px solid #d3d3d3;
      }
      100% {
        opacity: 1;
        border: none;
      }
    }
    @keyframes typing {
      from {
        width: 0;
        visibility: hidden;
      }

      to {
        width: 100%;
        visibility: visible;
        color: $white;
      }
    }
    /* clear text*/
    @keyframes typingReverse {
      from {
        width: 100%;
        visibility: visible;
        color: $white;
      }
      to {
        width: 0;
      }
    }
    /* typewriter blink effect */
    @keyframes blink-wait {
      from,
      to {
        width: 0;
        visibility: hidden;
      }
      30%,
      60% {
        width: 45px;
        visibility: visible;
      }
    }
    /* typewriter cursor effect */
    @keyframes blink-caret {
      from,
      to {
        border-color: transparent;
      }
      50% {
        border-color: #d3d3d3;
      }
    }
  }
}
</style>
