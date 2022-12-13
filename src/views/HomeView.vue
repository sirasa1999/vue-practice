<template>
  <div>This is the Home Page.</div>
  
  <PractisePractise name="hello" />
  <NewView name="Rita" age=20 address="Ktm"/>
</template>

<script>
import PractisePractise from './PractisePractise.vue';
import NewView from './NewView.vue';

export default {
    name: "HomeView",
    components: { PractisePractise , NewView}
}
</script>

