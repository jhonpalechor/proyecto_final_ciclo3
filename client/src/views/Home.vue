  
<template>
   <BasicLayouts>
 

    <div class="titulo">
    <h1>FOOD FAST</h1> 
   
    </div>
   
    <div class="ui grid">
    <div
    class="sixten wide mobile eight wide tablet four wide computer column"
    v-for="product in products"
    :key="product.id"
    >
      <Product :product="product" />
      </div>
    </div>
  

 </BasicLayouts>
  

</template>

<script>
import { ref, onMounted } from 'vue';
import BasicLayouts from '../layouts/BasicLayouts.vue';
import { getProducts } from '../api/product';
import Product from '../components/Product';
export default {
  name: 'Home',
  components: {
    BasicLayouts,
    Product,
  },
  setup() {
    let products = ref(null);
     
      onMounted(async () => {
      const response = await getProducts(20);
      products.value = response;
    });
    return {
      products,
    };
  },
};
</script>

<style>
header{
   background-image: url(../assets/fondo.png);
   background-repeat: no-repeat; /* para que no se repita la imagen */
   background-size: 99% 99%; /* alto y ancho por eso dos veces */
   height: 100vh; /* par que se ajuste al tamaño de la pantalla */
   color: white;

  
}

.titulo {
        color: #ffd207;
        /* background-image: url('../assets/banner.png');  */
}
</style>


