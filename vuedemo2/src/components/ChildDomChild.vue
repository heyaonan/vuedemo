<template>
<div class="c"> <p>doo: {{doo}}</p></div>
 
  
</template>

<script>
export default {
  inheritAttrs: false,
  props:["doo"],
  name: "child-dom-child",
}
</script>