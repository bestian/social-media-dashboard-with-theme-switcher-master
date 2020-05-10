<template>
  <div class="hello">
    <div class="ui grid container">
      <div class = "row">
        <div class="twelve wide column">
          <h1 class="ui header">
            Social Media Dashboard
            <div class="sub header">
              Total Followers: 23,004
            </div>
          </h1>
        </div>
        <div class="four wide column">
          <div class="inline field">
            <sui-form-field>
              <label>Dark Mode </label>
              <sui-checkbox toggle  v-model="light" label="" />
            </sui-form-field>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="four wide column">
          <div class="ui card">
            <div class="top bar lime-blue"></div>
            @nathanf
            <h1>1987</h1>
            Followers
            12 Today
          </div>
        </div>
        <div class="four wide column">
          <div class="ui card"> 
            <div class="top bar lime-blue"></div>
            @nathanf
            <h1>1044</h1>
            Followers
            99 Today
          </div>
        </div>
        <div class="four wide column">
          <div class="ui card">
            <div class="top bar lime-blue"></div>
            @realnathanf
            <h1>11k</h1>
            Followers
            1099 Today
          </div>
        </div>
        <div class="four wide column">
          <div class="ui card">
            <div class="top bar lime-blue"></div>
            Nathan F.
            <h1>8239</h1>
            Subscribers
            144 Today
          </div>
        </div>
    </div>
      Overview - Today

      Page Views
      87
      3%

      Likes
      52
      2%

      Likes
      5462
      2257%

      Profile Views
      52k
      1375%

      Retweets
      117
      303%

      Likes
      507
      553%

      Likes
      107
      19%

      Total Views
      1407
      12%    
    </div>
    <img src="../assets/design/desktop-design-light.jpg" width="100%" />
      
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      light: true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
