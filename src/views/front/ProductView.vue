<template>
  <h5 class="my-4">單一產品頁面</h5>  
  <img :src="product.imageUrl" width="200" class="img-fluid" alt="">
  <p>{{ product.title }}</p>
</template>

<script>
  const { VITE_APP_URL, VITE_APP_PATH } = import.meta.env
  export default {
    data () {
      return {
        product: {},
      }
    },
    methods: {
      getProduct () {
        const { id } = this.$route.params;
        this.$http.get(`${VITE_APP_URL}/api/${VITE_APP_PATH}/product/${id}`)
        .then((res) => {
          this.product = res.data.product;
        })
        .catch((err) => {
          alert(err.response.data.message);
        });
      }
    },
    mounted () {
      this.getProduct()
    },
  }
</script>