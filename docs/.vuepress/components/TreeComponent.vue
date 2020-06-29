<template>
  <svg :height="height" :width="width">
    <svg v-for="(item, index) in maxTreeDepth" :key="'arc' + index">
      <path
        class="gray-line"
        :d="
          describeArc(
            width / 2,
            height / 2,
            (maxRadius / maxTreeDepth) * (index + 1),
            -angle / 2,
            angle / 2
          )
        "
      />
    </svg>
    <svg v-for="(item, index) in maxTreeDepth" :key="index">
      <circle class="is-blue" :r="5" :cy="center.x" :cx="center.y" />
    </svg>
    <tree-node
      :radius="(maxRadius / maxTreeDepth) * 1"
      :tree-data="tree"
      :center="center"
      :angle-start="-135"
      :angle-end="135"
    />
  </svg>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator';
import TreeNode from './TreeNode.vue';

interface Point {
  x: number;
  y: number;
}

const getArrayDepth = (value: any[]): number => {
  return Array.isArray(value) ? 1 + Math.max(...value.map(getArrayDepth)) : 0;
};

@Component({
  components: {
    TreeNode,
  },
})
export default class TreeComponent extends Vue {
  @Prop() private message!: string;
  @Prop() private height!: number;
  @Prop() private width!: number;
  @Prop({ default: 270 }) private angle!: number;
  private tree: any[] = [0, 1, 2];

  get center(): Point {
    return { x: this.width / 2, y: this.height / 2 };
  }

  get maxTreeDepth(): number {
    let depth = getArrayDepth(this.tree);
    console.log('getting tree depth', depth);
    return depth;
  }
  get maxRadius(): number {
    return (this.height - 10) / 2;
  }

  polarToCartesian = (
    centerX: number,
    centerY: number,
    radius: number,
    angleInDegrees: number
  ): Point => {
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
}
</script>

<style lang="scss">
.gray-line {
  stroke: gainsboro !important;
  stroke-width: 1;
  fill: none;

  &:hover {
    stroke: red !important;
  }
}

.has-background-blue {
  fill: blue !important;
  stroke: none;

  &:hover {
    fill: red !important;
  }
}
</style>
