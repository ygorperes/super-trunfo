import random

class Carta:
    def __init__(self, nome, populacao, area, pib):
        self.nome = nome
        self.populacao = populacao
        self.area = area
        self.pib = pib

    def __str__(self):
        return f"{self.nome} | População: {self.populacao} | Área: {self.area} km² | PIB: {self.pib} bilhões"

# Definindo as cartas de cidades
cidades = [
    Carta("São Paulo", 12325232, 1521, 721.2),
    Carta("Rio de Janeiro", 6748000, 1182, 428.5),
    Carta("Belo Horizonte", 2521564, 331, 124.3),
    Carta("Brasília", 3055149, 5802, 122.7),
    Carta("Salvador", 2886698, 693, 160.5)
]

# Função para escolher uma carta aleatória
def escolher_carta():
    return random.choice(cidades)

# Função para jogar o Super Trunfo
def jogar():
    print("Bem-vindo ao Super Trunfo - Cartas de Cidades!\n")
    print("Escolha um atributo para comparar:")
    print("1. População")
    print("2. Área")
    print("3. PIB")

    escolha = input("Digite o número do atributo escolhido (1, 2 ou 3): ")

    if escolha not in ["1", "2", "3"]:
        print("Opção inválida! Por favor, escolha um número entre 1, 2 ou 3.")
        return
    
    carta_jogador1 = escolher_carta()
    carta_jogador2 = escolher_carta()

    print("\nJogador 1 escolheu:", carta_jogador1)
    print("Jogador 2 escolheu:", carta_jogador2)

    if escolha == "1":
        if carta_jogador1.populacao > carta_jogador2.populacao:
            print("Jogador 1 ganha a rodada!")
        elif carta_jogador1.populacao < carta_jogador2.populacao:
            print("Jogador 2 ganha a rodada!")
        else:
            print("Empate!")
    elif escolha == "2":
        if carta_jogador1.area > carta_jogador2.area:
            print("Jogador 1 ganha a rodada!")
        elif carta_jogador1.area < carta_jogador2.area:
            print("Jogador 2 ganha a rodada!")
        else:
            print("Empate!")
    elif escolha == "3":
        if carta_jogador1.pib > carta_jogador2.pib:
            print("Jogador 1 ganha a rodada!")
        elif carta_jogador1.pib < carta_jogador2.pib:
            print("Jogador 2 ganha a rodada!")
        else:
            print("Empate!")

# Iniciar o jogo
jogar()

