<template>
  <main class="main">
    <h1 class="main__title">Страница контакты</h1>
  </main>
</template>

<script>
export default {
  name: 'Contacts',

  head: {
    title: 'Контакты',
  },
};
</script>

<style scoped lang="scss">
.main {
  display: flex;
  height: 400px;
  background-color: #faf4e8;
  align-items: center;
  justify-content: center;
}
.main__title {
  display: block;
}
</style>
