<template>
  <div id="app" class="min-vh-100">
    <div id="point-cursor" class="cursor"></div>

    <div
      class="
        jumbotron
        d-flex
        justify-content-center
        align-items-center
        flex-column
        min-vh-100
        p-4
      "
    >
      <div class="header text-center mb-4">
        <div id="home">
          <router-link to="/" style="text-decoration: none; color: inherit"
            >Ana Sayfa</router-link
          >
        </div>
        <div id="projects">
          <router-link
            to="/projects"
            style="text-decoration: none; color: inherit"
            >Projelerim</router-link
          >
        </div>
        <div id="skills">
          <a
            style="text-decoration: none; color: inherit"
            target="__blank"
            href="https://discord.com/users/852603732494647347"
            >Discord</a
          >
        </div>
		<div id="skills">
          <a
            style="text-decoration: none; color: inherit"
            target="__blank"
            href="https://instagram.com/wizard.diss/"
            >Instagram</a
          >
        </div>
        <div id="skills">
          <a
            style="text-decoration: none; color: inherit"
            target="__blank"
            href="https://github.com/ben-wizard"
            >Github</a
          >
        </div>
      </div>
      <router-view />
    </div>

    <div
      id="author"
      style="
        position: absolute;
        bottom: 0;
        width: max-content;
        left: 50%;
        transform: translate(-50%, -50%);
        color: #52057b;
      "
    ></div>
  </div>
</template>

<script>

export default {
  mounted() {
    let pointCursor = document.getElementById("point-cursor");
    window.addEventListener("mousemove", (ev) => {
      let x = ev.clientX;
      let y = ev.clientY;

      pointCursor.style.top = `${y}px`;
      pointCursor.style.left = `${x}px`;
    });
  },
};
</script>

<style lang="scss">
$primary: #000000;
$secondary: #52057b;
$tertiary: #892cdc;
$quaternary: #bc6ff1;

@import url("https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;400;500;600&display=swap");

* {
  font-family: "Roboto Mono", monospace;
  cursor: none;
}

::selection {
  background-color: $quaternary;
}

h1,
h2,
h3,
h4,
h5,
h6,
span {
  color: $tertiary;
}

::-webkit-scrollbar {
  background-color: $primary;
}

::-webkit-scrollbar-track {
  border-radius: 10px;
}

::-webkit-scrollbar-thumb {
  background: $secondary; 
  border-radius: 10px;
}

body,
html {
  overflow-x: hidden;
  padding: 0;
  margin: 0;
  height: 100%;
  min-height: 100vh;
  min-width: 100vw;
  background-color: $primary;
}

.header {
  display: flex;
  width: 100%;
  justify-content: center;

  div,
  div router-link {
    padding: 5px 15px 5px 15px;
    color: whitesmoke;
    height: auto;

    transition: background-color 100ms ease-in-out;
    background-color: $tertiary;

    &:hover {
      background-color: $quaternary;
      color: $tertiary;
    }
  }
}

.cursor {
  position: absolute;
  pointer-events: none;
  visibility: visible;
  transform: translate(-50%, -50%);
  border-radius: 50%;
  opacity: 0.4;
  box-shadow: 0 0 15px $tertiary;
  width: 25px;
  height: 25px;
  z-index: 1000;
  background-color: $quaternary;
}

.text-center {
  text-align: center !important;
}

.underline {
  text-decoration: underline !important;
}

.uppercase {
  text-transform: uppercase !important;
}

.primary {
  color: $primary !important;
}

.secondary {
  color: $secondary !important;
}

.tertiary {
  color: $tertiary !important;
}

.quaternary {
  color: $quaternary !important;
}

.green {
  color: rgb(156, 248, 156) !important;
}

.border-dotted-block {
  padding: 10px;
  border: 2px $secondary dotted;

  height: 100%;

  transition: all 100ms ease-in-out;

  &:hover {
    background-color: $secondary;
  }
}

.tag {
  padding: 10px;
  margin: 5px;
  color: whitesmoke;
  border: 1px #b7ffb0 dashed;
  width: max-content;
}
</style>
