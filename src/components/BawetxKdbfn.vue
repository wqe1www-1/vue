<template>
  <div class="box2">
    <div class="div1">
      <el-input confirm-type="search" v-model="that" placeholder="请输入内容"></el-input>
      <div>
        <div class="tabs">
          <div v-for="(tab, index1) in search(that)" :key="index1" :class="{ active: activeTab === index1 }" @click="changeTab(index1)">
            <img class="id" :src="tab.imgs" alt="" />
            <span class="ziti"> {{ tab.name }} </span>
          </div>
        </div>
      </div>
    </div>
    <div class="div2">
      <div>
        <div class="aop" v-for="(tab, index) in list1" v-show="activeTab === index" :key="index">
          <span class="appsj"> {{ tab.content }} </span>
          <img class="id" :src="tab.imgs" alt="" />
        </div>
        <ul v-for="(item, inde) in list" :key="inde">
          <li>
            <div class="diyi" :style="{ backgroundColor: getBoxColor(inde) }">{{ item.id }}</div>
            <span class="zhong">{{ item.xiangqing }}</span>
            <span class="pian">{{ item.dian }}</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import mis from '../components/mkl.js'

export default {
  name: 'BawetxKdbfn',
  mixins: [mis],
  data() {
    return {
      activeTab: 0,

      list1: [
        {
          id: 1,
          name: '微信',
          imgs: 'https://files.codelife.cc/topsearch/WnBe01o371.png',
          content: '微信·24h热文榜'
        },
        {
          id: 2,
          name: 'it之家',
          imgs: 'https://files.codelife.cc/topsearch/Y2KeDGQdNP.png',
          content: '少数派·热门文章'
        },
        {
          id: 3,
          name: '百度',
          imgs: '	https://files.codelife.cc/topsearch/Jb0vmloB1G.png',
          content: '百度贴吧·热议榜'
        }
      ],
      mis: 'mis',
      that: ''
    }
  },
  components: {},

  created() {
    return this.list
  },
  methods: {
    search(that) {
      return this.list1.filter(item => {
        if (item.name.includes(that)) {
          return item
        }
      })
    },
    changeTab(index1) {
      this.activeTab = index1
    },
    getBoxColor(inde) {
      if (inde === 0) {
        return 'red'
      } else if (inde === 1) {
        return 'green'
      } else if (inde === 2) {
        return 'yellow'
      }
    }
  }
}
</script>

<style scoped>
.appsj {
  color: #fff;
  font-size: 20px;
  margin-left: 2%;
  margin-top: 7%;
}
.aop {
  margin-left: 4%;
  margin-bottom: 5%;
}
.zisd {
  width: 100%;
  margin: auto;
  height: 34px;
  color: #c6c6c7;
  margin-top: 20px;
}
.ziti {
  float: left;
  margin-left: 5%;
  margin-top: 3%;
}
.id {
  width: 35px;
  height: 35px;
  float: left;
}
.pian {
  float: right;
  font-size: 12px;
}
.tabs {
  width: 100%;
  color: #fff;
}

.tabs div {
  float: left;
  width: 85%;
  margin-top: 30px;
  padding: 10px 20px;
  cursor: pointer;
}

.tabs div.active {
  background-color: #1890ff;
  color: #fff;
}

.tab-content div {
  display: none;
}

.tab-content div.show {
  display: block;
}
ul li {
  list-style: none;
  color: #c6c6c7;
  font-weight: 100;
}
.diyi {
  width: 2%;
  height: 8%;
  text-align: center;
  float: left;
}
.zhong {
  margin-left: 3%;
}
.box2 {
  width: 98%;
  height: 80vh;
  background: #1c1c1e;
  margin: auto;
}
.div1 {
  width: 18%;
  height: 80vh;
  float: left;
}
.div2 {
  width: 70%;
  float: left;
  margin-left: 3%;
  height: 80vh;
}
</style>
