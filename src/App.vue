<template>
  <div class="box">
    <div class="imgs">
      <img src="./assets/e3be97b73717f0f52f8c318e4dd0007.png" class="img" alt="" />
    </div>
    <div class="box1">
      <span v-for="(item, id) in arr" :key="id">
        <button :class="item.flag ? 'true' : 'false'" @click="fun(id)">
          <div>{{ item.title }}</div>
        </button>
        <b v-show="item.flag"></b>
      </span>
    </div>
    <div class="di">
      <transition name="fade">
        <components :is="flag"></components>
      </transition>
    </div>
  </div>
</template>

<script>
import mis from './components/mkl.js'

import AdfsdHgshjd from './components/AdfsdHgshjd.vue'
import BawetxKdbfn from './components/BawetxKdbfn.vue'
import EafshgUkljsdh from './components/EafshgUkljsdh.vue'
import GhsdjkfLgshd from './components/GhsdjkfLgshd.vue'
import MshgdkjGsdhj from './components/MshgdkjGsdhj.vue'

export default {
  name: 'App',
  mixins: [mis],
  mis: 'mis',

  data() {
    return {
      flag: 'BawetxKdbfn',
      num: 0,
      show3: true
    }
  },
  components: {
    BawetxKdbfn,
    MshgdkjGsdhj,
    AdfsdHgshjd,
    GhsdjkfLgshd,
    EafshgUkljsdh
  },
  created() {
    return this.arr
  },
  methods: {
    show(id) {
      this.num = id
      if (id == 0) {
        if (this.num == id) {
          this.show3 = true
        } else {
          this.show3 = false
        }
      } else {
        if (this.num == id) {
          this.show3 = true
        } else {
          this.show3 = false
        }
      }
    },
    fun(num) {
      this.arr.forEach((item, id) => {
        if (id == num) {
          item.flag = true
        } else {
          item.flag = false
        }
      })
      if (num + 1 == 1) {
        this.flag = 'BawetxKdbfn'
      } else if (num + 1 == 2) {
        this.flag = 'MshgdkjGsdhj'
      } else if (num + 1 == 3) {
        this.flag = 'AdfsdHgshjd'
      } else if (num + 1 == 4) {
        this.flag = 'GhsdjkfLgshd'
      } else if (num + 1 == 5) {
        this.flag = 'EafshgUkljsdh'
      }
    }
  }
}
</script>
<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.8s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
  transform: translateX(30px);
}

.transition-box {
  margin-bottom: 10px;
  width: 200px;
  height: 100px;
  border-radius: 4px;
  background-color: #409eff;
  text-align: center;
  color: #fff;
  padding: 40px 20px;
  box-sizing: border-box;
  margin-right: 20px;
}
.true {
  color: #1890ff !important;
}
.false {
  color: white !important;
}
.di {
  margin-top: 1%;
}
.imgs {
  width: 120px;
  margin: auto;
}
.box {
  width: 100%;
  height: 100vh;
  background: #1c1c1e;
}
button {
  background: #1c1c1e;
  color: #fff;
  margin-left: 5%;
  border: none;
  border-radius: 0;
}
b {
  display: block;
  height: 3px;
  background: #1890ff;
}
span {
  text-align: center;
  width: 80px;
}
.box1 {
  width: 95%;
  height: 5vh;
  margin: auto;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}
</style>
