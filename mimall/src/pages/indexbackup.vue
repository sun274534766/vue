<template>
    <div class="index">
        <div class="container">
            <div class="swiper-box"></div>
                <swiper v-bind: options="swiperOption">
                    <swiper-slide v-for="(item,index) in slideList" v-bind: key="index">
                        <a v-bind:href="'/#/product/'+item.id"><img v-bind:src="item.img"></a>
                    </swiper-slide>
                <div class="swiper-pagination"  slot="pagination"></div>
                <div class="swiper-button-prev"  slot="button-prev"></div>
                <div class="swiper-button-next"  slot="button-next"></div>

                </swiper>
            <div class="ads-box"></div>
            <div class="banner"></div>
            <div class="product-box"></div>
        </div>
    </div>
</template>

<script>
    import ServiceBar from './../components/ServiceBar'
    import {swiper,swiperSlide} from 'vue-awesome-swiper'
    import 'swiper/dist/css/swiper.css'

    export default {
        name: "indexbackup",
        components:{
            swiper,
            swiperSlide,
            ServiceBar
        },
        data(){
            return {
                swiperOption:{

                    autoplay:true,
                    loop:true,
                    effect:'cube',
                    cubeEffect: {
                        slideShadows:true,
                        shadow:true,
                        shadowOffset:100,
                        shadowScale:0.6
                    },
                    pagination:{
                        el:'.swiper-pagination',
                        clickable:true
                    },
                    navigation:{
                        nextEl:'.swiper-button-next',
                        prevEl:'.swiper-button-prev',
                    }
                },
                slideList: [
                    {
                        id:'42',
                        img:'/imgs/slider/slide-1.jpg'
                    },
                    {
                        id:'45',
                        img:'/imgs/slider/slide-2.jpg'
                    },
                    {
                        id:'46',
                        img:'/imgs/slider/slide-3.jpg'
                    },
                    {
                        id:'',
                        img:'/imgs/slider/slide-4.jpg'
                    },
                    {
                        id:'',
                        img:'/imgs/slider/slide-5.jpg'
                    }
                ]
            }
        }
    }
</script>

<style lang="scss">

    .index{
       .swiper-box{
            .swiper-container{
                height:451px;
                img{
                    width:100%;
                    height:100%;
                }
            }

       }

    }

</style>