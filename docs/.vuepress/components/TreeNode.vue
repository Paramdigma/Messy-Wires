<template>
  <svg>
    <svg v-for="(item, index) in treeData">
      <path
        stroke="black"
        :d="
          `M ${center.x} ${center.y} L ${itemPos(index).x} ${itemPos(index).y}`
        "
      />
      <circle
        class="tree-node"
        :cx="itemPos(index).x"
        :cy="itemPos(index).y"
        :r="4"
        @mouseover="onMouseEnter"
        @mouseout="onMouseLeave"
      />
    </svg>
  </svg>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';

@Component({
  name: 'tree-node',
})
export default class TreeNode extends Vue {
  @Prop() private treeData!: any[];
  @Prop() private angleStart!: number;
  @Prop() private angleEnd!: number;
  @Prop() private radius!: number;
  @Prop() private center!: { x: number; y: number };
  @Prop() private parent!: { x: number; y: number };

  private hovered: boolean = false;
  isData() {}
  itemAngle(index: number) {
    const step = (this.angleEnd - this.angleStart) / this.treeData.length;
    const angle: number = this.angleStart + step * index + step / 2;
    return angle;
  }

  itemPos(index: number) {
    return this.polarToCartesian(
      this.center.x,
      this.center.y,
      this.radius,
      this.itemAngle(index)
    );
  }

  polarToCartesian = (
    centerX: number,
    centerY: number,
    radius: number,
    angleInDegrees: number
  ): any => {
    var angleInRadians = ((angleInDegrees - 90) * Math.PI) / 180.0;

    return {
      x: centerX + radius * Math.cos(angleInRadians),
      y: centerY + radius * Math.sin(angleInRadians),
    };
  };

  describeArc = (
    x: number,
    y: number,
    radius: number,
    startAngle: number,
    endAngle: number
  ): string => {
    var start = this.polarToCartesian(x, y, radius, endAngle);
    var end = this.polarToCartesian(x, y, radius, startAngle);

    var largeArcFlag = endAngle - startAngle <= 180 ? '0' : '1';

    var d = [
      'M',
      start.x,
      start.y,
      'A',
      radius,
      radius,
      0,
      largeArcFlag,
      0,
      end.x,
      end.y,
    ].join(' ');

    return d;
  };
  onMouseEnter(event: any) {
    let radius: number = event.target.getAttribute('r') as number;
    const targetRadius = 10;
    console.log('radius', radius);
    event.target.setAttribute('r', 10);
  }
  onMouseLeave(event: any) {
    event.target.setAttribute('r', '4');
  }
}
</script>

<style lang="scss">
.tree-node {
  fill: white;
  stroke: blue;
}
</style>
