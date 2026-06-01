print("==== SISTEMA ====")

while True:

    print("\n1 - cadastrar")
    print("2 - login")
    print("3 - sair")

    escolha = input("oque deseja fazer? ")

    if escolha == "1":

        print("\n=== cadastro ===")

        usuario = input("crie um usuario: ")
        senha = input("crie uma senha: ")

        arquivo = open("usuarios.txt", "a")

        arquivo.write(usuario)
        arquivo.write(";")
        arquivo.write(senha)
        arquivo.write("\n")

        arquivo.close()

        print("\nusuario cadastrado!")

    elif escolha == "2":

        print("\n=== login ===")

        usuario2 = input("usuario: ")
        senha2 = input("senha: ")

        arquivo = open("usuarios.txt", "r")

        login = False

        for linha in arquivo:

            linha = linha.strip()

            partes = linha.split(";")

            usuario_salvo = partes[0]
            senha_salva = partes[1]

            if usuario2 == usuario_salvo:

                if senha2 == senha_salva:

                    login = True

        arquivo.close()

        if login == True:

            print("\nlogin feito!")

            pontos = 0

            continuar = "s"

            while continuar == "s":

                print("\n===== FLASHCARDS =====")

                print("1 matematica")
                print("2 historia")
                print("3 portugues")

                opcao = input("digite: ")

                if opcao == "1":

                    resposta = input("quanto é 7 x 8? ")

                    if resposta == "56":
                        print("acertou")
                        pontos = pontos + 1

                    else:
                        print("errou")
                        print("resposta certa era 56")

                    resposta = input("quanto é 15 + 20? ")

                    if resposta == "35":
                        print("acertou")
                        pontos = pontos + 1

                    else:
                        print("errou")
                        print("a resposta era 35")

                    resposta = input("quanto é 100 dividido por 4? ")

                    if resposta == "25":
                        print("acertou")
                        pontos = pontos + 1

                    else:
                        print("errou")
                        print("era 25")

                elif opcao == "2":

                    resposta = input("quem descobriu o brasil? ")

                    if resposta.lower() == "pedro alvares cabral":
                        print("acertou")
                        pontos = pontos + 1

                    else:
                        print("errou")
                        print("foi pedro alvares cabral")

                    resposta = input("em que ano o brasil foi descoberto? ")

                    if resposta == "1500":
                        print("acertou")
                        pontos = pontos + 1

                    else:
                        print("errou")
                        print("foi em 1500")

                elif opcao == "3":

                    resposta = input("plural de cão: ")

                    if resposta.lower() == "cães":
                        print("acertou")
                        pontos = pontos + 1

                    else:
                        print("errou")
                        print("a resposta era cães")

                    resposta = input("antonimo de feliz: ")

                    if resposta.lower() == "triste":
                        print("acertou")
                        pontos = pontos + 1

                    else:
                        print("errou")
                        print("era triste")

                else:

                    print("opcao invalida")

                print("\nvc tem", pontos, "pontos")

                continuar = input("quer continuar? ")

            print("\nfim do jogo")

        else:

            print("\nlogin errado")

    elif escolha == "3":

        print("fechando sistema")
        break

    else:

        print("digite um numero valido")
