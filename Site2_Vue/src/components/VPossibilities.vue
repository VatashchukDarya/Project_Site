<script setup>

import Swiper from "swiper";
import {onMounted} from "vue";
import {Pagination} from "swiper/modules";


const possibilities = [
    {
        img: {
        src: '/public/chat_logo.svg',
        alt: '',
    },
    header4: 'Общение с классом',
    description: 'Видеосвязь' ,
    description1:'Чат с классом',
    },
    {
        img: {
        src: '/public/monitor_logo.svg',
        alt: '',
    },
    header4: 'Проведение занятий',
    description: 'Презентация файлов',
    description1:'Демонстрация экрана',
    },
    {
        img: {
        src: '/public/menu_logo.svg',
        alt: '',
    },
    header4: 'Посещаемость',
    description: 'Автоматическое',
    description1:'отслеживание присутствующих',
    },
    {
        img: {
        src: '/public/reload_logo.svg',
        alt: '',
    },
    header4: 'История занятий',
    description: 'Материалы урока'
    }
];

onMounted (() => {
    const swiper = new Swiper(".possibilities__swiper", {
        modules: [Pagination],
        spaceBetween: 30,
        pagination: {
            el: ".swiper-pagination",
            clickable: true,
        },
        breakpoints: {
            0:{
                slidesPerView: 1
            },
            560:{
                slidesPerView: 2
            },
            992:{
                slidesPerView: 3
            },
            1200:{
                slidesPerView:4
            },
        },
    });
})

</script>

<template>
    <section class="possibilities">
        <div class="container">
            <div class="possibilities__header">
                <h3>Возможности</h3>
            </div>
            <div class="possibilities__swiper-block">
                <div class="possibilities__swiper swiper">
                    <div class="possibilities__swiper-wrapper swiper-wrapper">
                        <div class="possibilities__swiper-slide swiper-slide" 
                            v-for="(item, index) in possibilities"
                            :key="index">
                            <div class="possibilities__card " :class="index%2===0 ? 'possibilities__card-blue' : 'possibilities__card-orange'">
                                <img :src="item.img.src" :alt="item.img.alt" class="possibilities__logo">
                                <h4>{{ item.header4 }}</h4>
                                <p>{{ item.description }}
                                </p>
                                <p>{{ item.description1 }}
                                </p>

                            </div>
                        </div>
                    </div>
                    <div class="swiper-pagination"></div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped> /*область видимости стиля*/

</style>