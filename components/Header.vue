<template>
  <header class="header">
    <div class="header-content">
      <div class="left-section">
      </div>
      <div class="title-section">
        <div class="title">TotallyNotCalypso</div>
      </div>
      <div class="right-section">
        <div class="mycalypso-section">
          <button class="mycalypso-button" @click="toggleMycalypsoDropdown">myc@lypso</button>
        </div>
        <div class="language-section">
          <button class="language-button" @mouseover="showLanguageDropdown = true" @mouseout="showLanguageDropdown = false">
            {{ selectedLanguage }}
          </button>
          <div class="language-dropdown" :class="{ 'visible': showLanguageDropdown }">
            <button @click="changeLanguage('PL')">PL</button>
            <button @click="changeLanguage('ENG')">ENG</button>
          </div>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      showMycalypsoDropdown: false,
      showLanguageDropdown: false,
      selectedLanguage: 'PL',
    };
  },
  methods: {
    toggleMenu() {
      // Implement your menu toggle logic here
      console.log("Menu button clicked");
    },
    openSearch() {
      // Implement your search functionality here
      console.log("Search button clicked");
    },
    openUserProfile() {
      // Implement your user profile functionality here
      console.log("User button clicked");
    },
    toggleMycalypsoDropdown() {
      this.showMycalypsoDropdown = !this.showMycalypsoDropdown;
    },
    changeLanguage(language) {
      this.selectedLanguage = language;
      console.log(`Language changed to ${language}`);
    },
  },
};
</script>

<style scoped>
/* Import external CSS file */
@import './Header.css';
</style>
