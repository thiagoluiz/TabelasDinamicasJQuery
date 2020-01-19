# Tabelas Dinâmicas com JQUERY#
Exemplo de como criar um Table Html dinamicamente utilizando JQUERY

## Proposta
Criar uma matriz estilo excel e depois preencher algumas colunas dinamicamente


# [Tables com JQuery](#)

## Primeiramente defini o título das colunas
```javascript
    $( document ).ready(function() {
	   var numeroLinhas   = 10;
	   var numeroColunas  = 7;	   
	   var letrasAlfabeto = ['A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P','Q','R','S','T','U','V','X','Z'];	   
	   var html = "<table id='tbl' class='table table-striped'>";
	   var numeroLinha = 1;	   
	   var nomeColuna = "";	   
	   //vai criar as colunas
	   
	   html = html + "<thead class='thead-dark'>" ;
	   html = html + "<tr>";	   
	   for (z = 0; z < numeroColunas; z++)
	   {
	      nomeColuna = letrasAlfabeto[z];
		  html = html + "<th>" +nomeColuna+ "</th>"; 	
	   }
       html = html + "</tr>";	   
	   
       html = html + "</thead>";	   
```
No Exemplo acima, foi criado o titulo das colunas, para isso criei um array do alfabeto para definir o nome de cada coluna


## Montando os Campos dinamicamente#

Criaremos os campos de acordo com a quantidade de colunas e linhas definidas

```javascript
  html = html + "<tbody>";	   	   
	   
	   
       nomeColuna = "";	   	   
	   for (x=0; x < numeroLinhas; x++)
	   {	   	  	  
	      html = html + "<tr >"; 				 	 
	      for (i=0; i < numeroColunas; i++)
	      {
		    nomeColuna =  letrasAlfabeto[i] + numeroLinha;
	        html = html + "<td id='" + nomeColuna + "'>-</td>";
	      }
          html = html + "</tr> ";				   	   	 
		  numeroLinha = numeroLinha + 1;	
       }
       html = html + "</tbody>";

```

## Setando valor a uma célula#

Com os campos criados, agora podemos setar o valor da coluna e linha que quisermos. No exemplo abaixo, alterei o valor das linhas A1 e E5

```javascript
	   $("#A1").text("ALTEREI DINAMICO");
     $("#E5").text("ALTEREI DINAMICO");	 

```


