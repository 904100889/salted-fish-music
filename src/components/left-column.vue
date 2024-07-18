<template>
  <aside class="salte-column">
    <header class="salte-logo mb-tiny">
      <img src="../assets/images/logo.jpg" alt="">
      <h1>咸鱼天音乐</h1>
    </header>
    <nav class="sidebar-nav">
      <section class="sidebar-section" v-for="(module, index) in modules" :key="index">
        <h3 v-if="module.title" class="sidebar-section-title">{{ module.title }}</h3>
        <ul class="sidebar-section-content">
          <li v-for="(item, idx) in module.items" :key="idx">
            <i :class="item.icon"></i>
            <a :href="item.path">{{ item.name }}</a>
          </li>
        </ul>
      </section>
    </nav>
  </aside>
</template>


<script lang="ts" setup>
interface ModulesItem {
  icon: string,
  path: string,
  name: string
}

interface Module {
  title: string,
  items: ModulesItem[]
}

const props = defineProps<{
  modules: Module[]
}>()

const { modules } = props

</script>

<style>
  .salte-column {
    padding: 10px 0 10px 30px;
    width: 200px;
    background-color: #f0e9df;
    height: 98vh;
  }

  .salte-logo > img {
    width: 32px;
    height: 32px;
    border-radius: 16px;
  }

  .salte-logo > h1 {
    display: inline-block;
    margin-left: 8px;
    vertical-align: middle;
    font-size: 16px;
  }

  .sidebar-section {
    margin-top: 30px;
  }

  .sidebar-section-title {
    margin-bottom: 10px;
    font-size: 12px;
    color: #666;
  }
</style>
