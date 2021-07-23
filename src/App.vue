<template>
  <div id="app">
    <canvas id="mainCanvas" class="main"></canvas>
  </div>
</template>


<script>
import * as THREE from "three";

function init() {
  // renderer
  var renderer = new THREE.WebGLRenderer({
    canvas: document.getElementById("mainCanvas"),
  });
  renderer.setClearColor(0x000000); // black

  // scene
  var scene = new THREE.Scene();

  // camera
  var camera = new THREE.PerspectiveCamera(45, 4 / 3, 1, 1000);
  camera.position.set(0, 0, 5);
  scene.add(camera);

  // a cube in the scene
  var cube = new THREE.Mesh(
    new THREE.CubeGeometry(1, 2, 3),
    new THREE.MeshBasicMaterial({
      color: 0xff0000,
    })
  );
  scene.add(cube);

  // render
  renderer.render(scene, camera);
}

export default {
  mounted() {
    init();
  },
};
</script>


<style lang="less">
.main {
  width: 400px;
  height: 300px;
}
</style>
