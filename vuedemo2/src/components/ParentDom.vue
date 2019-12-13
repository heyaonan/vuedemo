
//一个非prop特性是指向一个组件传递，但是该组件并没有相应的prop定义的特性
//显示的定义prop可以向组件传入信息，但是组件库的作者并不能总是预见组件的应用场景，所以子组件默认可以接收
//任意的特性，而对于在子组件中没有定义prop的特性，会被添加到该组件的根元素中
// 1:替换和合并特性
对于子组件已有的大多数特性来说，若父组件向子组件传入了同样的特性，则子组件的特性会被覆盖，其中class和type特性除外
若父组件向子组件传递了class特性，则子组件会合并父组件和本身的class特性，style同样。
//2：禁用特性继承
若子组件不希望父组件传入的特性添加到根元素上,可以设置inheritAttrs: false，这个功能配合实例的$attrs属性一起使用，
可以实现非prop特性跨组件传递，例如a组件包含b组件，b组件包含c组件，a和c传递信息，就可以使用这种方法，参见本例
注意 inheritAttrs: false 选项不会影响 style 和 class 的绑定和传入，子组件会合并
<template>
<div>
 <ChildDom class="a" v-bind:foo="foo" v-bind:doo="doo"></ChildDom>
</div>
</template>
<script>
import ChildDom from './ChildDom'
export default {
 name: "parent-dom",
 data() {
   return {
     foo:"hello foo",
     doo:"hello doo"
   }
 },
 components:{
   ChildDom
 }
}
</script>
