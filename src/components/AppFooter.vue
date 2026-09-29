<template>
  <footer class="site-footer">
    <div class="footer-container">

      <!-- Footer Brand -->
      <div class="footer-brand">
        <h2>Festify</h2>
        <p>
          Smart celebration planning made simple.
          Celebrate more. Plan less.
        </p>
      </div>

      <!-- Contact Details -->
      <div class="footer-contact">
        <h3>Contact</h3>
        <p>Email: hello@festify.example</p>
        <p>Phone: +61 400 123 456</p>
        <p>Melbourne, Australia</p>
      </div>

      <!-- Secondary Navigation -->
      <div class="footer-links">
        <h3>Explore</h3>

        <button type="button" @click="$emit('navigate', 'home')">
          Home
        </button>

        <button type="button" @click="$emit('navigate', 'packages')">
          Packages
        </button>

        <button type="button" @click="$emit('navigate', 'about')">
          Our Story
        </button>

        <button type="button" @click="$emit('navigate', 'planner')">
          Celebration Planner
        </button>
      </div>

    </div>

    <div class="footer-bottom">
      <p>
        © 2026 Festify. Fictional website created for SIT120.
      </p>
    </div>
  </footer>
</template>

<script setup>
defineEmits(['navigate'])
</script>