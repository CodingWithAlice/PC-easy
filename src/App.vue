<template>
  <div class="page-wrap">
    <!-- 主体 -->
    <section class="cate-wrap">
      <div v-for="(cate, cateIndex) in list" :key="cateIndex" class="cate">
        <div class="cate-title">
          <p>{{ cate.category }}</p>
        </div>
        <div class="item-wrap">
          <div
            v-for="(item, index) in cate.productList"
            :key="index"
            class="item"
          >
            <img :src="item.img" class="item-img" />
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
      list: ''
    };
  },
  created() {
    this.init();
  },
  methods: {
    init() {
      this.list = [
        {
          category: '作品集',
          productList: [
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DqWR00.md.jpg',
              title: 'MD笔记',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DqWylj.md.jpg',
              title: '时间戳转换',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DqW2mq.md.jpg',
              title: '颜色选取',
              targetUrl: '#',
              intro: '略'
            }
          ]
        },
        {
          category: '分类2',
          productList: [
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            }
          ]
        },
        {
          category: '分类3',
          productList: [
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            }
          ]
        },
        {
          category: '分类4',
          productList: [
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略'
            }
          ]
        }
      ];
    }
  }
};
</script>

<style lang="less">
body {
  margin: 0;
  padding: 0;
  background-color: #131417;
}
.page-wrap {
  padding-top: 80px;
}
.cate-wrap {
  width: 960px;
  margin: 0 auto;
  color: #fff;
  .cate {
    margin-bottom: 50px;
    .cate-title {
      margin: 10px 20px;
      p {
        margin-left: 5px;
        font-size: 25px;
        margin-bottom: 10px;
      }
      border-bottom: 1px solid #2c303a;
    }
    .item-wrap {
      display: flex;
      flex-wrap: wrap;
      .item {
        margin: 20px 20px;
        padding: 15px;
        display: flex;
        flex-direction: column;
        align-items: center;
        border-radius: 5px;
        background-color: #2c303a;
        .item-img {
          width: 250px;
          height: 160px;
          border-radius: 3px;
        }
        .item-title {
          margin: 10px 0px auto;
          font-size: 15px;
        }
      }
    }
  }
}
</style>
