# Sistema-PALC-9000
O projeto simula um jogo de Pokémon Go, utilizando conceitos de Física e ferramentas básicas em Python. O objetivo é mostrar a trajetória da Pokebola por meio de uma matriz e, assim, identificar se o Pokémon foi ou não capturado.

Para isso, o código utiliza arquivos e listas de listas (matrizes em Python). 
Primeiro, o programa lê as dimensões de uma matriz m por n (em metros) e as características dos Pokémons
presentes nela a partir de um arquivo texto (.txt) com todas as informações. 

A matriz representa um plano em que o eixo x corresponde à distância e o eixo y, à altura.
O programa deverá popular a matriz (cada índice correspondente a um metro) de acordo com a posição e raio dos Pokémons, bem como guardar as características deles em uma lista. Em seguida, receberá do usuário a quantidade de Pokebolas disponíveis. Enquanto houver Pokebolas e Pokémons livres, lerá as entradas do usuário em relação à velocidade (em m/s) e ângulo (em graus) referentes ao lançamento. 

O lançamento deverá produzir uma representação gráfica matricial, indicando por pontos os locais em que a Pokebola passou. Ao
capturar um Pokémon, o programa irá imprimir qual Pokémon foi capturado. Se não houve captura, irá informar que o lançamento não capturou Pokémon algum.

Finalmente, o programa imprime uma mensagem referente ao motivo pelo qual se encerrou (nenhuma Pokebola ou nenhum Pokémon livre disponíveis).

Este projeto foi entregue em janeiro de 2021 como avaliação final da disciplina MAC0115 do curso Física Bacharelado.

## Arquivos .txt utilizados

<p>
Dados da entrada1.txt: <br />
15 40 <br />
Pidgey 0 22 7 <br />
</p>
<p>
Dados da entrada2.txt:<br />
10 10<br />
Nidoran 1 4 5<br />
</p>
<p>
Dados da entrada3.txt:<br />
15 30<br />
Quilava 2 9 8<br />
</p>
<p>
Dados da entrada4.txt:<br />
15 32<br />
Nidoran 1 14 13<br />
Pidgey 0 25 10<br />
Quilava 2 9 12<br />
</p>
<p>
Dados da entrada5.txt:<br />
25 60<br />
Nidoran 1 14 23<br />
Pidgey 0 55 14<br />
Quilava 2 9 22<br />
Rayquaza 4 30 8<br />
</p>
<p>
Dados da entrada6.txt:<br />
12 15<br />
Nidoran 1 4 9<br />
Quilava 2 3 4<br />
Rayquaza 3 10 5<br />
</p>

## Exemplos

Jogada 1:

<div align="center">
    <img src="https://github.com/natalia-mvieira/Sistema-PALC-9000/assets/144560412/eebadb7e-41a7-4a62-a452-b6a5c4da9c2b" width="400px"/>
</div>



Jogada 2:

<div align="center">
    <img src="https://github.com/natalia-mvieira/Sistema-PALC-9000/assets/144560412/f47e7298-f40a-451e-81ac-0595f7bbcd0a" width="400px"/>
</div>


