<template>
    <div class="games">
        <div class="games-top">
            <div class="games-title">{{ gameTitle }}</div>
            <div class="more">more</div>
        </div>
        <swiper class="swiper" :options="swiperOption">
            <swiper-slide v-for="item in 8" :key="item">
                <img src="@/assets/images/home/GFY03.png" @click="$router.push('/games-detail-m')" />
                <span class="game-title">Matchstick Men</span>
            </swiper-slide>
            <div class="swiper-scrollbar" slot="scrollbar"></div>
        </swiper>
    </div>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'

export default {
    name: 'nft-games',
    components: { Swiper, SwiperSlide },
    data() {
        return {
            swiperOption: {
                slidesPerView: 'auto',
                loopedSlides: 4,
                freeMode: true,
                dragSize: 30,
                scrollbar: {
                    el: '.swiper-scrollbar',
                },
            },
        }
    },
    props: {
        gameTitle: {
            type: String,
            default: 'Games',
        },
    },
    mounted() {},
}
</script>

<style lang="less" scoped>
.games {
    margin-top: 50px;
    .games-top {
        display: flex;
        align-items: center;
        .games-title {
            font-size: 34px;
            font-weight: bold;
            color: #fcfbfb;
        }
        .more {
            margin-left: auto;
            width: 80px;
            height: 32px;
            background: #232323;
            border-radius: 16px;
            font-size: 20px;
            font-weight: 400;
            color: #999999;
            line-height: 32px;
            text-align: center;
        }
    }
    .swiper {
        margin-top: 34px;
        overflow-x: hidden;
        overflow-y: visible;
        height: 420px;
        .swiper-slide {
            width: 240px;
            height: 320px;
            margin-right: 20px;
            img {
                width: 100%;
                height: 100%;
                border-radius: 10px;
            }
            .game-title {
                font-size: 24px;
                font-weight: 400;
                color: #e8e8e8;
                padding-left: 10px;
            }
        }
        .swiper-scrollbar {
            bottom: 0px;
            width: 300px;
            left: 50%;
            transform: translateX(-50%);
            background: #292929;
        }
        /deep/ .swiper-scrollbar-drag {
            background: #268aef;
        }
    }
}
</style>
