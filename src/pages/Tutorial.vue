<template>
  <div class="container" id="tuto">
    <h1>{{ title }}</h1>
    <hr>
    <def-grid>
      <b-col md="4" sm="12" v-for="(card, id) in card_array">
        <b-card @click="showModal(id)" :img-src="card.image"
                :title="card.title"
                img-alt="Card image"
                img-top>
            <p class="card-text">{{card.desc}}</p>
        </b-card>
      </b-col>
    </def-grid>

	  <!-- Modal Component -->
	  <b-modal ref="modalDetail" hide-footer :title="card_title" size="lg">
	    <p class="my-4">{{card_desc}}</p>
      <b-btn class="mt-3" variant="outline-primary" block @click="hideModal">Close Me</b-btn>
	  </b-modal>

  </div>
</template>

<script>
import DefGrid from '@/components/grid/DefGrid';
export default {
  name: 'Tutorial',
  components:{
    DefGrid
  },
  methods:{
    showModal (id) {
      this.card_title = this.card_array[id].title;
      this.card_desc = this.card_array[id].desc;
      this.$refs.modalDetail.show();
    },
    hideModal () {
      this.$refs.modalDetail.hide();
    }
  },
  data () {
    return {
      title: 'Tutoriais',
      card_title: '',
      card_desc: '',
      card_array:[
        {
          'title':'tuto1',
          'desc': 'Lorem ipsum dolor sit amet, consectetur adipiscing elit.',
          'image':'http://nanoapi.online/img/portfolio/mobile.jpg'
        }
      ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .container{
    padding: 5.6rem 0;
  }
</style>
