<template>
  <div id="app">
    <div class="language-switcher">
      <button @click="changeLanguage('en')" :class="{ active: isActive('en') }">English</button>
      <button @click="changeLanguage('zh')" :class="{ active: isActive('zh') }">中文</button>
    </div>
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App',
  methods: {
    changeLanguage(lang) {
      this.$i18n.locale = lang;
    },
    isActive(lang) {
      return this.$i18n.locale === lang;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.language-switcher {
  margin-bottom: 20px;
}

.language-switcher button {
  background-color: #f0f0f0;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 10px 20px;
  margin: 0 10px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}

.language-switcher button.active {
  background-color: #007bff;
  color: white;
  border-color: #007bff;
}

.language-switcher button:hover {
  background-color: #e0e0e0;
}

.language-switcher button:focus {
  outline: none;
}
</style>
