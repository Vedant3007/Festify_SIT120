<template>
  <header class="site-header">
    <div class="header-container">

      <!-- Festify Branding -->
      <a href="#" class="brand" @click.prevent="$emit('navigate', 'home')">
        <span class="brand-name">Festify</span>
        <span class="brand-tagline">Celebrate more. Plan less.</span>
      </a>

      <!-- Navigation -->
      <nav class="main-navigation" aria-label="Main navigation">
        <button
          type="button"
          class="nav-link"
          :class="{ active: currentPage === 'home' }"
          @click="$emit('navigate', 'home')"
        >
          Home
        </button>

        <button
          type="button"
          class="nav-link"
          :class="{ active: currentPage === 'packages' }"
          @click="$emit('navigate', 'packages')"
        >
          Packages
        </button>

        <button
          type="button"
          class="nav-link"
          :class="{ active: currentPage === 'about' }"
          @click="$emit('navigate', 'about')"
        >
          Our Story
        </button>

        <button
          type="button"
          class="nav-cta"
          @click="$emit('navigate', 'planner')"
        >
          Plan My Celebration
        </button>
      </nav>

    </div>
  </header>
</template>

<script setup>
defineProps({
  currentPage: {
    type: String,
    default: 'home'
  }
})

defineEmits(['navigate'])
</script>