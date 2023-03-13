<script lang="ts">
    import * as Threlte from '@threlte/core';
    import * as Three from 'three';
    import * as Utils from 'three/src/math/MathUtils';
    import * as Extra from '@threlte/extras';
    import { HTML } from '@threlte/extras'
    import { Pane } from 'tweakpane';
    import { browser } from '$app/environment';
    import up from "../../assets/play_page/angle-up.png";
    import down from "../../assets/play_page/angle-down.png";
    import left from "../../assets/play_page/angle-left.png";
    import right from "../../assets/play_page/angle-right.png";

    type Ghost = keyof typeof ghost

    const gridHelper = new Three.GridHelper(20, 10);
    const axesHelper = new Three.AxesHelper(10);

    const sphere = {
		position: { x: 0, y: 8, z: 0 },
	}

    let ghost = {
		position: { x: 0, y: 1.9, z: 0 },
		scale: 0.4,
	}

    function setUpGhost() {
        ghost.scale = 2;
    }

    function handleUp() {
		const timeInSeconds = Date.now() / 300
		const offsetY = 6.5
		ghost.position.y = Math.sin(timeInSeconds) + offsetY
		requestAnimationFrame(handleUp)
	}

    function handleDown() {
		const timeInSeconds = Date.now() / 300
		const offsetZ = 10
		ghost.position.z = Math.sin(timeInSeconds) + offsetZ
		requestAnimationFrame(handleDown)
	}

    function handleRight() {
		const timeInSeconds = Date.now() / 300
		const offsetX = 10
		ghost.position.x = Math.sin(timeInSeconds) + offsetX
		requestAnimationFrame(handleRight)
	}

    function handleLeft() {
		const timeInSeconds = Date.now() / 300
		const offsetX = -10
		ghost.position.x = Math.sin(timeInSeconds) + offsetX
		requestAnimationFrame(handleLeft)
	}

	if (browser) {
        setUpGhost()
        // handleUp();
        // float();
        
		const pane = new Pane({ title: 'Scene' })

		// const sphereControls = pane.addFolder({ title: 'Sphere' })
		// sphereControls.addInput(sphere, 'position')

		// sphereControls.on('change', ({ value }) => {
		// 	sphere.position = value as any // 🤫
		// })
	}
</script>

<div class="scene">
    <Threlte.Canvas>
        <HTML position={{ y: -20, x: 0, z: 0 }} transform>
            <button
              class="w-48 bg-brand rounded-full px-3 text-white hover:opacity-90 active:opacity-70"
            on:click={() => {handleUp()}} >
              <img src={up} alt="up"/>
            </button>
            <button
              class="w-48 bg-brand rounded-full px-3 text-white hover:opacity-90 active:opacity-70"
              on:click={() => {handleDown()}} >
              <img src={down} alt="down"/>
            </button>
            <button
              class="w-48 bg-brand rounded-full px-3 text-white hover:opacity-90 active:opacity-70"
              on:click={() => {handleRight()}} >
              <img src={right} alt="right"/>
            </button>
            <button
              class="w-48 bg-brand rounded-full px-3 text-white hover:opacity-90 active:opacity-70"
              on:click={() => {handleLeft()}}>
              <img src={left} alt="left"/>
            </button>
        </HTML>
        <!-- <Threlte.Mesh
            geometry={new Three.SphereGeometry(4, 64, 64)}
            material={new Three.MeshStandardMaterial({ color: 'white' })}
            position={sphere.position}
            receiveShadow
            castShadow
        /> -->
        <Threlte.Object3DInstance object={gridHelper}/>
        <Threlte.Object3DInstance object={axesHelper}/>
        <!-- Camera -->
        <Threlte.PerspectiveCamera position={{x: 0, y:20, z:20}} fov={50}>
            <!-- Controls -->
            <Threlte.OrbitControls />
        </Threlte.PerspectiveCamera>

        <!-- Lights the scene equally -->
        <Threlte.AmbientLight color="white" intensity={0.2}/>

        <!-- Light that casts a shadow -->
        <Threlte.DirectionalLight 
            color="white"
            intensity={2}
            position={{x: 10, y: 10}}
            shadow={{
                camera: { top: 8 },
            }}
        />

        <!-- Sphere -->
        <!-- <Threlte.Mesh
            geometry={new Three.SphereGeometry(4, 64, 64)}
            material={new Three.MeshStandardMaterial({ color: 'white' })}
            position={{ y: 4 }}
            receiveShadow
            castShadow
        /> -->

        <!-- Floor -->
        <Threlte.Mesh
            geometry={new Three.PlaneGeometry(40, 40)}
            material={new Three.MeshStandardMaterial({
            color: 'white',
            side: Three.DoubleSide,
            })}
            rotation={{ x: Utils.DEG2RAD * 90 }}
            receiveShadow
        />
        <Extra.GLTF url={"./models/cute_ghost.glb"} {...ghost}/>
    </Threlte.Canvas>
</div>

<style>
    .scene {
      width: 100%;
      height: 100%;
      position: absolute;
      inset: 0;
      background: radial-gradient(hsl(220 14% 20%), hsl(220 20% 10%));
      background-attachment: fixed;
    }
</style>