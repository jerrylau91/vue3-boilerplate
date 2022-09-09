<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>Hover the number to see animation</p>
    <div class="counter"></div>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
}

@property --num {
  syntax: "<integer>";
  initial-value: 0;
  inherits: false;
}

.counter {
  transition: --num 5s;
  counter-set: num var(--num);
  font: 800 40px system-ui;
  margin-top: 30px;
}

.counter:hover {
  --num: 100;
}

.counter::after {
  content: counter(num);
}
</style>
