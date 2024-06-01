import random

jogador1 = str(input("Nome do jogador 1: "))
jogador2 = str('MESA')
valor1 = None
valor2 = None
soma = None

def distr_valores():
    global valor1, valor2
    valor1 = random.randint(1, 11)
    valor2 = random.randint(1, 11)
    soma = valor1 + valor2
    return soma

valores_jogador1 = distr_valores()

while valores_jogador1 < 21:
    print("A soma das cartas de {} é: {}".format(jogador1, valores_jogador1))
    if valores_jogador1 == 21:
        print("Parabéns {} você ganhou!!".format(jogador1))
        break
    elif valores_jogador1 > 21:
        print("VOCÊ ESTOUROU!!".format(jogador1))
        break
    else:
        print("\nO jogador {} deseja mais uma carta?".format(jogador1))
        resposta = str(input("Digite 'S' para sim ou 'N' para não: ")).lower()
    while resposta != 's' and resposta != 'n':
        print("\nOPSSSS, DIGITE APENAS 'S' OU 'N'!!!")
        resposta = str(input("Digite 'S' para sim ou 'N' para não: ")).lower()
    
    #JOGADOR VAI PEDIR MAIS UMA CARTA
    if resposta == 's':
        carta1 = random.randint(1, 11)
        valores_jogador1 += carta1
        if valores_jogador1 < 21:
            print("\nA carta sorteada foi um {}!!".format(carta1))
            continue
        elif valores_jogador1 == 21:
            print("\nA carta sorteada foi um {}!!".format(carta1))
            print("BLACKJACK!! VOCÊ FEZ 21!!")
            break
        else:
            print("\nA carta sorteada foi um {}!!".format(carta1))
            print("A soma das cartas de {} é: {}".format(jogador1, valores_jogador1))
            print("\nVOCÊ ESTOUROU!!".format(jogador1))
            break
    elif resposta == 'n':
        print("Você ficou com o valor final de: {}".format(valores_jogador1))
        break
    
print("-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=--=-")
print('''\nAGORA É A RODADA DA MESA\n''')
print("-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=--=-")

valores_jogador2 = distr_valores()

while valores_jogador2   < 21:
    print("A soma das cartas de {} é: {}".format(jogador2, valores_jogador2))
    if valores_jogador2 == 21:
        print("Parabéns {} você ganhou!!".format(jogador2))
        break
    elif valores_jogador2 > 21:
        print("VOCÊ ESTOUROU!!".format(jogador2))
        break
    else:
        print("\nO jogador {} deseja mais uma carta?".format(jogador2))
        resposta = str(input("Digite 'S' para sim ou 'N' para não: ")).lower()
    while resposta != 's' and resposta != 'n':
        print("\nOPSSSS, DIGITE APENAS 'S' OU 'N'!!!")
        resposta = str(input("Digite 'S' para sim ou 'N' para não: ")).lower()
    
    #JOGADOR VAI PEDIR MAIS UMA CARTA
    if resposta == 's':
        carta1 = random.randint(1, 11)
        valores_jogador2 += carta1
        if valores_jogador2 < 21:
            print("\nA carta sorteada foi um {}!!".format(carta1))
            continue
        elif valores_jogador2 == 21:
            print("\nA carta sorteada foi um {}!!".format(carta1))
            print("BLACKJACK!! VOCÊ FEZ 21!!")
            break
        else:
            print("\nA carta sorteada foi um {}!!".format(carta1))
            print("A soma das cartas de {} é: {}".format(jogador2, valores_jogador2))
            print("\nVOCÊ ESTOUROU!!".format(jogador2))
            break
    elif resposta == 'n':
        print("\nVocê ficou com o valor final de: {}".format(valores_jogador2))
        break
    
if valores_jogador1 > valores_jogador2 and valores_jogador1 < 21:
    print("\nParabéns {} você GANHOU!!".format(jogador1))
elif valores_jogador2 > valores_jogador1 and valores_jogador2 < 21:
    print("\nParabéns {} você GANHOU!!".format(jogador2))
elif valores_jogador1 > 21 and valores_jogador2 <= 21:
    print("\nParabéns {} você GANHOU!!".format(jogador2))
elif valores_jogador2 > 21 and valores_jogador1 <= 21:
    print("\nParabéns {} você GANHOU!!".format(jogador1))
elif valores_jogador1 > 21 and valores_jogador2 > 21:
    print("\nOS DOIS ESTOURARAM, QUE PENA!!!")
elif valores_jogador1 and valores_jogador2 == 21:
    print("\nOS DOIS FIZERAM BLACKJACK, EMPATARAM BONITO!!!")
elif valores_jogador1 == valores_jogador2 and valores_jogador1 and valores_jogador2 < 22:
    print("\n-=-=-=-EMPATE-=-=-=-!!")
    
def reiniciar_partida():
    input("VOCÊ QUER REINICAR A PARTIDA? [S/N]").upper()
    if resposta == 'S':
        print("-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=--=-")
        print("\nREINICIANDO A PARTIDA...")
        print("-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=--=-")
        distr_valores()
    elif resposta == 'N':
        print("\nENCERRANDO O JOGO...")
    else:
        print("\nOPÇÃO INVÁLIDA. DIGITE 'S' PARA SIM OU 'N' PARA NÃO.")
        reiniciar_partida()
