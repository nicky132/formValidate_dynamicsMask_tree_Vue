<template>
    <div>
        <input type="text" :value="value" @input="onInput" v-bind="$attrs">
    </div>
</template>
<script>
    export default{
        inheritAttrs:false,//父类上的属性消失，放到子组件上
        props:{
            value:{
                type:String,
                default:''
            }
        },
        methods:{
            onInput(e){
                this.$emit("input",e.target.value)
                this.$parent.$emit('validate')
            },
        }
    }
</script>