<template>
  <header>
    <h1>Gelato Production</h1>
    <nav>
      <a href="#intro">Intro</a>
      <a href="#ingredients">Ingredients</a>
      <a href="#process">Process</a>
    </nav>
  </header>
</template>

<script>
export default {};
</script>

<style scoped lang="scss">
header {
  width: 100%;
  background: rgba(0, 0, 0, 0.5);
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

header h1 {
  color: #fff;
  margin: 0;
  font-size: 24px;
}

nav {
  display: flex;
  gap: 20px;
}

nav a {
  color: #fff;
  text-decoration: none;
  font-size: 18px;
  transition: color 0.3s;
}

nav a:hover {
  color: #f0f0f0;
}
</style>
