<template>
  <div class="page-wrap">
    <!-- 主体 -->
    <section class="cate-wrap">
      <div v-for="(cate, cateIndex) in list"
           :key="cateIndex"
           class="cate">
        <p class="cate-title">{{ cate.category }}</p>
        <div class="item-wrap">
          <div v-for="(item, index) in cate.productList"
               :key="index"
               class="item">
            <img :src="item.img"
                 class="item-img" />
            <p class="item-title">{{ item.title }}</p>
          </div>
        </div>

      </div>
    </section>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data() {
    return {
      list: '',
    }
  },
  created() {
    this.init();
  },
  methods: {
    init() {
      this.list = [
        {
          category: '分类1',
          productList: [
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
            }
          ]
        },
        {
          category: '分类2',
          productList: [{
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          {
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          {
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          ]
        },
        {
          category: '分类3',
          productList: [{
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          {
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          {
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          ]
        },
        {
          category: '分类4',
          productList: [{
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          {
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          {
            img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
            title: 'JSON格式化',
            targetUrl: '#',
            intro: '略',
          },
          ]
        },

      ];
    },
  },
}
</script>

<style lang="less" scoped>
.page-wrap {
  background-color: #131417;
}
.cate-wrap {
  width: 80%;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  color: #fff;
  .cate {
    display: flex;
    flex-direction: column;
    .item-wrap {
      display: flex;
      justify-content: space-between;
      .item {
        width: 25%;
        display: flex;
        flex-direction: column;
        align-items: center;
        border-radius: 15px;
        background-color: #2C303A;
        .item-img {
            margin-top: 5%;
            width: 90%;
            border-radius: 10px;
        }
      }
    }
  }
}
</style>
