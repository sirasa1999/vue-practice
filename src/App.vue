<template>
  <nav class="bg-purple-600 text-white">
    <div class="container mx-auto">
      <div class="flex items-center">
        <router-link to="/"
                     class="inline-block px-16 py-4 transition-colors hover:bg-purple-500">Home</router-link>
        <router-link to="/todos"
                     class="inline-block px-16 py-4 transition-colors hover:bg-purple-500">Todo List</router-link>
      </div>
    </div>
  </nav>
  <router-view />
</template>

<!-- <style>
</style> -->
