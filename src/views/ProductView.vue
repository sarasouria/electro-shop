<template>

<div class="container-fluid">
  <div class="row justify-content-center">
    <div class="col-lg-8 col-sm-12 m-3">
      <div id="carouselExampleIndicators" class="carousel slide" data-mdb-ride="carousel">
        <div class="carousel-indicators">
          <button
          v-for="(picture,index) in product.pictures" :key="index"
            type="button"
            data-mdb-target="#carouselExampleIndicators"
            :data-mdb-slide-to="index"
            class="active"
            aria-current="true"
            aria-label="Slide 1"
          ></button>
          
        </div>
        <div class="carousel-inner">
          <div v-for="(picture,index) in product.pictures" :key="index" :class="{'carousel-item':true,' active':index===0}">
            <img v-bind:src="picture.path" class="d-block w-100" />
          </div>
        </div>
        <button class="carousel-control-prev" type="button" data-mdb-target="#carouselExampleIndicators" data-mdb-slide="prev">
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button class="carousel-control-next" type="button" data-mdb-target="#carouselExampleIndicators" data-mdb-slide="next">
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </div>
  </div>
</div>


<div class="container mb-3">
    <div class="row justify-content-center">
      <div class="spinner-border" style="width: 3rem; height: 3rem;" role="status" v-if="loading">
              <span class="visually-hidden">Loading...</span>
      </div> 
      <h1>{{product.name}}</h1>
      <h3>{{product.description}}</h3>
      <p>{{product.details}}</p>
      <h6>{{product.price}}</h6>
    </div>
</div>
</template>
<script>
import axios from 'axios';
export default {
    data(){
        return{
            product:{},
            loading:false
        }
    },
    created()
    {
        this.loading=true;
        axios.get("https://matjar-simple.000webhostapp.com/api/product/"+this.$route.params.id).then((response)=>{
            this.product=response.data.product;
        }).catch((error)=>{
            alert(error);
        }).finally(()=>{           
            this.product.pictures.forEach(picture=>{
                picture.path="https://matjar-simple.000webhostapp.com/"+picture.path;
            });                               
            this.loading=false;            
        });
    }
}
</script>