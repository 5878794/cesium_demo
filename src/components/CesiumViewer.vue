<script>
import * as Cesium from "cesium";
import "cesium/Source/Widgets/widgets.css";

const viewer = new Cesium.Viewer("app",{
  baseLayerPicker:false, //图层选择
  timeline:false,  //时间线
  navigationHelpButton:false,  //帮助按钮
  geocoder:false, //搜索
  scene3DOnly:true, //只显示3d
  homeButton:false,   //主页按钮
  fullscreenButton:false, //全屏按钮
  animation:false
});
//去logo等信息
viewer._cesiumWidget._creditContainer.style.display = "none";


// viewer.scene.debugShowFramesPerSecond = true; //刷新率

// viewer.camera.flyTo({
//   destination: Cesium.Cartesian3.fromDegrees(-104.9965, 39.74248, 4000)
// });
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#cesium-container {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
}
</style>
