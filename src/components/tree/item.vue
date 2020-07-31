<template>
    <li>
        <div @click="toggle">
            {{model.title}}
            <span v-if="isFolder">[{{open?'-':'+'}}]</span>
        </div>
        <ul v-show="open" v-if="isFolder">
            <item class="item" v-for="model in model.children" 
            :model="model"
            :key="model.id">
            </item>
        </ul>
    </li>
</template>
<script>
    export default{
        name:'Item',
        props:{
            model:{
                type:Object,
                require:true
            }
        },
        data(){
            return{
                open:false
            };
        },
        computed:{
            isFolder:function(){
                return this.model.children && this.model.children.length;
            }
        },
        methods:{
            toggle:function(){
                if(this.isFolder){
                    this.open = !this.open
                }
            },
        }
    }
</script>