<template>
  <div class="card-storage demo-card-square mdl-card mdl-shadow--2dp">
    <div style="margin-bottom: -20px" class="mdl-card__title mdl-card--expand">
      <h2 class="mdl-card__title-text">{{ Object.keys(storage) }} <div style="margin-top: 5px; margin-left:10px;border-radius: 150%; height: 15px; width:15px; background:#42b983;"></div> </h2>
    </div>
    <div class="mdl-card__supporting-text">
      <p class="ip-text">192.178.2.1 </p>
      <hr>
      <p class="plots-text">
        Plots <strong>1323</strong>   / Disk space <strong>522TB</strong>
      </p>
    </div>
    <div class="mdl-card__actions mdl-card--border">
      <a class="mdl-button mdl-button--colored mdl-js-button mdl-js-ripple-effect">

      </a>
    </div>
  </div>
</template>
#5376
<script>
export default {
  name: "cardStorage",
  props: {
    storage: Object
  }
}
</script>

<style scoped>
.card-storage {
  border-radius: 15px;
}
.ip-text{
  font-size: 16px;
  color: #18d3ec;
  margin-top: -5px;
  margin-bottom: -10px;
}
.plots-text{
  font-size:16px;
  margin-top: 10px;
}
</style>