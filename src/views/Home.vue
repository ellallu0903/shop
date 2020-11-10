<template lang="pug">
  #home
    b-row
      b-col(cols="12" md="6" lg="3" v-for="(item,index) in items" :key="index")
        b-card(:title="item.name" :img-src="item.img" img-top :sub-title="'$'+item.price")
          b-button(variant="primary"  @click="addCart(item)")
            font-awesome-icon(:icon="['fas','shopping-cart']")
            |  加入購物車
</template>

<script>
export default {
  name: 'Home',
  data () {
    return {
      items: [
        {
          img: 'https://e.ecimg.tw/items/DHAY3K1900AF2ZB/000001_1604571681.jpg',
          name: 'Microsoft 微軟 3吋10代i5輕薄觸控筆電',
          price: 22888
        },
        {
          img: 'https://d.ecimg.tw/items/DYAJ93A900AXPNV/000001_1603176778.jpg',
          name: 'Apple iPhone 12 (128G)-黑色',
          price: 28500
        },
        {
          img: 'https://d.ecimg.tw/items/DYAN70A900AUPA5/000001_1599102543.jpg',
          name: '小米手環 5',
          price: 845
        },
        {
          img: 'https://e.ecimg.tw/items/DYAJE01900AXAFZ/000001_1603678779.jpg',
          name: 'AirPods Pro',
          price: 6090
        }
      ]
    }
  },
  methods: {
    addCart (item) {
      this.$store.commit('addCart', item)
    }
  }
}
</script>
