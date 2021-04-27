<template>
  <div class="nav">
    <div class="nav__arrow">
      <div class="nav__arrow_next" @click="nextSlide">
        <svg width="89" height="89" viewBox="0 0 89 89" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle cx="44.6614" cy="44.6614" r="43.6614" stroke="#C8C8C8"/>
          <path d="M25.9471 43.5586H62.5215V45.8466H25.9471V43.5586Z" fill="#242424" stroke="#242424"
                stroke-width="0.5"/>
          <path
            d="M62.5206 44.7038V41.8781L50.3024 29.1452L51.9498 27.5664L64.8086 40.9629V44.7038V48.4448L51.9498 61.8413L50.3024 60.2625L62.5206 47.5296V44.7038Z"
            fill="#242424" stroke="#242424" stroke-width="0.5"/>
        </svg>
      </div>
      <div class="nav__arrow_prev" @click="prevSlide">
        <svg width="90" height="89" viewBox="0 0 90 89" fill="none" xmlns="http://www.w3.org/2000/svg">
          <circle r="43.6614" transform="matrix(-1 0 0 1 44.862 44.4231)" stroke="#C8C8C8"/>
          <path d="M63.5782 43.3164H27.0039V45.6044H63.5782V43.3164Z" fill="#242424" stroke="#242424"
                stroke-width="0.5"/>
          <path
            d="M27.0029 44.4616V41.6359L39.221 28.903L37.5736 27.3242L24.7148 40.7207V44.4616V48.2026L37.5736 61.5991L39.221 60.0203L27.0029 47.2874V44.4616Z"
            fill="#242424" stroke="#242424" stroke-width="0.5"/>
        </svg>
      </div>
    </div>
    <transition-group name="list" tag="div" class="nav__lang">
      <span v-for="item in langs" :key=item.name class="list-item">
        {{ item.name }}
      </span>
    </transition-group>
    <ul class="nav__menu">
      <li class="nav__menu_item">
        <div>
          <NuxtLink to="/" exact>HOME</NuxtLink>
        </div>
      </li>
      <li class="nav__menu_item">
        <div>
          <NuxtLink to="#">PROJECTS</NuxtLink>
        </div>
      </li>
      <li class="nav__menu_item">
        <div>
          <NuxtLink to="#">About</NuxtLink>
        </div>
      </li>
      <li class="nav__menu_item">
        <div>
          <NuxtLink to="#">SERVICES</NuxtLink>
        </div>
      </li>
      <li class="nav__menu_item">
        <div>
          <NuxtLink to="#">CONTACT</NuxtLink>
        </div>
      </li>
    </ul>
  </div>


</template>

<script>
    export default {
        name: "SideBar",
        data: () => ({
            langs: [
                {name: 'EN'}, {name: 'RU'}, {name: 'UA'}
            ]
        }),
        methods: {
            prevSlide() {
                this.$emit("show-prev-slide")
            },
            nextSlide() {
                this.$emit("show-next-slide")
            },

        }

    }
</script>

<style>


</style>
