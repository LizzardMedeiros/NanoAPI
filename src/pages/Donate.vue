<template>
	<div class="container" id="donate">
        <h1>{{title}}</h1>
        <hr>
        <img style="width: 256px; padding: 1rem 0;" src="http://nanoapi.online/img/heart-512.png" alt="">
        <div class="card text-center">
          <div class="card-body">
            <h6 class="card-subtitle mb-2 text-muted">Ajude-nos a manter e melhorar nossa API!</h6>
            <p class="card-text">Qualquer quantidade doada será de grande ajuda, precisamos pagar os servidores e ter os incentivos necessários para continuarmos a trabalhar duro!</p>
            <p class="card-text">Endereço: <kbd>{{nano_addr}}</kbd></p>
            <div class="progress" style="height: 40px">
              <div class="progress-bar progress-bar-striped progress-bar-animated" role="progressbar" aria-valuenow="75" aria-valuemin="0" aria-valuemax="100" :style="'width:'+((nano_balance/10)*100)+'%'">
              {{nano_balance}} XRB
              </div>
            </div>
            <p class="text-info">Objetivo - 10 XRB</p>
          </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Donate',
  created: function(){
  	var response = axios
        .get('http://nanoapi.online/index.php/api/v2/account/balance/'+this.nano_addr)
        .then((r) => {
        	this.nano_balance = r.data.result;
        })
        .catch((e) => (console.log(e)));
  },
  data () {
    return {
      title: 'Colabore',
      nano_addr: 'xrb_3qky49n3hootdx8dratgaffw4tx3uznj7pji1whtpcnf98tg95jmgbk5brwa',
      nano_balance: 0
    }
  }
}
</script>

<style scoped>
	.container{
		padding: 5.6rem 0;
	}
</style>
