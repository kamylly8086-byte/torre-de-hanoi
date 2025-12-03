# torre-de-hanoi

Implementação do jogo Torre de Hanoi em Python, com interface no terminal. Permite ao usúario jogar movendo os discos, valida os movimentos, exibe as torres e informa quando o jogo é concluido.

 







while True:



        try:

            v = input(mensagem) .strip()

            if v.lower() in ('q', 'quit', 'sair'):

                print("Saindo...")

                sys.exit(0)

            n = int(v)

            if n < mínimo:

                print(f"Digite um número inteiro >= {minimo}."

                continue

            return n

        except ValueErro:

            print("Entrada inválida. Digite um número inteiro ou 'q' para sair.")









def criar jogo(n\_torres, n\_discos):

    #torre 0 começa com discos n\_discos..1 (n\_discos é maior embaixo)

    torres = \[\[] for \_ in range(n\_torres)]

    torres\[0] = list(range(n\_discos, 0, -1)) #maior (n) embaixo até 1 (menor) no topo

    return torres



def mostrar torres(torres, n\_discos):

    n\_torres = len(torres)

    largura\_max\_disc = n\_discos \* 2 + 1

    altura = n\_discos

    # para cada nível do topo para baixo

    for nível in range(altura-1, -1, -1):

        linha = ""

        for t in torres:

            if len(t) - 1 >= nível:

               disco = t\[nivel]

               largura = dsico \* 2 + 1

               pad = (largura\_max\_disc - largura) // 2

               linha += " " \* pad + "(" + "=" \* (largura - 2) + ")" +"" \* pad + " "

           else:

               # mostra o espaço vazio com '|' central

               pad = (largura\_max\_disc - 1) // 2

               linha += " " \* pad "|" + " " \* pad + " "

       print(linha)

     # índices das torres

     índices = ""

     for i in range(n\_torres):

         s = f"\[{i}]"

         pad = (largura\_max\_disc - len(s) // 2

     print(índices)

     print()  #linha em branco



def movimento valido(torres, origem, destino):

    if origem < 0 or origem >= len(torres) or destino < 0 or destino >= len(torres):

        return False, "Índice de torre inválido."

    if origem == destino:

        return False, "Origem e destino iguais."

    if not torres\[origem]:

        return False, "A torre de origem está vazia."

    if torres\[destino] and torres\[origem]\[-1] > torres\[destino]\[-1]:

        return False, "Movimento inválido: não pode colocar disco maior sobre menor."

    return True, ""



def checar\_vitoria(torres, n\_discos, torre\_inicial=0):

    # vitória: qualquer torre (exceto a inicial) contém todos os discos em ordem descrescente

    for i, t in enumerate(torres):

        if i == torre inicial:

            continue

        if len(t) == discos and t == list(range(n\_discos, 0, -1)):

            return True, i

    return False, None



def instruções():

    print("Comandos:")

    print(" - Para mover: digite 'origem destino' (ex.: 0 2) ou '0,2' ou 'move 0 2'.")

    print(" - 'q' ou 'quit' para sair.")

    print("Regras: só é permitido mover um por vez e nunca colocar disco maior sobre menor.")

    print()



def parse move(line):

    line = line.strip().lower().replace(',','').replace('move','').split()

    if not line:

        return None

    try:

        origem = int(line\[0])

        destino = int(line\[1])

        returne origem, destino

    except Exceptiion:

        return None



def jogo():

    print("=== Torre de Hanói (interativo) ===")

    print(Digite 'q' a qualquer momento para sair.")

    n\_torres = solicitar\_int("Número de torres (mínimo 3): ", 3)

    n\_discos = solicitar\_int("Número de discos (mínimo 3): ", 3)

    torres = criar\_jogo(n\_torres, n\_discos)

    movimentos = 0

    instrcoes()

    while True:

        mostrar\_torres(torres, n\_discos)

        print(f"Movimentos: {movimento}")

        if linha = input("Seu movimento > ").strip()

            if linha.lower() in ('q', 'quit', 'sair'):

             print("saindo... Até a próxima.")

             break

        parsed = parse move(linha)

        if not parsed:

            print("Formato inválido. Exemplos válidos: '0 2', 'move 0 2', '0,2'.")

            continue

        # executar movimento

        disco = torres\[origem].pop()

        torres\[destino].append(disco)

        movimentos += 1

        ganhou, qual = checar\_vitoria(torres, n\_discos, torre\_inicial=0)

        if ganhou:

            mostrar torres(torres, n\_discos)

           print(f"Parabéns - você venceu em {movimentos} movimentos! Todos os discos foram movidos para a torre {qual}.")

           break



if \_\_name\_\_ == "\_\_main\_\_":

    try:

        jogo()

    except KeyboardInterrupt:

        print("\\nJogo interrompido. Até

