<template>
  <ul>
    <li v-for="na in name" v-bind:key="na">{{na}}</li>
  </ul>
  <h3>PRODUCT</h3>
  <ul>
    <li v-for="(na,idx) in product" v-bind:key="na">{{na.tit}} : {{na.price * na.sts}} {{na.sts}} 
      <button @click="increase(idx)"> + </button></li>
  </ul>
  <div>total : {{
    product[0].price * product[0].sts + product[1].price * product[1].sts + product[2].price * product[2].sts
  }}</div>
    <div>total : {{ total }} <button @click="allPrice">total</button></div>
  
</template>
<script>
export default {
  name: 'App',
  data() {
    return {
      total:0,
      name:['lee', 'kim'],
      product :reactive([
        {tit:"제품01", price:3000, sts:0},
        {tit:"제품02", price:4000, sts:0},
        {tit:"제품03", price:5000, sts:0},
      ]),
    }
    
  },
  methods : {
    increase(i){
      this.product[i].sts +=1
    }, 
    allPrice () {
      this.product.reduce((pr, cur) => {return this.total = pr + cur.price}, 0)
    }

  },

  
}

</script>

<style lang="scss">
h3 {
  color: #f00;
}

ul {
  color:#f00369;
  li {
    color: #333
  }
}
</style>