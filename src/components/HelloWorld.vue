<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <!-- <el-button @click='addClick(a+=3,b+=3)'>添加</el-button>
    <li v-for="value in dataInfo"  :key="value.key">{{value.name}}</li>

    <button
        v-for="tab in tabs"
        v-bind:key="tab"
        v-bind:class="['tab-button', { active: currentTab === tab }]"
        v-on:click="currentTab = tab"
        >{{ tab }}
    </button>
   <component
    :is="currentTabComponent"
    class="tab"
  ></component> -->
  <opt-item></opt-item>

  </div>
</template>

<script>
import Vue from 'vue';
import { Button } from 'element-ui';
import tab1 from  './tab1.vue';
import tab2 from  './tab2.vue';
import tab3 from  './tab3.vue';
import tab4 from  './tab4.vue';
import optItem from  './select_item.vue';
Vue.use(Button);
export default {
  name: 'HelloWorld',
  data () {
    return {
      activeName:'second',
      currentTab: 'tab1',
      tabs: ['tab1', 'tab2', 'tab3','tab4'],
      msg: 'Welcome to gjf vue',
      a:0,
      b:3,
      reviews:[
      {
          name:'111'
      },{
          name:'222'
      },{
          name:'333'
      },{
          name:'444'
      },{
          name:'555'
      },{
          name:'666'
      },{
          name:'777'
      },{
          name:'888'
      },{
          name:'999'
      },{
          name:'101'
      },{
          name:'102'
      }
      ],
      dataInfo:[]
    }
  },
  components:{
      tab1,
      tab2,
      tab3,
      tab4,
      optItem
      
  },
  methods: {
      handleClick(){},
    addClick(a,b) {
          this.reviews.slice(a, b).forEach((item)=>{
             this.dataInfo.push(item)
          })
    }
  },
  computed: {
    currentTabComponent: function () {
      return   this.currentTab;
    }
  },
  mounted() {
    this. addClick(0,3)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
.tab-button {
  padding: 6px 10px;
  border-top-left-radius: 3px;
  border-top-right-radius: 3px;
  border: 1px solid #ccc;
  cursor: pointer;
  background: #f0f0f0;
  margin-bottom: -1px;
  margin-right: -1px;
}
.tab-button:hover {
  background: #e0e0e0;
}
.tab-button.active {
  background: #e0e0e0;
}
.tab {
  border: 1px solid #ccc;
  padding: 10px;
}

</style>
