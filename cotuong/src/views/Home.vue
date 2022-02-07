<template>
  <div>
    <div class="home">hello pixijs</div>
    <canvas id="pixi-canvas"></canvas>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import * as PIXI from "pixi.js";

export default defineComponent({
  setup() {
    return {};
  },

  methods: {
    // demo() {
    //   const app = new Application({
    //     view: document.getElementById("pixi-canvas") as HTMLCanvasElement,
    //     resolution: window.devicePixelRatio || 1,
    //     autoDensity: true,
    //     backgroundColor: 0x6495ed,
    //     width: 640,
    //     height: 480,
    //   });

    //   const clampy: Sprite = Sprite.from("favicon.ico");

    //   clampy.anchor.set(0.5);

    //   clampy.x = app.screen.width / 2;
    //   clampy.y = app.screen.height / 2;

    //   app.stage.addChild(clampy);
    // },

    demo2() {
      // Create the application helper and add its render target to the page
      let app = new PIXI.Application({ width: 640, height: 360 });
      document.body.appendChild(app.view);

      // Create the sprite and add it to the stage
      let sprite = PIXI.Sprite.from("favicon.ico");
      app.stage.addChild(sprite);

      // Add a ticker callback to move the sprite back and forth
      let elapsed = 0.0;
      app.ticker.add((delta) => {
        elapsed += delta;
        sprite.x = 100.0 + Math.cos(elapsed / 50.0) * 100.0;
      });
    },
  },

  mounted() {
    this.demo2();
  },
});
</script>
