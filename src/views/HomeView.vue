<script setup>
// import TheWelcome from '../components/TheWelcome.vue'


</script>

<template>
  <main>
    <header>
        <div class="header-content">          
                <h1>Welcome to Electro Shop</h1>
                <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Delectus rerum quis, natus,
                  dolorem vel est qui minus ipsam esse, ad voluptatem quisquam labore possimus similique 
                  fugiat unde! Eius, adipisci molestiae.</p>
                  <RouterLink to="/gallery" class="gallery-link">Navigate Gallery ...</RouterLink>
      
        </div>

    </header>
    <section id="categories">     
      <div class="container">
        <h1>Our products categories</h1><br >
        <div class="row">
          <div class="col-lg-3 col-md-6 col-sm-12">
            <div class="category">
              <RouterLink to="/category/2" >
                <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" fill="currentColor" class="bi bi-phone" viewBox="0 0 16 16">
                <path d="M11 1a1 1 0 0 1 1 1v12a1 1 0 0 1-1 1H5a1 1 0 0 1-1-1V2a1 1 0 0 1 1-1h6zM5 0a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h6a2 2 0 0 0 2-2V2a2 2 0 0 0-2-2H5z"/>
                <path d="M8 14a1 1 0 1 0 0-2 1 1 0 0 0 0 2z"/>
              </svg>
              Mobiles
            </RouterLink>                      
            </div>
          </div>

          <div class="col-lg-3 col-md-6 col-sm-12">
            <div class="category">
              <RouterLink to="/category/1" >
                <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" fill="currentColor" class="bi bi-laptop" viewBox="0 0 16 16">
                  <path d="M13.5 3a.5.5 0 0 1 .5.5V11H2V3.5a.5.5 0 0 1 .5-.5h11zm-11-1A1.5 1.5 0 0 0 1 3.5V12h14V3.5A1.5 1.5 0 0 0 13.5 2h-11zM0 12.5h16a1.5 1.5 0 0 1-1.5 1.5h-13A1.5 1.5 0 0 1 0 12.5z"/>
                </svg>
                Laptops
              </RouterLink>                
            </div>
          </div>

          <div class="col-lg-3 col-md-6 col-sm-12">
            <div class="category">
              <RouterLink to="/category/1" >
                <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" fill="currentColor" class="bi bi-tablet-landscape" viewBox="0 0 16 16">
                  <path d="M1 4a1 1 0 0 1 1-1h12a1 1 0 0 1 1 1v8a1 1 0 0 1-1 1H2a1 1 0 0 1-1-1V4zm-1 8a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V4a2 2 0 0 0-2-2H2a2 2 0 0 0-2 2v8z"/>
                  <path d="M14 8a1 1 0 1 0-2 0 1 1 0 0 0 2 0z"/>
                </svg>
                Tablets
              </RouterLink>
            </div>
          </div>

          <div class="col-lg-3 col-md-6 col-sm-12">
            <div class="category">
              <a href="#">
                <svg xmlns="http://www.w3.org/2000/svg" width="64" height="64" fill="currentColor" class="bi bi-pc" viewBox="0 0 16 16">
                  <path d="M5 0a1 1 0 0 0-1 1v14a1 1 0 0 0 1 1h6a1 1 0 0 0 1-1V1a1 1 0 0 0-1-1H5Zm.5 14a.5.5 0 1 1 0 1 .5.5 0 0 1 0-1Zm2 0a.5.5 0 1 1 0 1 .5.5 0 0 1 0-1ZM5 1.5a.5.5 0 0 1 .5-.5h5a.5.5 0 0 1 0 1h-5a.5.5 0 0 1-.5-.5ZM5.5 3h5a.5.5 0 0 1 0 1h-5a.5.5 0 0 1 0-1Z"/>
                </svg>
                Pcs
              </a>             
            </div>
          </div>

        </div>
      </div>

    </section>

    <section id="about-us">
      <div class="container">
        <div class="row">
          <div class="col-lg-4 col-md-6 col-sm-12">
              <h2>Who we are</h2>
              <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum architecto pariatur assumenda eos, amet quaerat, suscipit error nobis, porro doloribus eveniet fugiat velit est commodi? Aperiam reiciendis omnis delectus hic.</p>
          </div>
        </div>
      </div>
    </section>
    
  </main>
</template>



<style>

header{
  height:100vh;
  background-image: url("https://images.pexels.com/photos/3760263/pexels-photo-3760263.jpeg?auto=compress&cs=tinysrgb&dpr=1");
  background-size: cover;
  color: white;
  opacity:0.5;
  position: relative;
  text-align: center;

}
.header-content{
position:absolute;
top: 40%;
text-align: center;
margin-right: 200px;
margin-left: 200px;
}
.gallery-link{
  background-color: #2196F3;
  color: white;
  border: none;
  border-radius: 8px;
  font-size: large;
  stop-opacity: unset;
  padding: 12px;
}
.gallery-link:hover{
  background-color: #90CAF9;
}

#categories{
  background-color: #2196F3;
  color:white;
  padding: 32px;
}

.category{
  background-color: #FAFAFA;
  color: #2196F3;
  border-radius: 8px;
  padding: 16px;
  margin-top: 16px;
  cursor: pointer;
  transition: all 0.5s ease;
}

.category:hover{
  color: #90CAF9;
  transform: scale(1.2, 1.2);
  margin-left: 24px;
  margin-top: 12px;

}

#about-us{
  background-color: #FFB300;
  color: white;
  padding: 32px;
}


@media screen and (max-width: 600px) {
  .header-content{
    margin-right: auto;
    margin-left: auto;
  }
}

</style>
