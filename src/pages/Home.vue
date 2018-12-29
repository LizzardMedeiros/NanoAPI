<template>
	<div>
	    <div class="main-container">
	      <div class="container">
	        <img class="responsive-img" src="/static/img/nano.png"/>
	        <hr>
	        <h5 class="text-white">{{msg}}</h5>
	      </div>
	    </div>
	    <tutorial/>
	    <documentation/>
	    <donate/>
	    <footer/>
	</div>
</template>

<script>
import Tutorial from '@/pages/Tutorial';
import Documentation from '@/pages/Documentation';
import Donate from '@/pages/Donate';
import Footer from '@/pages/Footer';

export default {
  name: 'Home',
  components:{
  	Tutorial,
  	Documentation,
  	Donate,
  	Footer
  },
  data () {
    return {
      msg: 'Nano API - Ferramentas para desenvolvedores'
    }
  }
}
</script>
<style scoped>
	.container{
		padding: 5.6rem 0;
	}
	.main-container{
		background-image: linear-gradient(to bottom right, #0f6bff, #80acf2);
	}
	.main-container hr{
	  margin: 3rem 0;
	  border-color: #64b5f6;
	}
	h4{
		font-size: 1rem;
	}
	.main-container .responsive-img{
	  width: 196px;
	}
	@media (min-width: 992px) {
		.main-container .responsive-img{
		  width: 256px;
		}
		h4{
			font-size: 2rem;
		}
	}
</style>
