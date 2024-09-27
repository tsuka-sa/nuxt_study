<script setup lang="ts">
    import * as THREE from 'three';
    // シーンの作成
    const scene = new THREE.Scene();

    // カメラの作成
    const camera = new THREE.PerspectiveCamera(80, window.innerWidth / window.innerHeight, 0.1, 1000);
    camera.position.z = 10;

    // レンダラーの作成
    const renderer = new THREE.WebGLRenderer();
    renderer.setSize(window.innerWidth, window.innerHeight);
    document.body.appendChild(renderer.domElement);

    // 立方体のジオメトリを作成（ビルのような形状）
    const geometry = new THREE.BoxGeometry(1, 5, 1);  // ビルの幅、高さ、奥行き

    // 線のマテリアルを作成
    const material = new THREE.LineBasicMaterial({ color: 0x00ff00 });

    // ジオメトリを線に変換
    const edges = new THREE.EdgesGeometry(geometry);
    const line = new THREE.LineSegments(edges, material);



    const positions = [
      { x: -5,  y: 0, z: 4 },
      { x: -3,  y: 0, z: 4 },
      { x: 0,  y: 0, z: 4 },
      { x: 3,  y: 0, z: 4 },
      { x: 5,  y: 0, z: 4 }
    ];

    positions.forEach((pos) => {
      const building = line.clone();  // クローンを作成
      building.position.set(pos.x, pos.y, pos.z);  // 座標を設定
      scene.add(building);  // シーンに追加
    });

    // アニメーション関数
    function animate() {
      requestAnimationFrame(animate);

      renderer.render(scene, camera);
    }

    animate();

    // リサイズ処理
    window.addEventListener('resize', () => {
      renderer.setSize(window.innerWidth, window.innerHeight);
      camera.aspect = window.innerWidth / window.innerHeight;
      camera.updateProjectionMatrix();
    });

</script>
<template>
     <div>
        <Head>
            <Title>{{ title }}</Title>
        </Head>
    </div>
</template>