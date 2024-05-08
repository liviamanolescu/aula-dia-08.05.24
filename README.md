def gravar_nome_em_arquivo():
    nome = input("Por favor, digite seu nome: ")

    # Abrindo o arquivo em modo de escrita ('w')
    with open("nome_usuario.txt", "w") as arquivo:
        arquivo.write(nome)

    print("Seu nome foi gravado no arquivo com sucesso!")

# Chamando a função para gravar o nome do usuário
gravar_nome_em_arquivo()

def imprimir_conteudo_arquivo():
    # Solicita ao usuário o nome do arquivo de texto
    nome_arquivo = input("Por favor, digite o nome do arquivo de texto: ")

    try:
        # Abre o arquivo em modo de leitura ('r')
        with open(nome_arquivo, "r") as arquivo:
            # Lê e imprime o conteúdo do arquivo
            conteudo = arquivo.read()
            print("Conteúdo do arquivo:")
            print(conteudo)
    except FileNotFoundError:
        # Se o arquivo não for encontrado, imprime uma mensagem de erro
        print("O arquivo especificado não foi encontrado.")

# Chama a função para imprimir o conteúdo do arquivo
imprimir_conteudo_arquivo()

def copiar_conteudo_arquivo():
    # Solicita ao usuário o nome do arquivo original
    nome_arquivo_original = input("Digite o nome do arquivo de origem: ")

    try:
        # Abre o arquivo original em modo de leitura ('r')
        with open(nome_arquivo_original, "r") as arquivo_original:
            # Lê o conteúdo do arquivo original
            conteudo = arquivo_original.read()

            # Solicita ao usuário o nome do novo arquivo
            nome_novo_arquivo = input("Digite o nome do novo arquivo: ")

            # Abre o novo arquivo em modo de escrita ('w')
            with open(nome_novo_arquivo, "w") as novo_arquivo:
                # Escreve o conteúdo do arquivo original no novo arquivo
                novo_arquivo.write(conteudo)

            print("Conteúdo do arquivo copiado com sucesso para o novo arquivo.")
    except FileNotFoundError:
        # Se o arquivo original não for encontrado, imprime uma mensagem de erro
        print("O arquivo especificado não foi encontrado.")

# Chama a função para copiar o conteúdo do arquivo
copiar_conteudo_arquivo()


def encontrar_nome_por_numero():
    # Solicita ao usuário um número
    numero = input("Digite um número para encontrar o nome correspondente: ")

    try:
        # Abre o arquivo em modo de leitura ('r')
        with open("nomes.txt", "r") as arquivo:
            # Lê todas as linhas do arquivo
            linhas = arquivo.readlines()

            # Percorre cada linha para procurar o número
            encontrado = False
            for linha in linhas:
                # Separa o número e o nome da linha
                partes = linha.strip().split(":")
                if partes[0] == numero:
                    # Se o número for encontrado, imprime o nome correspondente
                    print("O nome correspondente ao número", numero, "é:", partes[1])
                    encontrado = True
                    break

            # Se o número não for encontrado, exibe uma mensagem
            if not encontrado:
                print("Número não encontrado no arquivo.")
    except FileNotFoundError:
        # Se o arquivo não for encontrado, imprime uma mensagem de erro
        print("O arquivo de nomes não foi encontrado.")

# Chama a função para encontrar o nome correspondente ao número
encontrar_nome_por_numero()

def encontrar_nome_por_numero():
    try:
        # Solicita ao usuário um número
        numero = input("Digite um número para encontrar o nome correspondente: ")

        # Abre o arquivo em modo de leitura ('r')
        with open("exemplo.txt", "r") as arquivo:
            # Lê todas as linhas do arquivo
            linhas = arquivo.readlines()

            # Percorre cada linha para procurar o número
            encontrado = False
            for linha in linhas:
                # Separa o número e o nome da linha
                partes = linha.strip().split(":")
                if partes[0] == numero:
                    # Se o número for encontrado, imprime o nome correspondente
                    print("O nome correspondente ao número", numero, "é:", partes[1])
                    encontrado = True
                    break

            # Se o número não for encontrado, exibe uma mensagem
            if not encontrado:
                print("Número não encontrado no arquivo.")
    except FileNotFoundError:
        # Se o arquivo não for encontrado, imprime uma mensagem de erro
        print("O arquivo de exemplo não foi encontrado.")

# Chama a função para encontrar o nome correspondente ao número
encontrar_nome_por_numero()

