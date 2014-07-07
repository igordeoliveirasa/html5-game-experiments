<html>
<head>
    <title></title>
    <style>canvas { width: 100%; height: 100% }</style>
</head>
<body>
<script src="js/three.min.js"></script>
<script src="js/threex.keyboardstate.js"></script>
<script>

// renderer
var renderer = new THREE.WebGLRenderer({ antialias: true });
renderer.setSize(window.innerWidth, window.innerHeight);
renderer.setClearColor( 0xf0f0f0 );
renderer.gammaInput = true;
renderer.gammaOutput = true;
renderer.shadowMapEnabled = true;
renderer.shadowMapSoft = true;
renderer.shadowMapType = THREE.PCFShadowMap;//THREE.PCFSoftShadowMap;

document.body.appendChild(renderer.domElement);

var scene = new THREE.Scene();
scene.fog = new THREE.Fog( 0xffffff, 1000, 10000 );

var fov = 75;
var aspect = window.innerWidth/window.innerHeight;
var near = 0.1;
var far = 1500;

var playerAngle = 0;
var velocity = 0;
var acceleration = 0.01;

var camera = new THREE.PerspectiveCamera(fov, aspect, near, far);

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
ground.receiveShadow = true;
scene.add( ground );


// player
var geometry = new THREE.BoxGeometry(1,1,1);

var texture = THREE.ImageUtils.loadTexture( "textures/box.jpg" );
var material = new THREE.MeshPhongMaterial( { color: 0xffffff, map: texture} );

texture.wrapS = texture.wrapT = THREE.RepeatWrapping;
texture.repeat.set( 1, 1);

var cube = new THREE.Mesh(geometry, material);
cube.position.x = 38;
cube.position.y = 0.6;
cube.position.z = -9;
cube.castShadow = true;
cube.receiveShadow = true;
scene.add(cube);
cube.add(camera);

camera.position.y = 3;
camera.position.z = 5;
camera.lookAt(new THREE.Vector3(0,0,0))

// object
var texture = THREE.ImageUtils.loadTexture( "textures/rock.jpg" );
var material = new THREE.MeshLambertMaterial( { color: 0xffffff, map: texture} );
texture.wrapS = texture.wrapT = THREE.RepeatWrapping;
texture.repeat.set( 1,1 );
var obj = new THREE.Mesh(new THREE.SphereGeometry(1, 20, 20), material);

obj.position.x = 50;
obj.position.y = 1;
obj.position.z = -30;

obj.castShadow = true;
obj.receiveShadow = true;

scene.add(obj);

// sky
var material = new THREE.MeshBasicMaterial( {color: 0x0088cc, wireframe: false} );
var sphere = new THREE.Mesh(new THREE.SphereGeometry(1000, 10, 10), material);
sphere.material.side = THREE.BackSide;
scene.add(sphere);


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
        if (collisions.length > 0 && collisions[0].distance < 1) {
            return true;
        }
    }
    return false;
}

function buildAxis( src, dst, colorHex, dashed ) {
    var geom = new THREE.Geometry(),
            mat;

    if(dashed) {
        mat = new THREE.LineDashedMaterial({ linewidth: 3, color: colorHex, dashSize: 3, gapSize: 3 });
    } else {
        mat = new THREE.LineBasicMaterial({ linewidth: 3, color: colorHex });
    }

    geom.vertices.push( src.clone() );
    geom.vertices.push( dst.clone() );
    geom.computeLineDistances(); // This one is SUPER important, otherwise dashed lines will appear as simple plain lines

    var axis = new THREE.Line( geom, mat, THREE.LinePieces );

    return axis;

}


function buildAxes( length ) {
    var axes = new THREE.Object3D();

    axes.add( buildAxis( new THREE.Vector3( 0, 0, 0 ), new THREE.Vector3( length, 0, 0 ), 0xFF0000, false ) ); // +X
    axes.add( buildAxis( new THREE.Vector3( 0, 0, 0 ), new THREE.Vector3( -length, 0, 0 ), 0xFF0000, true) ); // -X
    axes.add( buildAxis( new THREE.Vector3( 0, 0, 0 ), new THREE.Vector3( 0, length, 0 ), 0x00FF00, false ) ); // +Y
    axes.add( buildAxis( new THREE.Vector3( 0, 0, 0 ), new THREE.Vector3( 0, -length, 0 ), 0x00FF00, true ) ); // -Y
    axes.add( buildAxis( new THREE.Vector3( 0, 0, 0 ), new THREE.Vector3( 0, 0, length ), 0x0000FF, false ) ); // +Z
    axes.add( buildAxis( new THREE.Vector3( 0, 0, 0 ), new THREE.Vector3( 0, 0, -length ), 0x0000FF, true ) ); // -Z

    return axes;

}

//scene.add(buildAxes(1000));



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
    mesh.position.x = 30;
    mesh.position.y = 0;
    mesh.position.z = -30;
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
    mesh.position.x = 40;
    mesh.position.y = 0;
    mesh.position.z = -40;

    //mesh.rotation.y = 180;

    mesh.doubleSided = true;
    mesh.castShadow = true;
    mesh.receiveShadow = true;
    scene.add(mesh);
});

var new_position = new THREE.Vector3(0,0,0);
var accelerating = false;

var animate = function () {

    requestAnimationFrame(animate);

    accelerating = false;


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
        new_position.x = cube.position.x - (velocity * Math.sin(playerAngle));
        new_position.y = cube.position.y;
        new_position.z = cube.position.z - (velocity * Math.cos(playerAngle));

        if (!is_colliding(new_position, [obj])) {
            cube.position.x = new_position.x;
            cube.position.z = new_position.z;
        }
    }

    if (keyboard.pressed("space")) {
        alert(cube.position.x + " - " + cube.position.z);
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
    renderer.render(scene, camera);
};

var keyboard    = new THREEx.KeyboardState();
animate();

// AUDIO

var audio = document.createElement( 'audio' );
var source = document.createElement( 'source' );
//source.src = 'sounds/musics/04. Midori - When the Swallows Return.mp3';
source.src = 'sounds/musics/06. Midori - The Rivers of Home.mp3';
audio.appendChild( source );
audio.load();
audio.play();

</script>
</body>
</html>