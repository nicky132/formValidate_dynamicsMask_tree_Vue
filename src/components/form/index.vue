<template>
    <div>
        <h3>饿了吗表单</h3>
        <hr>
        <k-form :model="model" :rules="rules" ref = "loginForm">
            <k-form-item label="用户名" prop="username">
                <k-input v-model="model.username" autocomplete="off"></k-input>
            </k-form-item>
            <k-form-item label="确认密码" prop="password">
                <k-input type="password" v-model="model.password" autocomplete="off"></k-input>
            </k-form-item>
            <k-form-item>
                <button @click="submitForm('loginForm')">提交</button>
            </k-form-item>
        </k-form>
    </div>
</template>
<script>
    import kForm from "./form";
    import kFormItem from "./formItem";
    import kInput from "./input";
    import create from "../utils/create";
    import Notice from "../notice/knotice";
    export default{
        components:{
            kForm,
            kFormItem,
            kInput
        },
        data(){
            return{
                model:{
                    username:'tom',
                    password:''
                },
                rules:{
                    username:[{required:true,message:'请输入用户名'}],
                    password:[{required:true,message:'请输入密码'}]
                }
            }
        },
        methods:{
            submitForm(form){
                this.$refs[form].validate(valid=>{
                    const notice = create(Notice,{
                        title:"社会哥",
                        message:valid?"请求登录":"校验失败",
                        duration:1000
                    });
                    notice.show();
                });
            }
        }
    }
</script>