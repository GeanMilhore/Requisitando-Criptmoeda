# Informa��es CriptoMoedas :chart:

### Tecnologias utilizadas:	:dollar: CoinMarketCap API, :yellow_square: JavaScript , :orange_square: HTML & :blue_square: CSS

O Projeto tem como objetivo a busca de informa��es sobre as principais criptomoedas <br> do mundo, utilizando __*javaScript*__ e os objetos *promises*. 

## Visual do Projeto

!["visual-main"](/code/img/Readme/Main-photo.png "Visual p�gina")

as __*divs*__, s�o feitas atrav�s de um ``` .then() ``` que ap�s a requisi��o do __json()__ da API <br> faz com que as informa��es sejam passadas para ```div#coin```.

### Modelo da DIV em que s�o passadas as informa��es.
```

<div class="media">
    <img src="./img/${api.data[i].name}.png" height="60" width="70">
    <div class="media-body">
        <h5>${api.data[i].name}</h5>
    </div>
</div>           
                        
```

## Mostrando informa��es.

!["info-moeda"](/code/img/Readme/info-photo.png "Informa��es Moeda")

ap�s o clicar em qualquer uma das moedas uma tela de informa��es ir� descer<br> informando o nome, sigla e sua primeira data hist�rica, isso foi implementado <br> utilizando um ```EventListener```  e um ```for()``` como vemos abaixo.


```
.then((api) =>{
        
    const divMoedas = document.getElementsByClassName('media')

    for (let i = 0; i < divMoedas.length; i++){
            divMoedas[i].addEventListener('click', function(){
                expPop('info-moeda', api.data[i].name, api.data[i].first_historical_data.split('T')[0], api.data[i].symbol )
            })
    }


```
O c�digo acima adiciona como evento em cada __div__ com informa��es um evento de <br> escuta para que ao clicarmos chame a fun��o __*exPop*()__ sejam apresentadas as <br>informa��es sobre aquela moeda.
## ( Projeto implementado durante uma aula na Digital Innovation One :pencil2: ) 
