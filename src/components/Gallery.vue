<template>
<div class="container">
    <div class="row justify-content-center">
        <div class="card col-12 mt-3 mb-3">
            <div class="card-header">
                        <div class="row  justify-content-center">
                            <div class="col-lg-8 col-sm-12">
                                <form method="GET" v-on:submit.prevent="search">
                                    <div class="input-group mb-3">
                                    <button class="btn btn-outline-primary" type="submit" id="button-addon1" data-mdb-ripple-color="dark">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-search" viewBox="0 0 16 16">
                                            <path d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001c.03.04.062.078.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1.007 1.007 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0z"/>
                                        </svg>
                                    </button>
                                    <input
                                        type="text"
                                        class="form-control"
                                        placeholder=""
                                        aria-label="Example text with button addon"
                                        aria-describedby="button-addon1"
                                        v-model="looker.stmt"
                                    />
                                    </div>
                                </form>
                                
                            </div>                                                        
                                                      
                        </div>
                                                 
            </div>
            <div class="card-body">               
                <div class="container-fluid">
                    <div class="row justify-content-center">
                        <div class="spinner-border" style="width: 3rem; height: 3rem;" role="status" v-if="loading">
                            <span class="visually-hidden">Loading...</span>
                        </div>

                        <div class="col-lg-4 col-md-6 col-sm-12" v-for="(product,index) in products" :key="index">
                            <Product :product="product" />          
                        </div>
                    </div>
                </div>                
            </div>

        </div>


        
    </div>
</div>

</template>

<script>
import axios from 'axios';
import Product from './Product.vue';
export default {
    Name:'Gallery',
    components:{
        Product
    },
    data()
    {
        return{
            products:[],
            loading:false,
            looker:{
                stmt:''
            }
        }
    },
    created()
    {
        this.loading=true;
        axios.get("https://matjar-simple.000webhostapp.com/api/products").then((response)=>{
            this.products=response.data.products.data;
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
    },
    methods:{
        
        search()
        {
            this.products=[];
            this.loading=true;
            axios.get("https://matjar-simple.000webhostapp.com/api/product/search/"+this.looker.stmt).then((response)=>{
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

   
}
</script>




