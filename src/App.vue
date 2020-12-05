<template>
  <div class="page-wrap">
    <div class="header-img">
      <img src="https://media.giphy.com/media/3o6Ztj6n6THmbi329y/giphy.gif" />
    </div>
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
          category: '前端作品集',
          productList: [
            {
              img: 'https://s3.ax1x.com/2020/12/05/DLMA4H.png',
              title: 'TodoList',
              targetUrl: '#',
              intro: 'Vue实现的待办事项',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DLMZ8A.jpg',
              title: 'Timeline Notes',
              targetUrl: '#',
              intro: '以时间线记录的笔记',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DLMuKP.jpg',
              title: '网址导航',
              targetUrl: '#',
              intro: '每个人应该有个自己的导航网址',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DLM1Ug.jpg',
              title: 'idea收集',
              targetUrl: '#',
              intro: '不要放掉一个闪念',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DLNjcF.jpg',
              title: 'Fliqlo在线版',
              targetUrl: '#',
              intro: 'web版翻页时钟',
              show: false
            }
          ]
        },
        {
          category: 'TODO...',
          productList: [
            {
              img: 'https://s3.ax1x.com/2020/12/05/DLKm0U.jpg',
              title: '...',
              targetUrl: '#',
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DLKm0U.jpg',
              title: '...',
              targetUrl: '#',
              intro: '略',
              show: false
            },
            {
              img: 'https://s3.ax1x.com/2020/12/05/DLKm0U.jpg',
              title: '...',
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

.header-img {
  width: 100%;
  img {
    width: 100%;
    height: 400px;
    object-fit: cover;
  }
}

.cate-wrap {
  padding-top: 80px;
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
        width: 250px;
        height: 190px;
        cursor: pointer;
        transition: all 0.2s;
        margin: 20px 20px;
        padding: 10px;
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
          top: 167px;
          color: rgb(200, 200, 200);
          font-size: 13px;
        }
      }
    }
  }
}
</style>
