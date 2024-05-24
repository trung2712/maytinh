<script >export default {
  name: 'NutBanPhim',
  props: {
    Nut: String,
    tennut : String
  },
  methods: {
    hienthi() {
      this.$emit('hienthi', this.Nut);
    }
  }
}


</script>

<template>
  <div >
    <div >
    <button @click="hienthi" class="btn"> {{Nut}}</button>
    </div>
  </div>

</template>

<style scoped>

.btn{
  padding: 10px;
  border-radius: 10px;
  font-size: 15px;
  width: 60px;
}

</style>