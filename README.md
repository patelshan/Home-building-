<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>3D House Builder</title>
  <style>
    html, body {
      margin: 0;
      overflow: hidden;
      touch-action: none;
    }
    #ui {
      position: absolute;
      top: 10px;
      left: 10px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      z-index: 2;
    }
    button {
      padding: 10px;
      font-size: 16px;
      border: none;
      background: #4CAF50;
      color: white;
      border-radius: 4px;
    }
  </style>
</head>
<body>
  <div id="ui">
    <button onclick="addWall()">Add Wall</button>
    <button onclick="addRoof()">Add Roof</button>
    <button onclick="addWindow()">Add Window</button>
  </div>
  <script src="https://cdn.jsdelivr.net/npm/three@0.155.0/build/three.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.155.0/examples/js/controls/OrbitControls.js"></script>
  <script>
    const scene = new THREE.Scene();
    scene.background = new THREE.Color('#87CEEB');const camera = new THREE.PerspectiveCamera(75, window.innerWidth/window.innerHeight, 0.1, 1000);
camera.position.set(5, 5, 10);

const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

const controls = new THREE.OrbitControls(camera, renderer.domElement);
controls.enablePan = false;
controls.enableDamping = true;

const grid = new THREE.GridHelper(20, 20);
scene.add(grid);

const ambient = new THREE.AmbientLight(0xffffff, 0.8);
scene.add(

