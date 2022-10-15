<template>
    <div class="product-card">
        <div class="offer" v-if="product.offer">
            {{product.offer.percentage}}
        </div>
        <div class="product-picture">
            <img v-bind:src="product.pictures[0].path" class="card-img-top" alt="...">
        </div>
        <div class="product-info">
            <div class="product-name">
                {{product.name}}
            </div>
            <div class="product-description">
                <p>{{product.description}}</p>
            </div>

            <div class="product-price">
                {{product.price}}
            </div>
                   
            <div class="product-action">
                <button v-on:click="show(product.id)">Show more</button>              
            </div>                   
        </div>

       

    </div>
</template>

<script>
export default {
    Name:'Product',
    props: {
        product:{}
    },
    methods:{
        show(id)
        {
            this.$router.push("/product/"+id);
        }
    }
   

}
</script>

<style>
.product-card{
    width:auto;
    height: auto;
    border-radius: 12px;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    background-color: #2196F3;
    color: white;

    position: relative;
}
.product-card .offer{
    width:75px;
    height: 100px;
    background-color: #FF8F00;
    text-align: center;
    padding: 16px;
    color: white;
    z-index: 100;
    position: absolute;
    top: 0;
    right: 0;
    clip-path:polygon(0 0,100% 0,100% 100%,50% 75%,0 100%);
    margin-right: 12px;
    font-size: large;
}
.product-card .offer::after{
    content:'%'
}
.product-card .product-picture{
    clip-path: polygon(0 0,100% 0,100% 80%,0 100%);    
    height: 270px;  
}
.product-card .product-info{
    padding: 16px;
}
.product-card .product-info .product-name{
    font-size: x-large;
    font-weight: bold;
}
.product-card .product-info .product-price::before{
    content:'Price : ';
    color:white ;
    font-size: large;
}
.product-card .product-info .product-price::after{
    content:' $';
    color:white ;
}
.product-card .product-info .product-price{
    margin-bottom: 12px;
    color: #EC407A;
}
.product-card .product-info .product-action{
    margin-top: 16px;
    margin-bottom: 12px;

}
.product-card .product-info .product-action button{
    padding: 12px;
    font-size: medium;
    color: white;
    background-color: #37474F;
    border-radius: 4px;

    height: auto;
    border: none;

}
.product-card .product-info .product-action button:hover{
    background-color: #9E9E9E;
}


</style>
