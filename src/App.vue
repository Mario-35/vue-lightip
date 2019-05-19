<template>
  <div id="app">
    <section class="demo">
        <div class="demo__inner">
            <ul class="nav">
              <li class="nav__item">
                <Lightip class="nav__link outline" size="150" fontSize="9" position="top-left" label="Its me. I am a leftist. Get it?">
                  <a>Essai</a>
                  </Lightip>
              </li>
              <li class="nav__item">
                <Lightip class="nav__link outline" label="I continue in single line unless you specify a size" position="top">
                  Top
                </Lightip>
              </li>
              <li class="nav__item">
                <Lightip class="nav__link outline" label="Emoji? No problem 😎" position="top-right">
                  Top Right
                </Lightip>
              </li>
            </ul>
  
            <ul class="nav">
              <li class="nav__item">
                <Lightip class="nav__link outline" color="#f10000" borderColor="rgb(229, 255, 0)" backgroundColor="rgba(175, 187, 70, 0.575)" 
                label="I am a large lightip.  with color='#f10000' borderColor='rgb(229, 255, 0)'' backgroundColor='rgba(175, 187, 70, 0.575)'" position="left" size="large">
                  Left
                </Lightip>
              </li>
              <li class="nav__item">
                <span class="demo__center">Vue-Lightip</span>
              </li>
              <li class="nav__item">
                <Lightip class="nav__link outline" label="I am a medium size lightip. Use me for slightly longer messages" position="right" size="medium">
                  Right
                </Lightip>
              </li>
            </ul>
  
            <ul class="nav">
              <li class="nav__item">
                <Lightip class="nav__link outline" label="I am a medium sized lightip to the bottom left" position="bottom-left" size="medium">
                  Bottom Left
                </Lightip>
              </li>
              <li class="nav__item">
                <Lightip class="nav__link outline" label="I am a small message" position="bottom" size="small">
                  Bottom
                </Lightip>
              </li>
              <li class="nav__item">
                <Lightip class="nav__link outline" label="Look, its me at the bottom right" position="bottom-right">
                  Bottom Right
                </Lightip>
              </li>
            </ul>
  
        </div>
      </section>


  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Lightip from "./components/lightip/Lightip.vue";
export default Vue.extend({
  name: "app",
  components: {
    Lightip,
  },
});
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
}
body {
  border-top: solid 5px #36c;
}
.outline {
  background-color: #fff;
  border: dashed 1px #36c;
  padding: 14px 30px;
  min-width: 120px;
  display: inline-block;
  text-align: center;
  line-height: 1.5;
}
.nav {
  list-style-type: none;
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
}
.nav__item {
  flex: 1;
  position: relative;
  margin: 10px;
}
.nav__link {
  text-decoration: none;
  color: #36c;
}
.demo {
  margin: 80px 0;
  background-color: #eff3fd;
  width: 100%;
  border: solid 1px #d3dcf2;
  border-radius: 3px;
  padding: 60px 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
.demo__inner {
  display: inline-block;
  margin: auto;
  text-align: center;
}
.demo__center {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  font-size: 30px;
}
</style>