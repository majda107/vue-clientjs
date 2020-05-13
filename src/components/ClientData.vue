<template>
  <div class="data" v-if="client != null">
    <div class="data-mobile" v-if="client.isMobile()">
        <h2>It's mobile device!</h2>
      <div class="data-mobile-android" v-if="client.isMobileAndroid()">
        <img src="../assets/android.svg" />
        <span>Eyyy it's android!</span>
      </div>
      <div class="data-mobile-ios" v-if="client.isMobileIOS()">
        <img src="../assets/ios.svg" />
        <span>Oof it's iOS!</span>
      </div>
    </div>
    <div class="data-desktop" v-else>
      <h2>Desktop it is!</h2>
      <img src="../assets/desktop.svg" />
      <span class="data-desktop-java" v-if="client.isJava()">Yikes and it has some Java...</span>
      <span class="data-desktop-nojava" v-else>Luckily without Java...</span>
    </div>

    <div class="data-useragent">
      <h2>User agent:</h2>
      <span class="data-useragent-type">{{ client.getUserAgent() }}</span>
    </div>

    <div class="data-browser">
      <h2>Browser:</h2>
      <span class="data-browser-type">Type: {{ client.getBrowser() }}</span>
      <span class="data-browser-version">Version: {{ client.getBrowserVersion() }}</span>
      <span class="data-browser-major">Major version: {{ client.getBrowserMajorVersion() }}</span>
      <span class="data-browser-engine">{{ client.getEngineVersion() }}</span>
    </div>

    <div class="data-os">
      <h2>Operating system:</h2>
      <span class="data-os-type">Your OS: {{ client.getOS() }}</span>
      <span class="data-os-version">Version: {{ client.getOSVersion() }}</span>
    </div>

    <div class="data-hardware">
      <h2>Hardware:</h2>
      <span class="data-hardware-cpu">CPU: {{ client.getCPU() }}</span>
      <span class="data-hardware-screen">Screen: {{ client.getScreenPrint() }}</span>
    </div>

    <div class="data-region">
      <h2>Region:</h2>
      <span class="data-region-langauge">{{ client.getLanguage() }}</span>
    </div>

    <div class="data-fingerprint">
      <h2>Fingerprint data:</h2>
      <span class="data-fingerprint">{{ client.getFingerprint() }}</span>
      <!-- <img v-bind:src="this.client.getCanvasPrint()" /> -->
    </div>

    <span class="data-fingerprint">Created by Marián Trpkoš | <a href="https://majdatrpkos.cz/">www.majdatrpkos.cz</a></span>
  </div>
</template>

<script>
import ClientJSService from "../services/ClientJSService";

export default {
  name: "ClientData",
  props: {},
  data: function() {
    return {
      client: null
    };
  },
  created: function() {
    this.client = ClientJSService.getClient();

    console.log();
  }
};
</script>

<style lang="sass" scoped>
div
    display: grid
    grid-auto-flow: row
    justify-content: center
    justify-items: center
    row-gap: 6px

.data
    background-color: rgba(10, 10, 10, 0.9)
    
    z-index: 1000
    row-gap: 32px

    -webkit-box-shadow: 10px 10px 35px -6px rgba(0,0,0,0.74)
    -moz-box-shadow: 10px 10px 35px -6px rgba(0,0,0,0.74)
    box-shadow: 10px 10px 35px -6px rgba(0,0,0,0.74)

    padding: 40px
    // padding-top: 48px
    // padding-bottom: 48px
    max-width: 700px
    border-radius: 16px

    &-desktop
        img
            width: 100px
            filter: invert(1)
            padding: 10px

        h2
            font-size: 1.4rem


    &-mobile
        &-android, &-ios
            img
                width: 86px
                filter: invert(1)
                padding: 10px

    &-fingerprint
        img
            width: 200px

span
    font-weight: 500
    opacity: 0.5

h2
    font-size: 1.2rem
</style>