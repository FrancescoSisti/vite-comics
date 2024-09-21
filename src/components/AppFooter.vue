<script>
  export default {
    data() {
      return {
        name: 'AppFooter',
        footerSections: [
          {
            title: 'DC COMICS',
            items: ['Characters', 'Comics', 'Movies', 'TV', 'Games', 'Videos', 'News']
          },
          {
            title: 'SHOP',
            items: ['Shop DC', 'Shop DC Collectibles']
          },
          {
            title: 'DC',
            items: ['Terms Of Use', 'Privacy policy (New)', 'Ad Choices', 'Advertising', 'Jobs', 'Subscriptions', 'Talent Workshops', 'CPSC Certificates', 'Ratings', 'Shop Help', 'Contact Us']
          },
          {
            title: 'SITES',
            items: ['DC', 'MAD Magazine', 'DC Kids', 'DC Universe', 'DC Power Visa']
          }
        ]
      }
    }
  }
</script>

<template>
  <footer>
    <div class="footer-top">
      <div class="d-flex container">
        <div class="col-md-8 footer-list">
          <div class="row">
            <div v-for="(section, index) in footerSections" :key="index" class="col">
              <h4>{{ section.title }}</h4>
              <ul>
                <li v-for="(item, idx) in section.items" :key="idx">{{ item }}</li>
              </ul>
            </div>
          </div>
        </div>
        <div class="col-md-4 footer-image text-end">
          <img src="../assets/img/dc-logo-bg.png" alt="DC Image">
        </div>
      </div>
    </div>
    <div class="footer-bottom">
      <div class="container d-flex justify-content-between">
        <div class="signup text-center my-3">
          <button id="join-us" class="btn">SIGN-UP NOW!</button>
        </div>

        <div class="social-media d-flex align-items-center gap-4">
          <p class="mb-0">FOLLOW US</p>
          <div class="social-icons d-flex justify-content-center gap-3">
            <img src="../assets/img/footer-facebook.png" alt="Facebook">
            <img src="../assets/img/footer-twitter.png" alt="Twitter">
            <img src="../assets/img/footer-youtube.png" alt="Youtube">
            <img src="../assets/img/footer-pinterest.png" alt="Pinterest">
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<style scoped lang="scss">
  @use '../../styles/variables';

  footer {
    color: variables.$secondary-color;
    background-color: variables.$footer-background-color;
  }

  .footer-bottom {
    color: variables.$primary-color;
    background-color: variables.$footer-background-color;
    position: relative;
    bottom: 0;
    right: 0;
    z-index: 2;
  }

  .footer-top {
    padding: 20px;
    background-image: url(../assets/img/footer-bg.jpg);
    background-size: cover;
  }

  h4 {
    margin-bottom: 10px;
  }

  ul {
    list-style: none;
    padding: 0;
    margin-bottom: 20px;
  }

  li {
    margin-bottom: 5px;
    color: variables.$secondary-color;
    text-shadow: 0 2px 2px black;
    cursor: pointer;

    &:hover {
      color: variables.$primary-color;
      transform: scale(1.05);
    }
  }

  .footer-image img {
    width: 300px;
  }

  .social-icons {
    cursor: pointer;

    img:hover {
      color: variables.$primary-color;
      transform: scale(1.1);
    }
  }

  #join-us {
    border-color: variables.$primary-color;
    color: variables.$title-color;
    transition: background-color 0.3s ease, transform 0.3s ease;

    &:hover {
      background-color: variables.$background-color;
      color: variables.$primary-color;
      transform: scale(1.05);
      box-shadow: 0px 4px 15px rgba(0, 123, 255, 0.6);
    }
  }
</style>