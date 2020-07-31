<template>
    <div class="box" v-if="isShow">
        <p>{{title}}</p>
        <p class="box-content">{{message}}</p>
    </div>
</template>
<script>
    export default{
        props:{
            title:{
                type:String,
                default:''
            },
            message:{
                type:String,
                default:''
            },
            duration:{
                type:Number,
                default:1000
            }
        },
        data(){
            return{
                isShow:false
            }
        },
        methods:{
            show(){
                this.isShow = true;
                setTimeout(this.hide,this.duration);
            },
            hide(){
                this.isShow = false;
                this.remove();
            }
        }
    }
</script>
<style>
    .box{
        position:fixed;
        padding:8px 8px;
        top:10px;
        left:50%;
        transform: translateX(-50%);
        text-align:center;
    }
    .box-content{
        width:200px;
        margin:10px auto;
        font-size:14px;
        border:blue 3px solid;
        padding:8px 16px;
        background:#fff;
        border-radius:1px;
        margin-bottom:8px;
    }
</style>