<script>
  import { T } from '@threlte/core'
  import { ContactShadows, Float, Grid, OrbitControls, Environment } from '@threlte/extras'

  import Can from "./models/Gleem_Can_DragonFruitMango.svelte"
  import Dragonfruit from "./models/Dragonfruit.svelte"
  import Mango from "./models/Mango.svelte"
</script>

<Environment
  path="/envmap/"
  files="overcast.hdr"
  isBackground={false}
  format="hdr"
  groundProjection={{ radius: 200, height: 5, scale: { x: 100, y: 100, z: 100 } }}
/>

<T.PerspectiveCamera
  makeDefault
  position={[-10, 10, 10]}
  fov={15}
>
  <OrbitControls
    autoRotate
    enableZoom={true}
    enableDamping
    autoRotateSpeed={0.5}
    target.y={1.75}
  />
</T.PerspectiveCamera>

<T.DirectionalLight
  intensity={0.5}
  position.x={5}
  position.y={10}
/>

<Grid
  position.y={-0.001}
  cellColor="#ffffff"
  sectionColor="#ffffff"
  sectionThickness={0}
  fadeDistance={25}
  cellSize={2}
/>

<ContactShadows
  scale={10}
  blur={2}
  far={2.5}
  opacity={0.5}
/>

<Float
  floatIntensity={0.5}
  floatingRange={[0, 1]}
>
  <Can scale={0.5} />
  <Dragonfruit scale={0.5} position.x={1} />
  <Mango scale={0.5} position.y={0.5} position.x={-1.25} />
</Float>


