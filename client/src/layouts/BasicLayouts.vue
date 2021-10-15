<template>

    <div>
        <header>

    <div class="basic-layout">
    <Menu />
    

    <div class="ui container">
        <slot />
    </div>
    </div>
     </header>
   </div>
   <Cart />
</template>

<script>
import Menu from '../components/Menu.vue';
import Cart from '../components/Cart/Cart.vue';

export default {
    name : "BasicLayouts",
    components: {
        Menu,
        Cart,
    },
};
</script>

<style>



</style>