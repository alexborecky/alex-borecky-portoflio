<template>
  <div class="hero">
    <div class="container">
      <div class="v-proposition flex center">
        <div class="">
          <p>Welcome 👋</p>
          <h1> <nuxt-link to="/about" class="link" href=""> <div class="highlight"></div> <div class="underline"></div> Alex Borecky </nuxt-link> is a Product Designer based in Prague, currently working as a freelancer </h1>
        </div>
      </div>
      <div class="featured box flex center-column-top">
        <feature
          projectTitle="Shoptetak.cz"
          projectDes="Website for a partnered client which provides services in e-commerce design and development"
          featureImg="https://ik.imagekit.io/alexborecky/My__Web/shoptetak_W-mXIlftz.png"
        />
        <feature class="switch"
          projectTitle="Opal"
          projectDes="A Shoptet template focusing on specific industry of Fashion, created for Shoptetak.cz"
          featureImg="https://ik.imagekit.io/alexborecky/My__Web/opal_FuFKlNQNJpy8.png"
        />
        <feature class="dark-image low-image"
          projectTitle="Chat Thread"
          projectDes="Thread feature study, which enriches experience of organisation in group channels "
          featureImg="https://ik.imagekit.io/alexborecky/My__Web/phone_kM28kFfUMii.png"
        />
        <feature class="switch blue-image low-image"
          projectTitle="smart.res"
          projectDes="Reservation and payment application that ease the process of going out to a restaurant"
          featureImg="https://ik.imagekit.io/alexborecky/My__Web/smart.res_Yt_EwNct6.png"
        />
      </div>
    </div>
  </div>
</template>

<script>


export default {
  components: {
    
  }
}
</script>

<style lang="scss" scoped>

.v-proposition {
  height: 60vh;
  h1 {
    max-width: 860px;
    .link {
      position: relative;
      transition: .4s ease-in-out;
      .highlight {
        top: -4px;
        position: absolute;
        height: 105%;
        width: 0%;
        background-color: $main-blue;
        z-index: -1;
        // transform: scaleX(0);
        transition: .4s ease-in-out;
      }
      .underline {
        position: absolute;
        height: 2px;
        bottom: 0;
        width: 95%;
        background-color: $web-black;
        z-index: -1;
        // transform: scaleX(0);
        transition: .4s ease-in-out;
      }
      &:hover {
        .highlight {
          width: 95%;
        }
        .underline {
          opacity: 0;
        }
        color: white;
      }
    }
  }
}

</style>
