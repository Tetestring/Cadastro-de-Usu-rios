# Aplicação de Cadastro de Usuários em Python

# Lista para armazenar os usuários
usuarios = []

def cadastrar_usuario():
    """Função para cadastrar um novo usuário."""
    nome = input("Digite o nome do usuário: ")
    email = input("Digite o e-mail do usuário: ")
    idade = input("Digite a idade do usuário: ")
    
    usuarios.append({"nome": nome, "email": email, "idade": idade})
    print("Usuário cadastrado com sucesso!\n")

def listar_usuarios():
    """Função para listar todos os usuários cadastrados."""
    if not usuarios:
        print("Nenhum usuário cadastrado.\n")
        return
    
    print("Lista de usuários cadastrados:")
    for i, usuario in enumerate(usuarios, 1):
        print(f"{i}. Nome: {usuario['nome']}, E-mail: {usuario['email']}, Idade: {usuario['idade']}")
    print()

def buscar_usuario():
    """Função para buscar um usuário pelo nome."""
    nome_busca = input("Digite o nome do usuário que deseja buscar: ")
    
    for usuario in usuarios:
        if usuario["nome"].lower() == nome_busca.lower():
            print(f"Usuário encontrado: Nome: {usuario['nome']}, E-mail: {usuario['email']}, Idade: {usuario['idade']}\n")
            return
    
    print("Usuário não encontrado.\n")

def menu():
    """Função para exibir o menu e capturar as opções do usuário."""
    while True:
        print("1 - Cadastrar Usuário")
        print("2 - Listar Usuários")
        print("3 - Buscar Usuário")
        print("4 - Sair")
        
        opcao = input("Escolha uma opção: ")
        print()
        
        if opcao == "1":
            cadastrar_usuario()
        elif opcao == "2":
            listar_usuarios()
        elif opcao == "3":
            buscar_usuario()
        elif opcao == "4":
            print("Saindo do programa...")
            break
        else:
            print("Opção inválida! Tente novamente.\n")
