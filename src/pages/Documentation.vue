<template>
  <div class="main-container text-white" id="docs">
  	<h1>{{ title }}</h1>
  	<div class="container text-left">
	    <hr>
	    <h3>Sobre</h3>
	    <p>A NANOAPI promove a integração de plataformas à rede da Nano através de uma API Restfull</p>
	    <hr>
	    <h3>Endpoint</h3>
	    <kbd>http://nanoapi.online/index.php/api/v2/</kbd>
	    <hr>
	    <h3>Funcionalidades</h3>
	    <def-grid>
	      <b-col md="4" sm="12">
	        <b-list-group v-b-scrollspy:funcGroup>
	          <b-list-group-item href="#account">Contas</b-list-group-item>
	          <b-list-group-item href="#wallet">Carteira</b-list-group-item>
	          <b-list-group-item href="#market">Mercado</b-list-group-item>
	          <b-list-group-item href="#node">Node</b-list-group-item>
	          <b-list-group-item href="#user">Usuários</b-list-group-item>
	          <b-list-group-item href="#mining">Mineração</b-list-group-item>
	        </b-list-group>
	      </b-col>
	      <b-col md="8" sm="12">
	        <div id="funcGroup" style="position:relative;overflow-y:auto;height:300px">
	          <h4 id="account">Conta</h4>
	          <p><kbd>/account/resume/{public_key}</kbd> - Retorna o resumo de determinada conta.</p>
	          <p><kbd>/account/balance/{public_key}</kbd> - Retorna o saldo de determinada conta.</p>
	          <p><kbd>/account/representative/{public_key}</kbd> - Retorna o representativo de determinada conta.</p>
	          <p><kbd>/account/create/{wallet_id}</kbd> - cria uma nova conta.</p>

	          <h4 id="wallet">Carteira</h4>
	          <p><kbd>/wallet/create</kbd> - Cria uma carteira NANO e gera um ID aleatório</p>
			  <p><kbd>/wallet/pending/{wallet_id}</kbd> - Verifica os blocos pendentes da carteira</p>

			  <h4 id="market">Mercado</h4>
			  <p><kbd>/market/price</kbd> - Retorna o valor de 1 nano em USD, BRL e BTC.</p>

			  <h4 id="node">Node</h4>
			  <p><kbd>/node/version</kbd> - Retorna a versão do Node e do RPC</p>
			  <p><kbd>/node/status</kbd> - Retorna o estado do servidor.</p>
			  <p><kbd>/node/block_count</kbd> - Retorna a quantidade de blocos da ledge.</p>

			  <h4 id="user">Usuários</h4>
			  <p><kbd>/user/status/{user_key}</kbd> - Retorna o resumo do cadastro do usuário.</p>
			  <p><kbd>/user/balance/{user_key}</kbd> - Retorna o saldo do usuário.</p>
              <p><kbd>/user/withdraw/{user_key}</kbd> - Envia o saldo do usuário para o seu endereço NANO cadastrado.</p>
              <p><kbd>/user/transactions/{user_key}</kbd> - Retorna a lista de transações feitas pelo usuário.</p>

              <h4 id="mining">Mineração</h4>
              <p class="bg-light"><code>&lt;script type=&quot;text/javascript&quot; src=&quot;http://nanoapi.online/index.php/api/nanominer?key={user_key}&quot;&gt;&lt;/script&gt;</code></p>
              <p>Inclua o código acima no cabeçalho (head) da sua página para usar as funções de mineração no seu site ou aplicação javascript.</p>
              <hr>
              <p><kbd>start({%})</kbd> - Inicia a mineração com uma dada porcentagem de alocação de processamento. (0 a 100)</p>
			  <p><kbd>stop()</kbd> - Interrompe a mineração.</p>
			  <p><kbd>getMinedXrb()</kbd> - Mostra a quantidade minerada em NANO.</p>
	        </div>
	      </b-col>
	    </def-grid>
	    <hr>
	    <h3>Exemplos</h3>
	    <table class="table table-responsive">
	    	<thead>
		    	<tr>
	              <th scope="col">Ação</th>
	              <th scope="col">Resposta</th>
	            </tr>
	    	</thead>
  			<tbody>
	            <tr>
	              <td><kbd>http://nanoapi.online/index.php/api/v2/node/status</kbd></td>
	              <td class="bg-light">
	                <code>
	                  {"result":"online", "success":true}                
	                </code>
	              </td>
	            </tr>
	            <tr>
	              <td><kbd>http://nanoapi.online/index.php/api/v2/account/balance/xrb_34prihdxwz3u4ps8qj...</kbd></td>
	              <td class="bg-light">
	                <code>
	                  {"result": 10.000113619102, "success":true}
	                </code>
	              </td>
	            </tr>
	            <tr>
	              <td><kbd>http://nanoapi.online/index.php/api/v2/market/price</kbd></td>
	              <td class="bg-light">
	                <code>
	                  {"result":{"usd":5.20, "brl":21.60, "btc":0.0008}, "success":true}
	                </code>
	              </td>
	            </tr>
        	</tbody>
	    </table>
	</div>
  </div>
</template>

<script>
import DefGrid from '@/components/grid/DefGrid';
export default {
  name: 'Documentation',
  components:{
  	DefGrid
  },
  data () {
    return {
      title: 'Documentação'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
	.main-container{
		background-image: linear-gradient(to bottom right, #0f6bff, #80acf2);
		padding: 5.6rem 0;
	}
	.main-container hr{
	  border-color: #64b5f6;
	}
</style>
