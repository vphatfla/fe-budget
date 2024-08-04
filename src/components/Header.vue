<template>
  <header class="header">
    <div class="container">
      <h1 class="logo">Cow Pig Budget Tracking</h1>
      <nav class="nav">
        <ul>
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/contact">Contact</router-link></li>
           <github-button
            href="https://github.com/vphatfla"
            data-color-scheme="no-preference: light; light: light; dark: dark;"
            data-size="large"
            aria-label="Follow @buttons on GitHub"
            >Follow @vphatfla</github-button>
        </ul>

      </nav>
    </div>
  </header>
</template>

<script>
import GithubButton from 'vue-github-button'
export default {
  name: 'Header',
  components: {GithubButton}
}
</script>

<style scoped>
.header {
  background-color: #cdcdcd2e;
  color: #000000;
  padding: 0.75rem;
  position: fixed;
  width: 100%;
  top: 0;
  left: 0;
  z-index: 1000;
}

.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 1rem;
}

.logo {
  font-size: 1.5rem;
}

.nav ul {
  list-style: none;
  display: flex;
  gap: 1rem;
}

.nav a {
  color: #000000;
  text-decoration: none;
}

.nav a:hover {
  text-decoration: underline;
}
</style>
