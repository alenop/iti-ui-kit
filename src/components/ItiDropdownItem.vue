<template>
  <iti-button color="primary" ><slot></slot></iti-button>

</template>

<style scoped>
.dropdown-menu-item {
  display: block;
  padding: 12px 8px;
  min-width: 100px;
}

.dropdown-menu-item:last-child {
  border-bottom: none;
}

.dropdown-menu-item:hover {
  background: var(--color-gray-light);
}
</style>
