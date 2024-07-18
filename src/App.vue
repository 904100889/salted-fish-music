<template>
  <div>
    <leftColumn :modules="sidebarModules"></leftColumn>
    <main>
      <musicPlayer></musicPlayer>
    </main>
  </div>
</template>

<script setup lang="ts">
  import leftColumn from './components/left-column.vue'
  import musicPlayer from './components/music-player.vue';
  import {ref} from 'vue'
  
  const sidebarModules = ref([
    {title: '', items: [{icon: 'xxx', name: '为我推荐', path: '/'}, {icon: 'xxx', name: '云音乐精选', path: '/'}]},
    {title: '我的', items: [{icon: 'xxx', name: '我喜欢的音乐', path: '/'}, {icon: 'xxx', name: '本地音乐', path: '/'}]},
  ])

</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
