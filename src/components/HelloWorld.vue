<template>
  <div>
    <p>hello</p>
    <p>{{ msg }}</p>
    <p @click="hideText">{{ notify }}</p>
    <p v-if="isVisible">Visible Text</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: {
      type: String,
      default: 'Hello',
      required: true
    }
  },
  data(){
    return{
      isVisible: true,
      notify: 'Hide'
    }
  },
  methods:{
    hideText(){
      this.isVisible =!this.isVisible;
      this.$emit('helloText', this.isVisible ? "My name is " : "Burak"); 
      if (this.isVisible === true){
        this.notify = 'Hide';
      }else{
        this.notify = 'Show';
      }
    }
  }

}

</script>

<style></style>
