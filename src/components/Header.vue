<template>
  <div>
    <div class="nav-menu">
      <div class="flex justify-between icon-cover">
        <div class="home-icon-mobile" @click="$emit('goTo', 'MainPage')">
          <img src="../assets/home.png" class="w-6 h-6 cursor-pointer" />
        </div>
        <div @click="clickMenu" class="nav-icon">
          <img src="../assets/burger-icon.png" class="w-6 h-6 cursor-pointer" />
        </div>
      </div>
      <div class="nav-content" :class="showMenu ? 'open-menu' : 'closed-menu'">
        <div class="home-icon" @click="$emit('goTo', 'MainPage')">
          <img src="../assets/home.png" class="w-6 h-6 cursor-pointer" />
        </div>
        <ul class="nav-items">
          <li
            @click="
              $emit('goTo', 'AboutPage');
              closeMenu();
            "
          >
            About
          </li>
          <li
            @click="
              $emit('goTo', 'CollectionPage');
              closeMenu();
            "
          >
            Collection
          </li>
          <li
            @click="
              $emit('goTo', 'ContactPage');
              closeMenu();
            "
          >
            Contact
          </li>
        </ul>
      </div>
    </div>
    <div class="bg-black">
      <img
        class="w-full"
        :src="
          require(windowWidth < 768
            ? '../assets/NoFaceTribe-mobile.png'
            : '../assets/NoFaceTribe.png')
        "
      />
    </div>
  </div>
</template>

<script>
  import { ref } from "vue";
  export default {
    setup() {
      let showMenu = ref(false);
      function clickMenu() {
        showMenu.value = !showMenu.value;
      }

      function closeMenu() {
        showMenu.value = false;
      }

      const windowWidth = ref(window.screen.width);

      return { showMenu, clickMenu, windowWidth, closeMenu };
    },
  };
</script>

<style scoped>
  .icon-cover {
    padding: 0;
    margin: 0;
  }
  .home-icon-mobile {
    display: none;
  }
  .home-icon {
    display: block;
  }
  .nav-menu {
    background-color: #f83b2f;
  }
  .nav-content {
    display: flex;
    justify-content: space-between;
    padding: 10px 30px;
    align-items: center;
  }
  .nav-items {
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
    list-style: none;
    margin: 0;
    padding: 0;
  }

  .nav-icon {
    display: none;
  }

  @media screen and (max-width: 768px) {
    .icon-cover {
      margin: 10px 20px;
    }
    .home-icon-mobile {
      display: block;
    }
    .home-icon {
      display: none;
    }
    .nav-menu {
      padding-top: 10px;
      position: absolute;
      width: 100%;
    }
    .open-menu {
      opacity: 1;
      height: 100%;
    }
    .closed-menu {
      opacity: 0;
      height: 0;
      padding: 0;
    }
    .nav-content {
      flex-direction: column;
      z-index: 100;
      position: relative;
      transition: all 0.2s ease-out;
    }
    .nav-items {
      flex-direction: column;
    }
    .nav-icon {
      display: block;
      text-align: right;
    }
  }

  li {
    margin: 10px;
    padding: 5px 10px;
    border-bottom: 4px solid #f83b2f;
    border-left: 4px solid #f83b2f;
    border-radius: 5px;
    font-size: 18px;
  }

  li:hover {
    background-color: white;
    border-bottom: 4px solid black;
    border-left: 4px solid black;
    cursor: pointer;
  }
</style>
