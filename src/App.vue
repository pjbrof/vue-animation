<template>
  <div>
    <Transition name="fade-in-next" appear>
      <div>Title</div>
    </Transition>
    <Transition name="fade-in-next" appear>
      <div>Subtitle</div>
    </Transition>
    <div class="card-grid">
      <TransitionGroup tag="ul" name="fade-list" appear>
        <li v-for="n in 3" :key="n">
          <span>Lorem ipsum dolor este met</span>
        </li>
      </TransitionGroup>
    </div>
  </div>
</template>

<script setup></script>

<style lang="scss" scoped>
.card-grid {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 2rem;
}

.card {
  border: 1px solid #ddd;
  border-radius: 1rem;
  padding: 1.5rem;

  span {
    color: red;
  }
}

@for $i from 1 through 10 {
  .fade-list-enter-active:nth-child(#{$i}n),
  .fade-list-leave-active:nth-child(#{$i}n) {
    transition: transform 1s ease #{$i * 0.5}s, opacity 1s ease #{$i * 0.5}s;
  }
}

.fade-list-enter-active,
.fade-list-leave-active {
  transition: all 0.5s ease;
}

.fade-list-enter-from,
.fade-list-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}

.fade-in-next-enter-active,
.fade-in-next-leave-active {
  transition: all 2s ease 0.5s;
}

.fade-in-next-enter-from,
.fade-in-next-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}

.fade-left-enter-from,
.fade-left-leave-to {
  opacity: 0;
  transform: translateX(-100px);
}

.fade-left-enter-active,
.fade-left-leave-active {
  transition: transform 2s ease-in-out;
}
</style>
