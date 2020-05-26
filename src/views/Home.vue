<template>
  <div class="home">
    <h1>Hello,</h1>
    <h1>I'm Aisha.</h1>
    <h1>I am a Frontend Engineer.</h1>
    <!-- <h1>
      <span class="typing-words">
        <span>I love building stuffs</span>
        <span>I love to play games</span>
        <span>I love to explore.</span>
      </span>
    </h1> -->
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

.home {
  height: 100vh;
  background: $black;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding-left: $base-gap * 3;

  h1 {
    font-family: "Piedra", cursive;
    color: $white;
    color: #fff;
    font-size: $base-font + 3;
    overflow: hidden;
    white-space: nowrap;
    letter-spacing: 0.15em;
    border-right: 4px solid orange;

    &:nth-child(1) {
      font-family: "Piedra", cursive;
      width: 13rem;
      animation: type1 2s steps(40, end);
      animation-fill-mode: forwards;
      margin-bottom: $base-gap * 2;
      margin-top: -$base-gap * 2;
    }
    &:nth-child(2) {
      width: 25rem;
      opacity: 0;
      animation: type2 2s steps(40, end);
      animation-delay: 2s;
      animation-fill-mode: forwards;
    }
    &:nth-child(3) {
      width: 60rem;
      opacity: 0;
      animation: type3 2s steps(40, end);
      animation-delay: 4s;
      animation-fill-mode: forwards;
    }
  }

  .typing-words span {
    position: absolute;
    overflow: hidden;
    white-space: nowrap;
    color: $white;
    visibility: hidden;
    border-right: 4px solid transparent;
    width: 30rem;
    &:nth-child(1) {
      animation: typing 0.7s steps(5), typingReverse 0.7s steps(5) 0.7s,
        blink-wait 1s step-end 1 1.4s, blink-caret 0.6s step-end infinite;
      // animation-delay: 6s;
    }
    &:nth-child(2) {
      animation: typing 0.7s steps(5) 2.4s, typingReverse 0.7s steps(5) 3.1s,
        blink-wait 1s step-end 1 3.8s, blink-caret 0.6s step-end infinite;
      // animation-delay: 7s;
    }
    &:nth-child(3) {
      animation: blink-caret 0.6s step-end 7 4.5s,
        typing 1s steps(7) 4.5s forwards;
      // animation-delay: 8s;
    }
  }

  /* The typing effect */
  @keyframes type1 {
    0% {
      width: 0;
    }
    99.9% {
      border-right: 0.15em solid orange;
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
      border-right: 0.15em solid orange;
    }
    100% {
      opacity: 1;
      border: none;
    }
  }
  @keyframes type3 {
    0% {
      width: 0;
    }
    1% {
      opacity: 1;
    }
    99.9% {
      border-right: 0.15em solid orange;
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
  /* The typewriter cursor effect */
  @keyframes blink-caret {
    from,
    to {
      border-color: transparent;
    }
    50% {
      border-color: orange;
    }
  }
}
</style>
