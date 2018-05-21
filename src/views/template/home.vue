<template>
    <div class="home">
        <div >
            <Carousel autoplay v-model="value2" loop >
                <CarouselItem>
                    <img :style="{height:'550px'}" class="images-con" src="../../images/动漫.jpg">
                </CarouselItem>
                <CarouselItem>
                    <img :style="{height:'550px'}" class="images-con" src="../../images/吉他1.jpg">
                </CarouselItem>
                <CarouselItem>
                    <img :style="{height:'550px'}" class="images-con" src="../../images/滑板1.jpg">
                </CarouselItem>
            </Carousel>
        </div>

        <div class="box-flex flex-direction-column margin-top-2">
            <div class="box-flex width-80 margin-auto" v-for="(A,index) in HomeArticle">
               <div class="box-flex width-100" v-if="index%2==0"> 
                <div class="flex-1">
                  <img class="images-con imgpic" v-bind:src="(A.img_group[0].photopath)" >
                </div>
                <div class="box-flex flex-1 padding-all flex-direction-column">
                    <router-link :to="('/detail/'+A._id)">
                    <span class="tirtleFont lineThrou">{{A.tirtle}}</span>
                    </router-link>
                    <span class="contentFont">{{A.info}}</span>
                </div>
               </div>
               <div class="box-flex width-100" v-else> 
                <div class="box-flex flex-1 padding-all flex-direction-column">
                    <router-link :to="('/detail/'+A._id)">
                      <span class="tirtleFont lineThrou">{{A.tirtle}}</span>
                    </router-link>
                    <span class="contentFont">{{A.info}}</span>
                </div>
                <div class="flex-1">
                  <img class="images-con imgpic" v-vind:src="A.img_group[0].photopath" >
                  <!-- <img class="images-con imgpic" src="../../images/吉他1.jpg" > -->
                </div>
               </div>
            </div>
        </div>

    </div>
</template>
<script>
    export default {
        data(){
            return {
                value2: 0,
                HomeArticle: [
                    {
                        "img_group":[{"photopath":"/static/images/吉他1.jpg"}],
                        "_id":"1",
                        "tirtle":"test",
                        "info":"this is test",

                    },
                    {
                        "img_group":[{"photopath":"/static/images/吉他1.jpg"}],
                        "_id":"1",
                        "tirtle":"test",
                        "info":"this is test",
                        
                    }
                ],
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