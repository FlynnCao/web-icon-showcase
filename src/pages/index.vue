<script setup lang="ts">
import axios from 'axios'

interface Info {
  home: InfoItem
  explorer: InfoItem
  article: InfoItem
  learning: InfoItem
  review: InfoItem
  repository: InfoItem
  collection: InfoItem
  record: InfoItem
  upload: InfoItem
  contact: InfoItem
  extension: InfoItem
  sponsor: InfoItem
  user: InfoItem
}

interface InfoItem {
  id: number
  title: string
  list: string[]
}
const data = ref<Info | null>(null)

onMounted(() => {
  axios.get('icons.json').then((res) => {
    data.value = res.data
  })
})
</script>

<template>
  <h1 class=" text-red-500">
    在下面点击选择你喜欢的图标
  </h1>
  <i class="fi fi-br-search" />
  <h2>主页</h2>
  <TransIcon v-for="(item, index) in data?.home?.list" :key="index" :class-name="item" />
  <h2>探索</h2>
  <TransIcon v-for="(item, index) in data?.explorer?.list" :key="index" :class-name="item" />
  <h2>文章</h2>
  <TransIcon v-for="(item, index) in data?.article?.list" :key="index" :class-name="item" />
  <h2>学习词块</h2>
  <TransIcon v-for="(item, index) in data?.learning?.list" :key="index" :class-name="item" />
  <h2>复习词块</h2>
  <TransIcon v-for="(item, index) in data?.review?.list" :key="index" :class-name="item" />
  <h2>词块库</h2>
  <TransIcon v-for="(item, index) in data?.repository?.list" :key="index" :class-name="item" />
  <h2>文章收藏</h2>
  <TransIcon v-for="(item, index) in data?.collection?.list" :key="index" :class-name="item" />
  <h2>学习记录</h2>
  <TransIcon v-for="(item, index) in data?.record?.list" :key="index" :class-name="item" />
  <h2>上传文章</h2>
  <TransIcon v-for="(item, index) in data?.upload?.list" :key="index" :class-name="item" />
  <h2>联系我们</h2>
  <TransIcon v-for="(item, index) in data?.contact?.list" :key="index" :class-name="item" />
  <h2>拓展服务</h2>
  <TransIcon v-for="(item, index) in data?.extension?.list" :key="index" :class-name="item" />
  <h2>捐赠我们</h2>
  <TransIcon v-for="(item, index) in data?.sponsor?.list" :key="index" :class-name="item" />
</template>

<route lang="yaml">
meta:
  layout: home
</route>
