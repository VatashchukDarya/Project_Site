<script setup>
import { ref } from 'vue';

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
  document.body.classList.toggle('hidden');
  document.querySelector('html').classList.toggle('hidden');
};
</script>

<template>
    <header>
    <div class="menu"></div>  
      <nav class="navigation mb-5 mt-5">
        <div class="container">
          <div class="navigation__wrap">
            <div class="navigation__logo">
              <img src="/public/logo.svg" alt="">
            </div>
            <button class="navigation__menu-button" id="navigation__menu-button" @click="toggleMenu">
              <span></span>
              <span></span>
              <span></span>
            </button>
            <div class="navigation__menu" :class="{open: isMenuOpen }">
              <ul class="navigation__list">
                <li><a href="">Возможности</a></li>
                <li><a href="">Как это работает?</a></li>
              </ul>
              <div class="navigation__refs">
                <ul class="navigation__refs-list" :class="{open: isMenuOpen }">
                  <li>г Сургут, ул Базовая, д. 34, офис 10</li>
                  <li>ОГРН 1238600001200ИНН</li>
                  <li>8602309464</li>
                  <li>ООО Дотсолюшн © 2023</li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </nav>
    </header>
</template>

<style scoped> /*область видимости стиля*/

</style>