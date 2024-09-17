<script>
export default {
    data() {
        return {
            name: 'AppHeader'
        }
    }
}
</script>

<template>
    <header class="app-header">
        <div class="container d-flex justify-content-between align-items-center">
            <div class="logo">
                <img src="../assets/img/dc-logo.png" alt="DC Logo">
            </div>
            <nav class="nav-links">
                <ul>
                    <li><a href="#">Characters</a></li>
                    <li><a href="#">Comics</a></li>
                    <li><a href="#">Movies</a></li>
                    <li><a href="#">TV</a></li>
                    <li><a href="#">Games</a></li>
                    <li><a href="#">Collectibles</a></li>
                    <li><a href="#">Videos</a></li>
                    <li><a href="#">Fans</a></li>
                    <li><a href="#">News</a></li>
                    <li><a href="#">Shop</a></li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<style scoped lang="scss">
@use '../../styles/variables'as vars;

.app-header {
    background-color: white; 
    padding: 20px 40px; 
    color: vars.$header-color;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); 

    .logo img {
        height: 60px; 
        transition: transform 0.3s ease; 
        
        &:hover {
            transform: scale(1.1); 
        }
    }

    .nav-links ul {
        list-style: none;
        display: flex;
        gap: 20px; 
        margin: 0;
        padding: 0;

        li a {
            color: vars.$header-color;
            text-decoration: none;
            font-weight: bold;
            position: relative; 
            padding-bottom: 5px; 
            font-size: 18px;
            transition: color 0.3s ease; 

            &:hover {
                color: #1e90ff; 
                text-decoration: none; 
            }

            &::after {
                content: '';
                position: absolute;
                left: 0;
                right: 0;
                bottom: 0;
                height: 3px; 
                background-color: #1e90ff; 
                transform: scaleX(0); 
                transition: transform 0.3s ease; 
            }

            &:hover::after {
                transform: scaleX(1); 
            }
        }
    }
}
</style>