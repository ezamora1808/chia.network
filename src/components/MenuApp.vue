<template>
  <div class="mdl-layout mdl-js-layout mdl-layout--fixed-header
            mdl-layout--fixed-tabs">
    <header class="mdl-layout__header">
      <div class="mdl-layout__header-row">
        <!-- Title -->
        <span class="mdl-layout-title">{{ nameApp }}</span>
      </div>
      <!-- Tabs -->
      <div class="mdl-layout__tab-bar mdl-js-ripple-effect">
        <a href="#fixed-tab-1" class="mdl-layout__tab is-active">Storages</a>
        <a href="#fixed-tab-2" class="mdl-layout__tab">Tab 2</a>
        <a href="#fixed-tab-3" class="mdl-layout__tab">Tab 3</a>
      </div>
    </header>
    <div class="mdl-layout__drawer">
      <span class="mdl-layout-title">{{ nameApp }}</span>
      <nav class="mdl-navigation">
        <a class="mdl-navigation__link" href="">Link</a>
        <a class="mdl-navigation__link" href="">Link</a>
        <a class="mdl-navigation__link" href="">Link</a>
        <a class="mdl-navigation__link" href="">Link</a>
      </nav>
    </div>
    <main class="mdl-layout__content">
      <section class="mdl-layout__tab-panel is-active" id="fixed-tab-1">
        <div class="page-content">

          <div class="container">
            <br>
            <br>
            <h2 class="text-center titleModule"><img width="40"  src="../assets/database.png"> Storages</h2>
            <div class="row">
                <code>
                  {{ typeof $data }}
                </code>
            </div>
            <div class="row">
              <div class="col-3">
               <card-storage :storage="$data">

               </card-storage>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section class="mdl-layout__tab-panel" id="fixed-tab-2">
        <div class="page-content"><!-- Your content goes here --></div>
      </section>
      <section class="mdl-layout__tab-panel" id="fixed-tab-3">
        <div class="page-content"><!-- Your content goes here --></div>
      </section>
    </main>
  </div>
</template>

<script>
import cardStorage from "@/components/cardStorage";
import axios from "axios";
export default {
  name: "MenuApp",
  components: {
    cardStorage
  },
  props: {
    nameApp: String
  },
  data : function () {
    axios
        .get('https://api.coindesk.com/v1/bpi/currentprice.json')
        .then(response => (this.info = response))
  }
}
</script>

<style scoped>
.demo-layout-waterfall .mdl-layout__header-row .mdl-navigation__link:last-of-type  {
  padding-right: 0;
}
.titleModule {
  font-weight: lighter !important;
  color: #5f5f5f;
}
</style>