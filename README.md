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

##Arquivos .txt utilizados

Dados da entrada1.txt:
15 40
Pidgey 0 22 7

Dados da entrada2.txt:
10 10
Nidoran 1 4 5

Dados da entrada3.txt:
15 30
Quilava 2 9 8

Dados da entrada4.txt:
15 32
Nidoran 1 14 13
Pidgey 0 25 10
Quilava 2 9 12

Dados da entrada5.txt:
25 60
Nidoran 1 14 23
Pidgey 0 55 14
Quilava 2 9 22
Rayquaza 4 30 8

Dados da entrada6.txt:
12 15
Nidoran 1 4 9
Quilava 2 3 4
Rayquaza 3 10 5

##Exemplos>





