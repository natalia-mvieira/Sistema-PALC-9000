import math

DELTA_T = 0.1
GRAVIDADE = 2

def leArquivo(nomeArquivo = 'entrada.txt'):
    '''
    Esta função lê um arquivo ('entrada.txt' por default) e
    retorna uma lista de listas.
    Entrada: arquivo cujo nome está armazenado em nomeArquivo.
             Por default, é 'entrada.txt'
    Saída: uma lista de listas, onde o primeiro elemento é uma
           lista de inteiros [m, n] (dimensões da matriz) e os
           elementos subsequentes são listas que representam as
           característica lidas dos Pokémons na forma:
                [nome, raio, x, y]
    '''
    lista = []
    with open(nomeArquivo) as arquivo:
        arqv = arquivo.read()
    a = arqv.split(sep='\n')
    for i in a:
        b = i.split()
        lista.append(b)
    return lista


def criaMatriz(m, n):
    '''
    Esta função cria e retorna uma lista de listas.
    Entrada: dois inteiros que representam o número de linhas e
             o número de colunas da matriz.
    Saída: uma lista de m listas, cada uma com n elementos, todos
           inicializados com zeros.
    '''
    lista = []
    for i in range(m):
        linha = []
        for j in range(n):
            linha.append(0)
        lista.append(linha)
    return lista


def populaMatriz(matriz, pokemons):
    '''
    Esta função recebe uma matriz e uma lista contendo listas que
    representam os pokémons na forma [nome, raio, x, y] e preenche-a
    os pokémons conforme a representação retangular considerando os
    raios da representação.
    Entrada: matriz representada por uma lista de listas
    Saída: A matriz fornecida é modificada.
    '''
    mat = copiaMatriz(matriz)
    ordem = 0 #posição do pokemon na lista, será o id
    for i in pokemons:
        l = []
        c = []
        linha = int(i[3]) 
        coluna =int(i[2]) 
        raio = int(i[1])
        ordem = ordem +1 
        for i in range((linha-raio), (linha+raio+1)):
            if i<len(mat) and i>=0:                
                l.append(i)
        for i in range((coluna-raio), (coluna+raio+1)):
            if i<len(mat[0]) and i>=0:
                c.append(i)
        for i in l:
            for j in c:
                mat[i][j] = ordem              
    return mat


def preenchePokemon(matriz, id, x, y, raio):
    '''
    Esta função é auxiliar da função populaMatriz. Ela insere
    um Pokémon na matriz de acordo com sua representação retangular
    baseada no raio ao redor do ponto central (x,y)
    Entrada: matriz representada por uma lista de listas
             id é o número a preencher a matriz; para o
             primeiro pokémon na lista (de índice zero),
             usa-se 1 e assim subsequentemente.
             x,y são as coordenadas do ponto central
             raio é a distância a ser guardada a partir do
             ponto central.
    Saída: A matriz fornecida é modificada.
    '''
    
    ''' não utilizei'''
    return None


def removePokemon(matriz, id, pokemons):
    '''
    Esta função recebe uma matriz, o numeral que representa o pokémon
    a ser removido da matriz (id) e a lista contendo as listas que
    representam pokémons, substituindo os numerais id por zero
    Entrada: matriz representada por uma lista de listas;
             id é o número a preencher a matriz, para o
             primeiro pokémon na lista (de índice zero),
             usa-se 1 e assim subsequentemente;
             pokemons lista contendo as listas que representam pokémons.
    Saída: A matriz fornecida é modificada.
    '''
    l = []
    c = []
    linha = int(pokemons[id][3])
    coluna = int(pokemons[id][2]) 
    raio = int(pokemons[id][1])
    for i in range((linha-raio), (linha+raio+1)):
        if i<len(matriz) and i>=0:                
                l.append(i)
        for i in range((coluna-raio), (coluna+raio+1)):
            if i<len(matriz[0]) and i>=0:
                c.append(i)
        for i in l:
            for j in c:
                if matriz[i][j] == id:
                    matriz[i][j] = 0
    return matriz
   
def imprimeMatriz(matriz):
    '''
    Esta função imprime a matriz dada.
    Note que a matriz deve ser impressa com espelhamento vertical, 
    pois a primeira linha representa o chão.
    Entrada: matriz representada por uma lista de listas.
    '''
    A = []
    copia = copiaMatriz(matriz)
    for i in range(len(copia)):
        for j in range(len(copia[0])):
            if copia[i][j] == 0:
                copia[i][j]= "."
    j = len(copia)-1 
    for i in range(len(copia)): #1,2,3
        A.append(copia[j]) 
        j = j-1
        
    for i in range(len(A)):
        for j in range(len(A[0])):
            print(A[i][j], end='')
        print()

def atualizaPosicao(x, y, vx, vy, dt=DELTA_T):
    '''
    Esta função calcula as atualizações das posições de x e y usando
    as velocidades escalares respectivamente dadas por vx e vy.
    Entrada: As posições x e y dadas em metros, as velocidades vx e
    vy em metros por segundo e o intervalo de tempo em segundos.
    Saída: Dois valores: o valor atualizado de x e o valor atualizado de y.
    '''
    xb = x
    yb = y
    v_x = vx
    v_y = vy
    yb = yb + v_y*dt - (GRAVIDADE*dt**2)/2
    xb = xb + v_x*dt
    x_atual = xb 
    y_atual = yb 
    return x_atual,y_atual


def atualizaVelocidade(vx, vy, dt=DELTA_T):
    '''
    Esta função calcula e atualiza as velocidades vx e vy para o
    próximo intervalo de tempo.
    Entrada: As velocidades vx e vy em metros por segundo e o
    intervalo de tempo em segundos.
    Saída: Dois valores: o valor atualizado de vx e o valor atualizado de vy.
    '''
    vy = vy - GRAVIDADE*dt
    vx_atual = vx #como não há aceleração na direção x, a componente x da velocidade é constante
    vy_atual = vy
    return vx_atual, vy_atual


def grau2Radiano(theta):
    '''
    Esta função converte o ângulo theta em graus para radianos.
    Entrada: ângulo theta.
    Saída: ângulo theta em radianos.
    '''
    a = theta*(math.pi)/180 
    return a

def copiaMatriz(matriz):
    '''
    Gera outro objeto, mas com mesmos elementos da "matriz".
    Entrada: matriz que se quer copiar.
    Saída: nova matriz
    '''
    M = []
    for i in range(len(matriz)):
        copia = []
        for j in matriz[i]:
            copia.append(j)
        M.append(copia)
    return M

def quandocaptura(lista,id):
    '''
    Exclui dados do pokemon capturado da lista proveniente do arquivo e copia restante dos dados em nova lista L.
    Entrada: "lista" com dados dos pokemons e id do pokemon a ser retirado
    Saída: nova lista
    '''
    L = []
    for i in range(len(lista)):
        if i != id:
            copia = []
            for j in lista[i]:
                copia.append(j)
            L.append(copia)
    return L

def main():
    nomearq = leArquivo(str(input("Digite o nome do arquivo: "))) #lista com dados do arquivo, cada linha um elemento da lista
    N = int(input(" Digite o numero N de pokebolas:"))
    x_treinador = int(input("Digite a coordenada x do treinador:"))
    print("pokebolas disponiveis = ", N)
    infomatriz = criaMatriz(int(nomearq[0][0]),int(nomearq[0][1])) #nomearq[0] representa a lista contendo dados da matriz: nomearq[0][0] é o número de linhas e nomearq[0][1] é o número de colunas
    matrizatual = populaMatriz(infomatriz,nomearq[1:]) #nomearq[1:] seria "pokemons", ou seja, a lista nomearq sem os dados da matriz.
    #"matrizatual" é a matriz contendo os zeros e os pokemons com seus raios
    trajeto = copiaMatriz(matrizatual)
    trajeto[0][x_treinador] = "T" #"trajeto" tem os mesmos elementos que "matrizatual", mas contém o treinador e será modificado ao longo do jogo
    print("Estado atual do jogo:")
    imprimeMatriz(trajeto)
    v_lancamento = int(input("Digite a velocidade de lancamento em m/s:"))
    angulo_lancamento = int(input("Digite o angulo de lancamento em graus:"))
    ang_radiano = grau2Radiano(angulo_lancamento)
    vx = v_lancamento*(math.cos(ang_radiano)) 
    vy = v_lancamento*(math.sin(ang_radiano)) 
    xpokebola = x_treinador #pokebola inicialmente junto com o treinador
    ypokebola = 0 #pokebola inicialmente junto com o treinador
    valor = N #número de tentativas disponíveis, depende da quantidade de pokebolas restantes
    while valor>0:
        valor = valor #garante que "valor" seja atualizado
        posicao = atualizaPosicao(xpokebola, ypokebola, vx, vy, DELTA_T) 
        vatual = atualizaVelocidade(vx, vy,DELTA_T)
        vx = vatual[0] 
        vy = vatual[1] 
        xpokebola = posicao[0] 
        ypokebola = posicao[1] 
        i = round(posicao[1]) #índice da linha em que a pokebola estará
        j = round(posicao[0]) #índice da coluna em que a pokebola estará
        if i<len(matrizatual) and j<len(matrizatual[0]) and i>=0 and j>=0: #se i e j estão dentro dos limites da matriz.
            if i != 0 or j != x_treinador: #se a pokebola não está na mesma posição do treinador (T)
                if matrizatual[i][j] == 0:  #se na posição que a pokebola se encontra não há pokemons
                    trajeto[i][j] = "o" #mostra por onde a bola passou
                elif matrizatual[i][j] > 0: #se encontrou algum pokemon
                    trajeto[i][j] = "o"
                    print("Representacao grafica do lancamento:")
                    imprimeMatriz(trajeto)
                    num = int(matrizatual[i][j]) #identifica qual pokemon foi capturado
                    print("Um ",nomearq[num][0],"foi capturado!")
                    matrizsempokemon = removePokemon(matrizatual,num,nomearq) #retira pokemon capturado da matriz
                    matrizatual = matrizsempokemon #a matriz atualizada
                    nomearq = (quandocaptura(nomearq,num)) #retira pokemon capturado da lista "nomearq"
                    if len(nomearq) == 1: #se restou apenas as informações da matriz em "nomearq", então todos os pokemons foram capturados
                        print("Parabens! Todos pokemons foram capturados")
                        return
                    else:
                        valor = valor -1
                        if valor >0:
                            print("pokebolas disponiveis = ", valor)
                            trajeto = copiaMatriz(matrizatual)
                            trajeto[0][j] = "T" #a matriz atualiza com o treinador, será modificada com a trajetória da pokebola
                            print("Estado atual do jogo:")
                            imprimeMatriz(trajeto)
                            v_lancamento = int(input("Digite a velocidade de lancamento em m/s:"))
                            angulo_lancamento = int(input("Digite o angulo de lancamento em graus:"))
                            ang_radiano = grau2Radiano(angulo_lancamento)
                            vx = v_lancamento*(math.cos(ang_radiano))
                            vy = v_lancamento*(math.sin(ang_radiano))
                            x_treinador = round(posicao[0]) #a posição do treinador em x se torna a mesma de onde ocorreu a captura
                            xpokebola = x_treinador #pokebola começa novamente com treinador
                            ypokebola = 0
                        else:
                            print("Jogo encerrado") #caso não haja mais pokebolas
        elif i<0 or j<0 or j>(len(matrizatual[0]) - 1): #caso a pokebola ultrapasse os limites da matriz
            print("Representacao grafica do lancamento:")
            imprimeMatriz(trajeto)
            print("O lancamento nao capturou pokemon algum")
            valor = valor -1
            if valor == 0:
                print("Jogo encerrado")
                return
            else: #se sobrou pokebolas
                x_treinador = int(input("Digite a coordenada x do treinador:"))
                print("pokebolas disponiveis = ", valor)
                trajeto = copiaMatriz(matrizatual)
                trajeto[0][x_treinador] = "T"
                print("Estado atual do jogo:")
                imprimeMatriz(trajeto)
                v_lancamento = int(input("Digite a velocidade de lancamento em m/s:"))
                angulo_lancamento = int(input("Digite o angulo de lancamento em graus:"))
                ang_radiano = grau2Radiano(angulo_lancamento)
                vx = v_lancamento*(math.cos(ang_radiano))
                vy = v_lancamento*(math.sin(ang_radiano))
                xpokebola = x_treinador 
                ypokebola = 0


main()
