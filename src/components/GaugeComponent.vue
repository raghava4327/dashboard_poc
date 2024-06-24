<template>
  <div class="container">
    <vue-gauge
      :refid="'type-unique-id'"
      :class="'metricsGauge'"
      :options="gaugeOptions"
    >
    </vue-gauge>
  </div>
</template>

<script>
import VueGauge from "vue-gauge";

export default {
  components: { VueGauge },
  props: {
    needleValue: {
      type: Number,
      required: true
    }
  },
  computed: {
    gaugeOptions() {
      return {
        needleValue: this.needleValue,
        centralLabel: '',
        needleColor: '#410082',
        arcDelimiters: [25, 50, 75],
        arcColors: ['#8264db', '#8264db', '#8264db', '#8264db'],
        arcOverEffect: true,
        arcLabels: ['50', '100', '150'],
        chartWidth: 225,
        rangeLabel: ['0', '200'],
        hasNeedle: true,
      };
    }
  }
};
</script>

<style>
.container {
  display: flex;
  justify-content: center;
}
</style>
