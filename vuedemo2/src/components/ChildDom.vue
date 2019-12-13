<template>
  <div class="b">
    <p>foo: {{foo}}</p>
    <p>attrs: {{$attrs}}</p>
    <child-dom-child v-bind="$attrs" v-bind:coo = "coo"></child-dom-child>
  </div>
</template>

<script>
import ChildDomChild from "./ChildDomChild";
export default {
  props: ["foo"],
  name: "child-dom",
  inheritAttrs: false,
  components: {
    "child-dom-child": ChildDomChild
  },
  data() {
    return {
      coo: "hello coo"
    }
  },
};
</script>