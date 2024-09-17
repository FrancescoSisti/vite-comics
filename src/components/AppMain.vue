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
    <div class="container img-fluid">
        <img src="../assets/img/jumbotron.jpg" class="h-100" alt="jumbotron">
    </div>



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
                <div class="comic-info" v-show="hoveredComicId === comic.id">
                    <p>{{ comic.type }}</p>
                    <p class="price">{{ comic.price }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
* {
    font-family: 'Open Sans', sans-serif;
}

.comics-section {
    background-color: #1c1c1c;
    padding: 50px 0;
}

.comics {
    display: flex;
    flex-wrap: wrap;
    gap: 25px;
    justify-content: space-around;
    padding: 20px;
}

.comic-card {
    background-color: #ffffff;
    border-radius: 20px;
    width: 240px;
    text-align: center;
    overflow: hidden;
    position: relative;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease-in-out, box-shadow 0.3s ease-in-out;
}

.comic-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 15px 25px rgba(0, 0, 0, 0.2);
}

.comic-card img {
    width: 100%; /* Forza l'immagine a occupare il 100% della larghezza del contenitore */
    height: 300px; /* Imposta un'altezza fissa */
    object-fit: cover; /* Assicura che l'immagine si adatti mantenendo le proporzioni */
    border-bottom-left-radius: 15px;
    border-bottom-right-radius: 15px;
    transition: transform 0.3s ease-in-out;
}


.comic-card:hover img {
    transform: scale(1.05); /* Slight zoom on image */
}

.comic-info {
    position: absolute;
    bottom: 0;
    width: 100%;
    background: rgba(0, 0, 0, 0.8);
    color: white;
    padding: 15px;
    text-align: center;
    opacity: 0;
    transform: translateY(100%);
    transition: transform 0.4s ease-in-out, opacity 0.4s ease-in-out;
}

.comic-card:hover .comic-info {
    opacity: 1;
    transform: translateY(0); /* Slides up the info box */
}

.comic-info p {
    margin: 0;
    font-size: 0.9rem;
    letter-spacing: 1px; /* Increased letter spacing for a modern feel */
    text-transform: uppercase; /* Apply uppercase */
}

.comic-info .price {
    margin-top: 10px;
    font-weight: bold;
    font-size: 1.1rem;
    color: #ffcc00; /* Gold for price emphasis */
}

h5 {
    font-size: 1.3rem; /* Slightly larger for series name */
    margin: 15px 0;
    color: #333; /* Darker color for headings */
    letter-spacing: 0.5px;
    text-transform: uppercase; /* Series name in uppercase */
}

</style>
