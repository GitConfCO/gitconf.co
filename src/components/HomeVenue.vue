<template>
  <section class="home-venue">
    <div class="container">
      <div class="home-venue__content wow fadeIn">
        <div class="home-venue__title-container">
          <h2 class="home-venue__title" data-heading="Venue">Venue</h2>
        </div>
        <div class="home-venue__details">
          <h3 class="home-venue__name">{{ name }}</h3>
          <p class="home-venue__description">{{ description }}</p>
          <p class="home-venue__description">{{ address }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import WOW from 'wow.js/dist/wow.min';

export default {
  name: 'home-venue',
  data() {
    return {
      name: 'Ruta N',
      description: "Medellin's own business and innovation center. A strategic location close to Metro.",
      address: 'Complejo Ruta N, Calle 67 N° 52-20, Medellín - Colombia.',
    };
  },
  mounted() {
    new WOW().init();
  },
};
</script>

<style lang="scss">
@import '../styles/variables';
@import '../styles/mixins';
@import '../styles/typography';

.home-venue {
  @extend %gc-section-padding;

  background: linear-gradient(rgba(#000, 0.6), rgba(#000, 0.6)),
              url('../assets/images/pictures/venue.jpg');
  background-attachment: fixed;
  background-repeat: no-repeat;
  background-size: cover;
  border-top: 2px solid $corn;
  position: relative;
  z-index: 0;

  &__content {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 0 20px 20px 0;

    @include from('lg') {
      flex-direction: row;
    }
  }

  &__description {
    @extend %gc-body2;
  }

  &__details {
    @include gc-double-box($corn, $ebony, 20px);

    flex: 1;
    padding: 25px;

    @include from('md') {
      padding: 40px;
    }
  }

  &__name {
    @extend %gc-paragraph-title;
  }

  &__title {
    @extend %gc-section-title;
  }

  &__title-container {
    flex: 1;
    margin-bottom: 56px;

    @include from('lg') {
      margin-bottom: 0;
    }
  }
}
</style>
