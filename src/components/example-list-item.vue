<template>
  <list-item v-on:click="redirect">
    <text class="item-txt">{{title}}</text>
  </list-item>
</template>

<style>
  .item-txt {
    font-size: 48px;
    color: #555;
  }
</style>

<script>
var event = weex.requireModule('event');
// var navigator = weex.requireModule('navigator')
// var modal = weex.requireModule('modal')
  module.exports = {
    props: {
      title: { default: '456' },
      url: { default: '' }
    },
    components: {
      listItem: require('./list-item.vue')
    },
    methods: {
      redirect: function() {
        console.log('this.url='+this.url);
        // navigator.push({
        //   // url: this.url,
        //   url:'file://assets/views/Couter.js',
        //   animated: "true"
        // }, event => {
        //   modal.toast({ message: 'callback: ' + event, duration: 0.3})
        // })
        event.openURL(this.url);
      }
    }
  }
</script>
