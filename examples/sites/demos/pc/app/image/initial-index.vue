<template>
  <div>
    <h4>默认从第一张图片开始预览</h4>
    <tiny-image :src="urlList[0]" :preview-src-list="urlList" @change-index="handleChangeIndex"></tiny-image>

    <h4 class="mt-4">指定从第三张图片开始预览 (initial-index=2)</h4>
    <tiny-image
      :src="urlList[2]"
      :preview-src-list="urlList"
      :initial-index="2"
      @change-index="handleChangeIndex"
    ></tiny-image>

    <div class="mt-4">
      <p>当前预览图片索引: {{ currentIndex }}</p>
    </div>
  </div>
</template>

<script>
import { Image } from '@opentiny/vue'

export default {
  components: {
    TinyImage: Image
  },
  data() {
    return {
      urlList: [
        'https://cube.elemecdn.com/6/94/4d3ea53c084bad6931a56d5158a48jpeg.jpeg',
        'https://fuss10.elemecdn.com/e/5d/4a731a90594a4af544c0c25941171jpeg.jpeg',
        'https://fuss10.elemecdn.com/3/28/bbf893f792f03a54408b3b7a7ebf0jpeg.jpeg',
        'https://fuss10.elemecdn.com/1/8e/aeffeb4de74e2fde4bd74fc7b4486jpeg.jpeg'
      ],
      currentIndex: 0
    }
  },
  methods: {
    handleChangeIndex(index) {
      this.currentIndex = index
    }
  }
}
</script>

<style scoped>
.mt-4 {
  margin-top: 1rem;
}
</style>
