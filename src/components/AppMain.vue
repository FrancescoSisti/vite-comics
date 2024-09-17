<script>
import comicsData from '../assets/comics/dc-comics.json';

export default {
    data() {
        return {
            name: 'AppMain',
            comics: comicsData,
            hoveredComicId: null
        }
    },
    methods: {
        showInfo(id) {
            this.hoveredComicId = id;
        },
        hideInfo() {
            this.hoveredComicId = null;
        }
    }
}
</script>

<template>
    <div class="comics-section">
        <div class="comics container">
            <div 
                v-for="comic in comics" 
                :key="comic.id" 
                class="comic-card"
                @mouseover="showInfo(comic.id)"
                @mouseleave="hideInfo"
            >
                <h5>{{ comic.series }}</h5>
                <img :src="comic.thumb" :alt="comic.title" />
                <div v-show="hoveredComicId === comic.id">
                    <p>{{ comic.type }}</p>
                    <p class="price">{{ comic.price }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
.comics {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
}

.comic-card {
    border: 1px solid #ccc;
    padding: 20px;
    width: 200px;
    text-align: center;
    position: relative;
}

.comic-card img {
    max-width: 100%;
    height: auto;
}

.price {
    font-weight: bold;
    color: #333;
}
</style>