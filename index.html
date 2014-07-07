<html>
<head>
    <title>My first Three.js app</title>
    <style>canvas { width: 100%; height: 100% }</style>
</head>
<body>
<script src="js/three.min.js"></script>
<script src="js/threex.keyboardstate.js"></script>
<script>
var scene = new THREE.Scene();
scene.fog = new THREE.Fog( 0xffffff, 1000, 10000 );
var fov = 75;
var aspect = window.innerWidth/window.innerHeight;
var near = 0.1;
var far = 1000;

var playerAngle = 0;
var velocity = 0;
var acceleration = 0.01;

var camera = new THREE.PerspectiveCamera(fov, aspect, near, far);


// renderer
var renderer = new THREE.WebGLRenderer({ antialias: true });
renderer.setSize(window.innerWidth, window.innerHeight);
renderer.setClearColor( 0xf0f0f0 );
renderer.gammaInput = true;
renderer.gammaOutput = true;
renderer.shadowMapEnabled = true;
renderer.shadowMapSoft = true;
renderer.shadowMapType = THREE.PCFSoftShadowMap;

document.body.appendChild(renderer.domElement);

// player
var geometry = new THREE.BoxGeometry(1,1,1);

var texture = THREE.ImageUtils.loadTexture( "textures/box.jpg" );
var material = new THREE.MeshPhongMaterial( { color: 0xffffff, map: texture} );

texture.wrapS = texture.wrapT = THREE.RepeatWrapping;
texture.repeat.set( 1, 1);

var cube = new THREE.Mesh(geometry, material);
cube.position.y = 0.8;
cube.castShadow = true;
cube.receiveShadow = true;
scene.add(cube);
cube.add(camera);

camera.position.x = cube.position.x;
camera.position.y = 2;
camera.position.z = cube.position.z-3;

camera.lookAt( cube.position );

// object
var texture = THREE.ImageUtils.loadTexture( "textures/rock.jpg" );
var material = new THREE.MeshLambertMaterial( { color: 0xffffff, map: texture} );
texture.wrapS = texture.wrapT = THREE.RepeatWrapping;
texture.repeat.set( 1,1 );
var obj = new THREE.Mesh(new THREE.SphereGeometry(1, 20, 20), material);

obj.position.x = 5;
obj.position.y = 1;
obj.position.z = -5;

obj.castShadow = true;
obj.receiveShadow = true;

scene.add(obj);


// sky
var material = new THREE.MeshBasicMaterial( {color: 0x0088cc, wireframe: false} );
var sphere = new THREE.Mesh(new THREE.SphereGeometry(1000, 10, 10), material);
sphere.material.side = THREE.BackSide;
scene.add(sphere);




// ground

var geometry = new THREE.PlaneGeometry( 400, 400 );
var texture = THREE.ImageUtils.loadTexture( "textures/grass.jpg" );
var material = new THREE.MeshLambertMaterial( { color: 0xffffff, map: texture} );

texture.wrapS = texture.wrapT = THREE.RepeatWrapping;
texture.repeat.set( 200, 200 );

var ground = new THREE.Mesh(geometry, material);
ground.position.x = 0;
ground.position.y = 0;
ground.position.z = 0;
ground.applyMatrix( new THREE.Matrix4().makeRotationX( - Math.PI / 2 ) );
//ground.castShadow = true;
ground.receiveShadow = true;
scene.add( ground );

// LIGHTS
var hemiLight = new THREE.HemisphereLight( 0xffffff, 0xffffff,1 );
hemiLight.color.setHSL( 0.6, 1, 0.6 );
//hemiLight.groundColor.setHSL( 0.095, 1, 0.75 ); // setar depois a cor real.
hemiLight.position.set( 0, 500, 0 );
scene.add( hemiLight );

//
var dirLight = new THREE.DirectionalLight( 0xffffff, 1 );
dirLight.color.setHSL( 0.1, 1, 0.95 );
dirLight.position.set( -1, 1.75, 1 );
dirLight.position.multiplyScalar( 50 );
scene.add( dirLight );

dirLight.castShadow = true;
dirLight.shadowMapWidth = 2048;
dirLight.shadowMapHeight = 2048;


var d = 50;

dirLight.shadowCameraLeft = -d;
dirLight.shadowCameraRight = d;
dirLight.shadowCameraTop = d;
dirLight.shadowCameraBottom = -d;

dirLight.shadowCameraFar = 3500;
dirLight.shadowBias = -0.0001;
dirLight.shadowDarkness = 0.35;
//dirLight.shadowCameraVisible = true;


//collision
var raycaster = new THREE.Raycaster();
var rays = [
    new THREE.Vector3(0, 0, 1),
    new THREE.Vector3(1, 0, 1),
    new THREE.Vector3(1, 0, 0),
    new THREE.Vector3(1, 0, -1),
    new THREE.Vector3(0, 0, -1),
    new THREE.Vector3(-1, 0, -1),
    new THREE.Vector3(-1, 0, 0),
    new THREE.Vector3(-1, 0, 1)
];

var is_colliding = function(position, obstacles) {

    for (i = 0; i < rays.length; i += 1) {
        raycaster.set(position, rays[i]);
        collisions = raycaster.intersectObjects(obstacles);
        if (collisions.length > 0 && collisions[0].distance < 0.5) {
            return true;
        }
    }
    return false;
}








// loading model
var loader = new THREE.JSONLoader(); // init the loader util

// init loading
loader.load('models/tree/tree.js', function (geometry, material) {
    // create a mesh with models geometry and material
    var materials = new THREE.MeshFaceMaterial(material);
    materials.wireframe = true;
    var mesh = new THREE.Mesh(
            geometry,
            materials
    );



    mesh.scale.set( 0.001, 0.001, 0.001 );
    mesh.position.x = 0;
    mesh.position.y = 0;
    mesh.position.z = 0;
    mesh.doubleSided = true;
    mesh.castShadow = true;
    mesh.receiveShadow = true;
    scene.add(mesh);
});

// loading inn
loader.load('models/inn/inn.js', function (geometry, material) {
    // create a new material
    var materials = new THREE.MeshFaceMaterial(material);
    materials.wireframe = true;
    var mesh = new THREE.Mesh(
            geometry,
            materials
    );



    mesh.scale.set( 0.001, 0.001, 0.001 );
    mesh.position.x = 10;
    mesh.position.y = 0;
    mesh.position.z = 10;
    mesh.doubleSided = true;
    mesh.castShadow = true;
    mesh.receiveShadow = true;
    scene.add(mesh);
});

var render = function () {

    var accelerating = false;

    if (keyboard.pressed("left")) {
        playerAngle += 0.05;
    }
    else if (keyboard.pressed("right")) {
        playerAngle -= 0.05;
    }

    if (keyboard.pressed("up")) {
        accelerating = true;
        velocity += acceleration;

        // check collision
        var new_position = new THREE.Vector3(
                        cube.position.x + (velocity * Math.sin(playerAngle)),
                        cube.position.y,
                cube.position.z + (velocity * Math.cos(playerAngle)));
        if (!is_colliding(new_position, [obj])) {
            cube.position.x = new_position.x;
            cube.position.y = new_position.y;
            cube.position.z = new_position.z;
        }
    }

    // velocity limit
    if (velocity>0.1) {
        velocity = 0.1;
    }

    if (!accelerating && velocity < 0) {
        velocity -= acceleration;
    }

    if (velocity<0) {
        velocity = 0;
    }

    cube.rotation.y = playerAngle;
    requestAnimationFrame(render);
    renderer.render(scene, camera);
};
var keyboard    = new THREEx.KeyboardState();
render();
</script>
</body>
</html>