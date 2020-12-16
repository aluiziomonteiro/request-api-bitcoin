#  Requisição em uma API de Criptomoedas
___
___

### Objetivos
 * Fazer uma requisição de uma API de Bitcoins.
 * Manipular os valores da API.
 * Exibir os dados em uma página web
 
### Requisitos
 * VS Code.
 * extensão do chrome [Moesif Orign & CORS Changer](https://chrome.google.com/webstore/detail/moesif-origin-cors-change/digfbfaphojjndkpccljibejjbppifbc/related?hl=pt-BR&authuser=1)
 
 * Conta de desenvolvedor na CoinMarketCap.
 1 - Acesse: [http://pro.coinmarketcap.com/account](http://pro.coinmarketcap.com/account/)
 2 - Clique em: GET an a API Key now.
 3 - Copie a key.
 ___

### HTML.
###### Esqueleto

...

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CoinMarketCap</title>
</head>
<body>
    <script type="text/javascript"></script>
</body>
</html>

...
 
### FETCH
###### Método do js que permite a execução dos verbos da RestAPI.

 * Método que consegue fazer as requisições.
 * Sempre dentro da tag ... <script> </script>. ...
 * É importante tratar os erros.
 	* "responde.ok" = 200
 	* "response.error" = 400, 404...
 
* A API será exibida pelo "console.log(api)"

...

    <script type="text/javascript">
    // My api key
        var apikey = {
            key: 'SUA API KEY VEM AQUI :)'
        }
    // GET Fetch Requisition - URI que fará a nossa requisição
    fetch('https://pro.coinmarketcap.com/v1/cryptocurrency/map?CMC_PRO_API_KEY=' +
    apikey.key)
    .then((response) => { // tratamento de erro
        if(!response.ok) throw new Error('Erro ao executar a requisição, status ' + response.status);
    })
    .then((api) => { // Aqui acontece a requisição
        console.log(api); // A resposta da requisição vem por aqui
    })
    .catch((error) => { // Exibição da mensagem de possível erro
        console.log(error.message);
    });

    </script>
    ...

* Ative a extensão.
* Abra o index.html e nas ferramentas do desenvolvedor, deverá ser possível visualizar a lista de dados das moedas.

___


























