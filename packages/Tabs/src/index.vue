<template>
  <div>
    <div class="tabs">
      <div class="tabs-item" @click="change(index,item.id)" v-for="(item,index) in tabs" :class="index === active ? 'tabs-on' : '' ">
        {{item.content}}
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    name: 'BTabs',
    props: {
      tabs: {
        type: Array
      }
    },
    data() {
      return {
        active:0,
      }
    },
    mounted() {

    },
    methods: {
      change(index,id){
        this.active = index
        this.$emit('tabClick',id)
      }
    }
  }
</script>

<style scoped>

  .tabs{
    display: flex;
    justify-content: start;
  }

  .tabs-on{
    background-color: transparent;
    border-color: #00a1d6;
    color: #00a1d6;
    border-bottom: 1px solid #00a1d6;
  }

  .tabs-item{
    position: relative;
    height: 20px;
    line-height: 20px;
    cursor: pointer;
    padding: 1px 0 2px;
    font-size: 12px;
    margin: 0 6px;
  }

</style>
