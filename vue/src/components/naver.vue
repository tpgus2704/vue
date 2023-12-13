<template>
  <div id="ex">
    <button class="ex-button" @click="doSomething">
      <span class="button-text">네이버 이동</span>
    </button>
  </div>
</template>

<script>
export default {
  methods: {
    doSomething() {
      window.open('https://www.naver.com', '_blank');
    },
  },
};
</script>

<style scoped>
.ex-button {
  background-color: rgb(87, 87, 249);
  color: #fff;
  border: none;
  padding: 5px;
  font-size: 16px;
  border-radius: 4px;
  cursor: pointer;
  display: flex;
  justify-content: flex-end;
  margin-left: auto;
  transition: all 0.3s;
  transform: scale(0.75);
}

.button-text {
  text-align: right;
  white-space: nowrap; /* Prevents the text from wrapping */
}

.ex-button:hover {
  background-color: blue;
}
</style>
