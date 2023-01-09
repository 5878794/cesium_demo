<script>
import * as Cesium from "cesium";
import "cesium/Source/Widgets/widgets.css";
import fj from '../../public/gltf/fj.gltf'

const viewer = new Cesium.Viewer("app",{
  baseLayerPicker:false, //图层选择
  timeline:false,  //时间线
  navigationHelpButton:false,  //帮助按钮
  geocoder:false, //搜索
  scene3DOnly:true, //只显示3d
  homeButton:false,   //主页按钮
  fullscreenButton:false, //全屏按钮
  animation:false,
});
//去logo等信息
viewer._cesiumWidget._creditContainer.style.display = "none";


const scene = viewer.scene;
const modelMatrix = Cesium.Transforms.eastNorthUpToFixedFrame(Cesium.Cartesian3.fromDegrees(-75.62898254394531, 40.02804946899414, 0.0));
const model = scene.primitives.add(Cesium.Model.fromGltf({
  url : fj,
  modelMatrix : modelMatrix,
  scale : 200.0
}));
viewer.trackedEntity = model;

//
// //添加3d模型
// const position = Cesium.Cartesian3.fromDegrees(
//   -123.222,
//   44.333,
//   5000
// )
// //弧度的航向分量。
// const heading = Cesium.Math.toRadians(0);
// //弧度的螺距分量。
// const pitch = 0;
// //滚动分量（以弧度为单位）
// const roll = 0;
// //HeadingPitchRoll旋转表示为航向，俯仰和滚动。围绕Z轴。节距是绕负y轴的旋转。滚动是关于正x轴。
// const hpr = new Cesium.HeadingPitchRoll(heading, pitch, roll);
// const orientation = Cesium.Transforms.headingPitchRollQuaternion(
//   position,
//   hpr
// );
//
// const entity = viewer.entities.add({
//   position: position,
//   orientation: orientation,
//   model: {
//     url: fj,
//     //不管缩放如何，模型的最小最小像素大小。
//     minimumPixelSize: 128,
//     //模型的最大比例尺大小。 minimumPixelSize的上限。
//     maximumScale: 20000,
//   },
// });
// // 获取或设置相机当前正在跟踪的Entity实例。
// viewer.trackedEntity = entity;




// viewer.scene.debugShowFramesPerSecond = true; //刷新率

viewer.camera.flyTo({
  destination: Cesium.Cartesian3.fromDegrees(-75.62898254394531, 40.02804946899414, 0.0)
});
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
