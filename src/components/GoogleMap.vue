<template>
  <div id="google-map"></div>
</template>
<script>
import { Loader } from '@googlemaps/js-api-loader';
export default {
  mounted: function () {
     // const wgs84togcj02 = coordtransform.wgs84togcj02(116.49432212686906, 39.80330583467197);
    const loader = new Loader({
      apiKey: 'AIzaSyDIJq4nY4cKJogPvuBsnfb_V_Ov5MgLJQQ', // 个人申请key 按次计费
      version: 'weekly',
      libraries: ['places', 'drawing'],
    });
    // google map配置项
    const mapOptions = {
      center: { lat: 39.79334259095674, lng: 116.51912734023836 },
      zoom: 18,
      mapTypeControlOptions: {
        // style: google.maps.MapTypeControlStyle.DROPDOWN_MENU,
        mapTypeIds: ['roadmap', 'satellite'],
      },
      // mapTypeId: 'coordinate',
      disableDefaultUI: true, // 禁用按钮
      zoomControl: true,
    };
    // Promise
    loader
      .load()
      .then(() => {
        const map = new window.google.maps.Map(document.getElementById('google-map'), mapOptions);
      })
      .catch((e) => {
        // do something
      });
  },
}
</script>
<style lang="scss" scoped>
#google-map {
  height: 100%;
  width: 100%;
}
</style>
