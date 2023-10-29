<template>
  <div class="container">
    <div class="rectangle">
      <div class="text">Obserwuj nas</div>
      <div class="buttons">
        <a class="facebook" href="https://www.youtube.com/watch?v=dQw4w9WgXcQ&t=2s" target="_blank">
          <i class="fab fa-facebook"></i> na Facebooku
        </a>
        <a class="instagram" href="https://www.youtube.com/watch?v=dQw4w9WgXcQ&t=2s" target="_blank">
          <i class="fab fa-instagram"></i> na Instagramie
        </a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.rectangle {
  background-color: #fff; /* Białe tło */
  border: 2px solid #000080; /* Granatowe obramowanie */
  border-radius: 10px;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  padding: 20px;
  text-align: center;
  color: #000;
}

.text {
  font-size: 24px;
}

.buttons {
  margin-top: 20px;
}

a {
  text-decoration: none;
}

a:hover {
  text-decoration: underline;
}

a.facebook {
  background-color: #3b5998;
  color: #fff;
  padding: 10px 20px;
  border-radius: 5px;
  margin-right: 10px;
}

a.instagram {
  background-color: #c13584;
  color: #fff;
  padding: 10px 20px;
  border-radius: 5px;
}
</style>