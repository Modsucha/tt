<template>
  <v-app>
    <div class="conter">
      <center>
        <div class="post1">
          <img src="" alt="">
        </div>
        <div class="post2">
          <h1>กิจกรรมพิเศษ</h1>
          <p>วิทยาเทคนิคชัยภูมิ</p>
          <div class="py" />
        </div>
      </center>
    </div>
  </v-app>
</template>

<style>
  .conter{
    /*background-color: #5C6BC0;*/
    background-color: #0084AA;
    background-size: cover;
    height: 100vh;
  }
  .post2
  {
    color: rgb(252, 245, 245);
    padding-top: 30%;
  }
  .post2 h1{
    font-size: 48px;
  }
  .post2 p{
    font-size: 24px;
    padding-top: 5%;
  }
  .py{
    width: 182px;
    height: 10px;
    background-color: #5A598A;
    margin-top: -15px;
    margin-bottom: 150px;
  }
</style>

<script>
export default {
  created () {
    this.nextpage()
  },
  methods: {
    nextpage () {
      console.log('nextpage')
      setInterval(() => {
        this.$router.push('/inspire')
      }, 3000)
    }
  }
}
</script>
