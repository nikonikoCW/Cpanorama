<template>
  <div class="hello">
    <div id="panorama"></div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  mounted(){
    debugger
    pannellum.viewer('panorama', {
        "type":"multires",
        "autoLoad": true, 
        "autoRotate":"3",
        "autoRotateInactivityDelay":'10000',
        "multiRes": {
            "path": "/%l/%s%y_%x",
            "fallbackPath": "/fallback/%s",
            "basePath":'../../static/pano/output',
            "extension": "jpg",
            "tileResolution": 512,
            "maxLevel": 4,
            "cubeResolution": 2544
        }
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#panorama,.hello {
            width: 100%;
            height: 100%;
        }
</style>
