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
            @click="goDetail(item.targetUrl)"
            @mouseenter="enter(item)"
            @mouseleave="leave(item)"
          >
            <img :src="item.img" class="item-img" />
            <p v-if="!item.show" class="item-title">{{ item.title }}</p>
            <p v-if="item.show" class="item-intro">{{ item.intro }}</p>
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
              intro: '这是一个简单的提示',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DqWR00.md.jpg',
              title: 'MD笔记',
              targetUrl: '#',
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DqWylj.md.jpg',
              title: '时间戳转换',
              targetUrl: '#',
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DqW2mq.md.jpg',
              title: '颜色选取',
              targetUrl: '#',
              intro: '略',
              show: false
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
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
              show: false
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
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
              show: false
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
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/04/DqaRje.jpg',
              title: 'JSON格式化',
              targetUrl: '#',
              intro: '略',
              show: false
            }
          ]
        }
      ];
    },
    goDetail(url) {
      location.href = url;
    },
    enter(item) {
      item.show = true;
    },
    leave(item) {
      item.show = false;
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
        cursor: pointer;
        transition: all 0.2s;
        margin: 20px 20px;
        padding: 15px;
        display: flex;
        flex-direction: column;
        align-items: center;
        border-radius: 5px;
        background-color: #2c303a;
        position: relative;
        &:hover {
          transform: scale(1.03);
        }
        .item-img {
          width: 250px;
          height: 160px;
          border-radius: 3px;
        }
        .item-title {
          margin: 10px 0px auto;
          font-size: 15px;
        }
        .item-intro {
          position: absolute;
          top: 175px;
          color: rgb(200, 200, 200);
          font-size: 13px;
        }
      }
    }
  }
}
</style>
