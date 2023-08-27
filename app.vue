<template>
  <div>
    <h1>Hello world - this is marius!</h1>
    <h1>This is marius homepage</h1>
    <p>Here you can play fun games -Coming soon!</p>
  </div>
</template>

<style>
body {
  background-color: var(--bg-color, rgb(0, 162, 255));
  padding: 20px;
  transition: background-color 0.3s ease; /* Add transition for smooth color change */
}

.page-container {
  background-color: rgb(255, 255, 255);
  padding: 20px;
}
</style>

<script>
export default {
  methods: {
    changeBackgroundColor() {
      // Generate a random color
      const randomColor = `rgb(${Math.floor(Math.random() * 256)}, ${Math.floor(
        Math.random() * 256
      )}, ${Math.floor(Math.random() * 256)})`;

      // Apply the random color to the --bg-color custom property
      document.documentElement.style.setProperty("--bg-color", randomColor);
    },
  },
  mounted() {
    // Add a click event listener to the body element
    document.body.addEventListener("click", this.changeBackgroundColor);
  },
  beforeDestroy() {
    // Remove the click event listener when the component is destroyed
    document.body.removeEventListener("click", this.changeBackgroundColor);
  },
};
</script>
