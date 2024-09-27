<script setup lang="ts">
    import * as THREE from 'three';
    const title = ref('My first three.js app')
    const scene = new THREE.Scene();
    scene.background = new THREE.Color( 0x404040 );
    const camera = new THREE.PerspectiveCamera( 100, window.innerWidth / window.innerHeight, 1, 1000 );
    camera.position.set( 0, 0, 100 );
    camera.lookAt( 0, 0, 0 );
    const renderer = new THREE.WebGLRenderer();
    renderer.setSize( window.innerWidth, window.innerHeight );
    document.body.appendChild( renderer.domElement );
    const material = new THREE.LineBasicMaterial( { color: 0x00ffff } );
    const points = [];
    points.push( new THREE.Vector3( - 10, 0, 0 ) );
    points.push( new THREE.Vector3( 0, 10, 0 ) );
    points.push( new THREE.Vector3( 10, 0, 0 ) );
    const geometry = new THREE.BufferGeometry().setFromPoints( points );

    const line = new THREE.Line( geometry, material );
    scene.add( line );

    camera.position.z = 5;

    function animate() {
        requestAnimationFrame( animate );
        renderer.render( scene, camera );
    }
    animate();

</script>
<template>
     <div>
        <Head>
            <Title>{{ title }}</Title>
        </Head>
    </div>
</template>