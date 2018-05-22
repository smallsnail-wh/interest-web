<template>
    <div id="mywork">
	    <div class="page-header-main">
	      <div class="box-flex width-80 margin-auto margin-top-2 flex-direction-column flex-justify-center flex-items-center">
	        <div class="line-height-50 font-size-22">test</div>
	        <!-- <div class="line-height-30 font-size-12">wqewq</div> -->
	        <div class="text-align-center margin-top-2">
	          <!-- <img class="images-con border-radius-9" v-bind:src="(config.api+article.img_group[0].photopath)"> -->
	          <img class="images-con border-radius-9" src="../../images/吉他1.jpg">
	        </div><!-- 
	        <div class="detailContent" v-html="article.content"></div> -->
	      </div>
	    </div>
  </div>
</template>
<script>
    export default {
        data(){
            return {
                
            }
        },
        mounted(){
            console.log(this.$route.params.id);
        },
        methods: {
            
        }
    };
</script>