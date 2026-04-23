

numero = input("Digite um número de até 4 dígitos: ")


if numero.isdigit():

    if len(numero) <= 4:

        numero = numero.zfill(4)

        erro = False

        for digito in numero:
            if numero.count(digito) >= 3:
                erro = True

        if erro:
            print("Erro: número com muitos dígitos repetidos.")

        else:
            contador = 0

            while numero != "6174":

                contador += 1

                crescente = "".join(sorted(numero))
                decrescente = "".join(sorted(numero, reverse=True))

                resultado = int(decrescente) - int(crescente)

                print(f"Iteração {contador}: {decrescente} - {crescente} = {resultado:04d}")

                numero = str(resultado).zfill(4)

            print("\nConstante de Kaprekar atingida!")

    else:   
        print("Erro: máximo 4 dígitos.")

else:
    print("Erro: digite apenas números inteiros positivos.")    
