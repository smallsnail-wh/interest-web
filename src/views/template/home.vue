<template>
    <div class="home">
        <div >
            <Carousel autoplay v-model="value2" loop height="550px">
                <CarouselItem>
                    <img class="images-con" src="../../images/pi1.jpg">
                </CarouselItem>
                <CarouselItem>
                    <img class="images-con" src="../../images/pi2.jpg">
                </CarouselItem>
            </Carousel>
        </div>
    </div>
</template>
<script>
    export default {
        data(){
            return {
                value2: 0,
                formLogin:{
                    userName: null,
                    password: null
                },
                ruleLogin: {
                        userName: [
                            { required: true, message: '请填写用户名', trigger: 'blur' }
                        ],
                        password: [
                            { required: true, message: '请填写密码', trigger: 'blur' },
                        ]
                }
            }
        },
        methods: {
            login(formLogin){
                this.$refs[formLogin].validate((valid) => {
                    if(valid){
                        this.$store.dispatch('users/userLogin',{"user_name":this.formLogin.userName,"user_password":this.formLogin.password,"router":this.$router});
                    }
                })
            }
        }
    };
</script>
<style >
.box-flex .imgpic {
    transition: .7s all;
    opacity: 0.8;
}
.box-flex .imgpic:hover { opacity: 1; box-shadow: 1px 1px 20px #333;
transform:scale(1.1,1.1);cursor: pointer; }
.lineThrou{transition: .8s all;}
.lineThrou:hover{text-decoration:line-through;cursor: pointer}

</style>