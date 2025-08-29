<!-- Inclure Three.js et un canvas minimal -->
<script src="https://unpkg.com/three@0.152.2/build/three.min.js"></script>
<canvas id="scene"></canvas>
<script>
const scene = new THREE.Scene();
const camera = new THREE.PerspectiveCamera(75, innerWidth/innerHeight, 0.1, 1000);
const renderer = new THREE.WebGLRenderer({canvas: document.getElementById('scene'), antialias: true});
renderer.setSize(innerWidth, innerHeight);
const geometry = new THREE.TorusKnotGeometry( 10, 3, 100, 16 );
const material = new THREE.MeshNormalMaterial();
const torusKnot = new THREE.Mesh( geometry, material );
scene.add( torusKnot );
camera.position.z = 50;
function animate(){ requestAnimationFrame(animate); torusKnot.rotation.x += 0.01; torusKnot.rotation.y += 0.02; renderer.render(scene, camera); }
animate();
</script>
