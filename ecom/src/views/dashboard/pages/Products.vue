<template>
  <v-container fluid>
    <v-row>
      <v-col
        :cols="3"
      >
        <v-select
          :items="currency"
          label="Currency"
          outlined
        />
      </v-col>
    </v-row>
    <v-row dense>
      <v-col
        v-for="(card,i) in products"
        :key="card['product-name'] + i"
        :cols="3"
      >
        <v-card>
          <v-img
            :src="card['product-image-url']"
            class="white--text align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="200px"
          >
            <v-card-title v-text="card['product-name']" />
          </v-img>

          <v-card-actions>
            <div
              :class="[`text-h2`, active && `mb-1`]"
              class="transition-swing"
              v-text=" card['product-price']"
            />
            <v-spacer />

            <v-btn icon>
              <v-icon>mdi-heart</v-icon>
            </v-btn>

            <v-btn icon>
              <v-icon>mdi-cart-outline</v-icon>
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
  export default {

    data: function () {
      return {
        currency: ['USD', 'EU', ''],
        cards: [
          { title: 'Pre-fab homes', src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg', flex: 12 },
          { title: 'Favorite road trips', src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg', flex: 6 },
          { title: 'Best airlines', src: 'https://cdn.vuetifyjs.com/images/cards/plane.jpg', flex: 6 },
        ],
        products: [
          {
            id: 1,
            'product-name': "MEN'S BETTER THAN NAKED&trade; JACKET",
            'product-image-url': 'http://images.thenorthface.com/is/image/TheNorthFace/236x204_CLR/mens-better-than-naked-jacket-AVMH_LC9_hero.png',
            'header-top-right-text': 'Shop All',
            'header-top-left-text': "Men's",
            'product-url': 'http://www.thenorthface.com/catalog/sc-gear/men-39-s-better-than-naked-8482-jacket.html',
            'header-top-right-url': 'http://www.thenorthface.com/en_US/shop-mens/',
            'product-cta-text': 'Shop Now',
            'product-price': '19.99',
          },
          {
            id: 2,
            'product-name': "WOMEN'S BETTER THAN NAKED&trade; JACKET",
            'product-image-url': 'http://images.thenorthface.com/is/image/TheNorthFace/236x204_CLR/womens-better-than-naked-jacket-AVKL_NN4_hero.png',
            'header-top-right-text': 'Shop All',
            'header-top-left-text': "Women's",
            'product-url': 'http://www.thenorthface.com/catalog/sc-gear/women-39-s-better-than-naked-8482-jacket.html',
            'header-top-right-url': 'http://www.thenorthface.com/en_US/shop-womens/',
            'product-cta-text': 'Shop Now',
            'product-price': '9.99',
          },
          {
            id: 3,
            'product-name': "WOMEN'S SINGLE-TRACK SHOE",
            'product-image-url': 'http://images.thenorthface.com/is/image/TheNorthFace/236x204_CLR/womens-single-track-shoe-ALQF_JM3_hero.png',
            'header-top-right-text': 'Shop All',
            'header-top-left-text': 'Running Shoes',
            'product-url': 'http://www.thenorthface.com/catalog/sc-gear/womens-single-track.html',
            'header-top-right-url': 'http://www.thenorthface.com/webapp/wcs/stores/servlet/TNFSearchResult?langId=-1&amp;storeId=207&amp;catalogId=10201&amp;searchTerm=running%20shoes',
            'product-cta-text': 'Shop Now',
            'product-price': '21.00',
          },
          {
            id: 4,
            'product-name': 'Enduro Boa&reg; Hydration Pack',
            'product-image-url': 'http://images.thenorthface.com/is/image/TheNorthFace/236x204_CLR/enduro-boa-hydration-pack-AJQZ_JK3_hero.png',
            'header-top-right-text': 'Shop All',
            'header-top-left-text': 'Equipment',
            'product-url': 'http://www.thenorthface.com/catalog/sc-gear/enduro-boa.html',
            'header-top-right-url': 'http://www.thenorthface.com/en_US/shop-equipment/',
            'product-cta-text': 'Shop Now',
            'product-price': '19.99',
          },
          {
            id: 5,
            'product-name': "MEN'S BETTER THAN NAKED&trade; JACKET",
            'product-image-url': 'http://images.thenorthface.com/is/image/TheNorthFace/236x204_CLR/mens-better-than-naked-jacket-AVMH_LC9_hero.png',
            'header-top-right-text': 'Shop All',
            'header-top-left-text': "Men's",
            'product-url': 'http://www.thenorthface.com/catalog/sc-gear/men-39-s-better-than-naked-8482-jacket.html',
            'header-top-right-url': 'http://www.thenorthface.com/en_US/shop-mens/',
            'product-cta-text': 'Shop Now',
            'product-price': '8.99',
          },
          {
            id: 6,
            'product-name': "WOMEN'S BETTER THAN NAKED&trade; JACKET",
            'product-image-url': 'http://images.thenorthface.com/is/image/TheNorthFace/236x204_CLR/womens-better-than-naked-jacket-AVKL_NN4_hero.png',
            'header-top-right-text': 'Shop All',
            'header-top-left-text': "Women's",
            'product-url': 'http://www.thenorthface.com/catalog/sc-gear/women-39-s-better-than-naked-8482-jacket.html',
            'header-top-right-url': 'http://www.thenorthface.com/en_US/shop-womens/',
            'product-cta-text': 'Shop Now',
            'product-price': '12.99',
          },
          {
            id: 7,
            'product-name': "WOMEN'S SINGLE-TRACK SHOE",
            'product-image-url': 'http://images.thenorthface.com/is/image/TheNorthFace/236x204_CLR/womens-single-track-shoe-ALQF_JM3_hero.png',
            'header-top-right-text': 'Shop All',
            'header-top-left-text': 'Running Shoes',
            'product-url': 'http://www.thenorthface.com/catalog/sc-gear/womens-single-track.html',
            'header-top-right-url': 'http://www.thenorthface.com/webapp/wcs/stores/servlet/TNFSearchResult?langId=-1&amp;storeId=207&amp;catalogId=10201&amp;searchTerm=running%20shoes',
            'product-cta-text': 'Shop Now',
            'product-price': '7.99',
          },
          {
            id: 8,
            'product-name': 'Enduro Boa&reg; Hydration Pack',
            'product-image-url': 'http://images.thenorthface.com/is/image/TheNorthFace/236x204_CLR/enduro-boa-hydration-pack-AJQZ_JK3_hero.png',
            'header-top-right-text': 'Shop All',
            'header-top-left-text': 'Equipment',
            'product-url': 'http://www.thenorthface.com/catalog/sc-gear/enduro-boa.html',
            'header-top-right-url': 'http://www.thenorthface.com/en_US/shop-equipment/',
            'product-cta-text': 'Shop Now',
            'product-price': '18.99',
          },
        ],
      }
    },
  }
</script>
