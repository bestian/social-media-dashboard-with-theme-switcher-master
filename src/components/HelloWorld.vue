<template>
  <div class="hello" :class = "light ? 'light' : 'dark'">
    <div class="filler"></div>
    <div class="ui stackable four column grid container">
      <div class = "row">
        <div class="twelve wide column">
          <h1 class="ui header">
            Social Media Dashboard
            <div class="sub header">
              Total Followers: 23,004
            </div>
          </h1>
        </div>
        <div class="four wide column right">
          <hr class="thin-only bgdk" />
          <div class="inline field">
            <sui-form-field>
              <label class="dk">Dark Mode </label>
              <span class="xs-float-right">
                <sui-checkbox toggle slider v-model="light" label="" />
              </span>
            </sui-form-field>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="four wide column">
          <div class="card">
            <div class="top bar facebook"></div>
            <span class="gray">
              <img src="../assets/icon-facebook.svg"/>
              <span class="m1">@nathanf</span></span>
            <h1 class="gigi">1987</h1>
            <span class="gray sp">{{ 'Followers' | toUpper }}</span>
            <div class="green">
              <img src="../assets/icon-up.svg"/>12 Today
            </div>
          </div>
        </div>
        <div class="four wide column">
          <div class="card"> 
            <div class="top bar twitter"></div>
              <span class="gray">
                <img src="../assets/icon-twitter.svg"/>
                <span class="m1">@nathanf</span>
              </span>
            <h1 class="gigi">1044</h1>
            <span class="gray sp">{{ 'Followers' | toUpper }}</span>
            <div class="green">
              <img src="../assets/icon-up.svg"/>99 Today
            </div>
          </div>
        </div>
        <div class="four wide column">
          <div class="card">
            <div class="top bar instagram"></div>
            <span class="gray">@realnathanf</span>
            <h1 class="gigi">11k</h1>
            <span class="gray sp">{{ 'Followers' | toUpper }}</span>
            <div class="green">
              <img src="../assets/icon-up.svg"/>1099 Today
            </div>
          </div>
        </div>
        <div class="four wide column">
          <div class="card">
            <div class="top bar youtube"></div>
            <span class="gray">Nathan F.</span>
            <h1 class="gigi">8239</h1>
            <span class="gray sp">{{ 'Subscribers' | toUpper }}</span>
            <div class="red">
              <img src="../assets/icon-down.svg"/>144 Today
            </div>
          </div>
        </div>
      </div>
      <div class="ui row">
        <div class="ui header m1">
          Overview - Today
        </div>
      </div>
      <div class="ui row">
        <div class="four wide column" v-for = "l in list" :key = "l[1]">
          <div class="card">
            <div class="top left">
              {{l[0]}}
            </div>
            <div class="top right">
              <img :src="'/icon-'+l[3]+'.svg'">
            </div>
            <div class="bottom left big">
              {{l[1]}}
            </div>
            <div class="bottom right" :class="l[2] > 0 ? 'green' : 'red'">
              <img v-if="l[2] > 0" src="../assets/icon-up.svg"/>
              <img v-else src="../assets/icon-down.svg"/>
              {{Math.abs(l[2])}}%
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  filters: {
    toUpper: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.toUpperCase()
    }
  },
  data () {
    return {
      light: false,
      list: [
        ['Page Views', '87', 3, 'facebook'],
        ['Likes', '52', -2, 'facebook'],
        ['Likes', '5462', 2257, 'instagram'],
        ['Profile Views', '52k', 1375, 'instagram'],
        ['Retweets', '117', 303, 'twitter'],
        ['Likes', '507', 553, 'twitter'],
        ['Likes', '107', -19, 'youtube'],
        ['Total Views', '1407', -12, 'youtube']
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

@import '../variables.scss';

.hello {
  &.dark {
    background-color: $VDBG;
    color: white;
    .ui.header {
      color: white;
      .sub.header {
        color: $DG;
      }
    }
    .dk {
      color: $DG;
    }
    .bgdk {
      border-color: $DG;
    }
    .column {
      border: none;
    }
    .card {
      background-color: $DCBG;
      &:active {
        background-color: $ACDKBG;
      }
      .top.left {
        color: $DG;
      }
    }
  }
}

.dk {
  color: gray;
}

.right {
  text-align: right;
}

@media screen and (max-width: 420px) {
  .right {
    text-align: left;
  }
  .xs-float-right {
    float: right;
  }
}

@media screen and (min-width: 421px) {
  .thin-only {
    display: none;
  }
}

.green {
  color: green;
  font-weight: bold;
  margin-top: 10px;
}

.red {
  color: red;
  font-weight: bold;
  margin-top: 10px;
}

.gray {
  color: gray;
  margin: 0 auto;
  display: flex;
  align-item: center;
  &.sp {
    letter-spacing: 3px;
  }
}

.m1 {
  margin-left: 11px;
}

.card {
  &:active {
    background-color: $ACBG;
  }
  cursor: pointer;
  width: 100%;
  max-width: 100%;
  position: relative;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
  -ms-flex-direction: column;
  flex-direction: column;
  border: none;
  border-radius: .28571429rem;
  text-align: center;
  padding: 30px 0;
  margin: 1em 0;
  margin-bottom: 15px;
  background-color: #f2f2f2;
  min-height: 100px;
  font-weight: bold;
  .top {
    position: absolute;
    top: 15px;
  }
  .bottom {
    position: absolute;
    bottom: 15px;
  }
  .left {
    left: 15px;
  }
  .right {
    right: 5px;
  }
  .big {
    font-size: 30px;
    font-weight: bold;
  }
  .top.bar {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 4px;
    border-radius: .28571429rem .28571429rem 0 0;
    &.lime-blue {
      background-color: $Lime-Green; 
    }
    &.facebook {
      background: $Facebook;
    }
    &.twitter {
      background-color: $Twitter;
    }
    &.instagram {
      background: $Instagram;
    }
    &.youtube {
      background: $YouTube;
    }
  }
}

.gigi {
  font-weight: bold;
  font-size: 52px;
  margin: 0 auto;
}

</style>
