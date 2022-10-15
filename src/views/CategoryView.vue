<template id="category-template">
    <div class="container-fluid">
        <div class="row justify-content-center">
                      
        </div>
        <div class="row justify-content-center">
            <div class="col-lg-3 col-sm-12 m-2" v-for="(product,index) in products" :key="index">
                <Product :product="product"/>
            </div>
        </div>

    </div>
</template>
<script>
import Product from '../components/Product.vue';
import axios from 'axios';
export default {
    components:{
        Product
    },
    data()
    {
        return{
            products:[],
            loading:false
        }
    },
    created()
    {
        this.loading=true;
        axios.get("https://matjar-simple.000webhostapp.com/api/category/"+this.$route.params.id+"/products").then((response)=>{
            this.products=response.data.products;
        }).catch((error)=>{
            alert(error);
        }).finally(()=>{
            
            this.products.forEach(product => {
                product.pictures.forEach(picture=>{
                    picture.path="https://matjar-simple.000webhostapp.com/"+picture.path;
                });
            });
        
            this.loading=false;

            
        });
    }
}
</script>
