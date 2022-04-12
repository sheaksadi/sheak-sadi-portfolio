<template>
    <canvas id="bg"></canvas>
</template>

<script>
import * as THREE from "three";


export default {
  name: 'background',
  mounted() {
    const scene = new THREE.Scene()
    const camera = new THREE.PerspectiveCamera(75,window.innerWidth/window.innerHeight,10,1000)
    const renderer = new THREE.WebGLRenderer({
      antialias: true ,
      canvas: document.querySelector("#bg")
    })

    renderer.setPixelRatio(window.devicePixelRatio)
    renderer.setSize(window.innerWidth, window.innerHeight)
    camera.position.setZ(0);
    const ambientLight = new THREE.AmbientLight(0xffffff);
    scene.add(ambientLight);

    function addStar() {
      const geometry = new THREE.SphereGeometry(.05,25,25)
      const material = new THREE.MeshBasicMaterial(0xffffff)
      const star = new THREE.Mesh(geometry, material)

      const [x, y, z] = Array(3).fill().map(() => THREE.MathUtils.randFloatSpread(200));

      star.position.set(x, y, z);
      scene.add(star);
    }
    Array(2000).fill().forEach(addStar);

    // scene.background = new THREE.TextureLoader().load("space.jpg");


    window.addEventListener(
      'resize',

        () => {
          const width = window.innerWidth;
          const height = window.innerHeight;
          camera.aspect = width / height;
          camera.updateProjectionMatrix();
          renderer.setSize(width, height);
        },)



    window.onmousemove = function(e){
      // let x = camera.rotateX
      // let y = camera.rotateY
      //
      //
      // console.log(e.movementX)
      // if (e.screenX < window.innerWidth * .5){
      //   camera.rotateX( camera.rotateX()+1);
      // }
      // if (e.screenX > window.innerWidth * .5){
      //   camera.rotateX( camera.rotateX()-1);
      // }
      camera.rotateX( e.movementY * .002);
      camera.rotateY(e.movementX * .002) ;

    };
    function animate() {
      requestAnimationFrame(animate);

      renderer.render(scene, camera);
    }

    animate();


  }
}
</script>
<style>
canvas {
  position: fixed;
  top: 0;
  left: 0;
}
</style>
