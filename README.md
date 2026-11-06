print()
print("Olá! Somos a Divina Marmita, um restaurante com temática de Tecnologia!!!")
print()
 
# Acumuladores para o fechamento do dia
total_pedidos = 0
total_marmitas = 0
total_marmitas_g = 0
faturamento_total = 0
maior_pedido = 0
 
# Lista para guardar os pedidos
pedidos = []
 
continuar_dia = "s"
 
while continuar_dia.lower() == "s":
 
    print("\n-----------------------------------------")
    print("NOVO PEDIDO")
    print("-----------------------------------------")
 
    # Validação da distância
    local = -1
 
    while local < 0:
        local = float(input("Digite em km a distância até o local: "))
 
        if local < 0:
            print("A distância não pode ser negativa. Tente novamente.")
 
    # Cálculo da taxa de entrega
    if local > 8:
        print("Local fora da área de entrega.")
        print("O pedido deverá ser retirado no restaurante.")
        taxa = 0.00
 
    elif local > 5:
        taxa = 8.00
        print(f"Taxa de entrega de R$ {taxa:.2f}")
 
    elif local > 2:
        taxa = 5.00
        print(f"Taxa de entrega de R$ {taxa:.2f}")
 
    else:
        taxa = 0.00
        print("Entrega Grátis!")
 
    print("\nNosso Menu:")
    print(" 1- Strogonoff de Frango P - R$ 15,00")
    print(" 2- Strogonoff de Frango M - R$ 18,00")
    print(" 3- Strogonoff de Frango G - R$ 22,00")
    print(" 4- Strogonoff de Carne P - R$ 15,00")
    print(" 5- Strogonoff de Carne M - R$ 18,00")
    print(" 6- Strogonoff de Carne G - R$ 22,00")
    print(" 7- Parmegiana de Frango P - R$ 15,00")
    print(" 8- Parmegiana de Frango M - R$ 18,00")
    print(" 9- Parmegiana de Frango G - R$ 22,00")
    print(" 10- Parmegiana de Carne P - R$ 15,00")
    print(" 11- Parmegiana de Carne M - R$ 18,00")
    print(" 12- Parmegiana de Carne G - R$ 22,00")
    print(" 13- Filé de Frango P - R$ 15,00")
    print(" 14- Filé de Frango M - R$ 18,00")
    print(" 15- Filé de Frango G - R$ 22,00")
 
    # Quantidade de marmitas
    quantidade = 0
 
    while quantidade < 1 or quantidade > 10:
        quantidade = int(input("\nQuantas marmitas deseja pedir? (1 a 10): "))
 
        if quantidade < 1 or quantidade > 10:
            print("Quantidade inválida! Escolha entre 1 e 10.")
 
    subtotal = 0
    quantidade_g = 0
    marmitas_pedido = []
 
    # Escolha das marmitas
    for i in range(quantidade):
 
        opcao = 0
 
        while opcao < 1 or opcao > 15:
            opcao = int(input(f"\nDigite a opção da marmita {i + 1} (1 a 15): "))
 
            if opcao < 1 or opcao > 15:
                print("Opção inválida! Tente novamente.")
 
        if opcao == 1:
            valor = 15.00
            nome = "Strogonoff de Frango P"
 
        elif opcao == 2:
            valor = 18.00
            nome = "Strogonoff de Frango M"
 
        elif opcao == 3:
            valor = 22.00
            nome = "Strogonoff de Frango G"
            quantidade_g += 1
 
        elif opcao == 4:
            valor = 15.00
            nome = "Strogonoff de Carne P"
 
        elif opcao == 5:
            valor = 18.00
            nome = "Strogonoff de Carne M"
 
        elif opcao == 6:
            valor = 22.00
            nome = "Strogonoff de Carne G"
            quantidade_g += 1
 
        elif opcao == 7:
            valor = 15.00
            nome = "Parmegiana de Frango P"
 
        elif opcao == 8:
            valor = 18.00
            nome = "Parmegiana de Frango M"
 
        elif opcao == 9:
            valor = 22.00
            nome = "Parmegiana de Frango G"
            quantidade_g += 1
 
        elif opcao == 10:
            valor = 15.00
            nome = "Parmegiana de Carne P"
 
        elif opcao == 11:
            valor = 18.00
            nome = "Parmegiana de Carne M"
 
        elif opcao == 12:
            valor = 22.00
            nome = "Parmegiana de Carne G"
            quantidade_g += 1
 
        elif opcao == 13:
            valor = 15.00
            nome = "Filé de Frango P"
 
        elif opcao == 14:
            valor = 18.00
            nome = "Filé de Frango M"
 
        elif opcao == 15:
            valor = 22.00
            nome = "Filé de Frango G"
            quantidade_g += 1
 
        subtotal += valor
        marmitas_pedido.append(nome)
 
        print(f"{nome} adicionado: R$ {valor:.2f}")
 
    # Valores das bebidas
    val_Coca_Lata_350ml = 9.90
    val_Coca_Lata_Zero_350ml = 10.50
    val_Coca_Cola_2L = 16.90
    val_Coca_Cola_2L_Zero = 16.90
    val_Fanta_Uva_Lata = 8.90
    val_Fanta_Uva_2L = 15.90
    val_Fanta_Laranja_Lata = 8.90
    val_Fanta_Laranja_2L = 15.90
    val_Sprit_Lata = 8.90
    val_Guarana_Lata = 8.90
    val_Guarana_Lata_Zero = 8.90
    val_Fanta_Guaraná_2L = 14.90
 
    valor_bebida = 0.00
 
    # Escolha de bebida
    resposta_bebida = 0
 
    while resposta_bebida != 1 and resposta_bebida != 2:
        print("\nDeseja adicionar bebida?")
        print(" 1 - Sim")
        print(" 2 - Não")
 
        resposta_bebida = int(input("Informe a opção: "))
 
        if resposta_bebida != 1 and resposta_bebida != 2:
            print("Opção inválida! Digite 1 ou 2.")
 
    if resposta_bebida == 1:
 
        print("\nBebidas:")
        print(" 1- Coca Lata 350ml: R$ 9,90")
        print(" 2- Coca Lata Zero 350ml: R$ 10,50")
        print(" 3- Fanta Uva Lata: R$ 8,90")
        print(" 4- Fanta Laranja Lata: R$ 8,90")
        print(" 5- Sprit Lata: R$ 8,90")
        print(" 6- Guaraná Lata: R$ 8,90")
        print(" 7- Guaraná Lata Zero: R$ 8,90")
        print(" 8- Coca Cola 2L: R$ 16,90")
        print(" 9- Coca Cola 2L Zero: R$ 16,90")
        print(" 10- Fanta Guaraná 2L: R$ 14,90")
        print(" 11- Fanta Uva 2L: R$ 15,90")
        print(" 12- Fanta Laranja 2L: R$ 15,90")
 
        bebida = 0
 
        while bebida < 1 or bebida > 12:
            bebida = int(input("Selecione o número da bebida (1 a 12): "))
 
            if bebida < 1 or bebida > 12:
                print("Bebida inválida! Tente novamente.")
 
        if bebida == 1:
            valor_bebida = val_Coca_Lata_350ml
 
        elif bebida == 2:
            valor_bebida = val_Coca_Lata_Zero_350ml
 
        elif bebida == 3:
            valor_bebida = val_Fanta_Uva_Lata
 
        elif bebida == 4:
            valor_bebida = val_Fanta_Laranja_Lata
 
        elif bebida == 5:
            valor_bebida = val_Sprit_Lata
 
        elif bebida == 6:
            valor_bebida = val_Guarana_Lata
 
        elif bebida == 7:
            valor_bebida = val_Guarana_Lata_Zero
 
        elif bebida == 8:
            valor_bebida = val_Coca_Cola_2L
 
        elif bebida == 9:
            valor_bebida = val_Coca_Cola_2L_Zero
 
        elif bebida == 10:
            valor_bebida = val_Fanta_Guaraná_2L
 
        elif bebida == 11:
            valor_bebida = val_Fanta_Uva_2L
 
        elif bebida == 12:
            valor_bebida = val_Fanta_Laranja_2L
 
    # Frete grátis para pedidos de R$ 80,00 ou mais em marmitas
    if subtotal >= 80 and local <= 8:
        taxa = 0.00
        print("\nParabéns! Seu pedido ganhou frete grátis!")
 
    # Cálculo do pedido
    total = subtotal + valor_bebida + taxa
 
    print("\n-----------------------------------------")
    print("RESUMO DO PEDIDO")
    print("-----------------------------------------")
    print(f"Quantidade de marmitas: {quantidade}")
    print(f"Marmitas escolhidas: {marmitas_pedido}")
    print(f"Valor das marmitas: R$ {subtotal:.2f}")
    print(f"Valor da bebida: R$ {valor_bebida:.2f}")
    print(f"Taxa de entrega: R$ {taxa:.2f}")
    print(f"Total deste pedido: R$ {total:.2f}")
 
    pix = "123.456.789-10"
 
    pag = input("\nEscolha a forma de pagamento (Pix ou Entrega): ").strip()
 
    if pag == "Entrega":
 
        forma = input("Cartão ou Dinheiro: ").strip()
 
        if forma == "Cartão":
            print("A maquininha será enviada!")
 
        elif forma == "Dinheiro":
 
            precisa_troco = input("Precisa de troco? (Sim/Não): ").strip()
 
            if precisa_troco.lower() == "sim":
                pagto = float(input("Digite quanto pagará: "))
                troco = pagto - total
                print(f"Troco: R$ {troco:.2f}")
 
            else:
                print("Ok!")
 
    elif pag == "Pix":
        print(f"Nossa chave Pix é: {pix}")
 
    # Registro do pedido na lista
    registro = f"Pedido {total_pedidos + 1} - Marmitas: {marmitas_pedido} - Quantidade: {quantidade} - Marmitas G: {quantidade_g} - Marmitas: R$ {subtotal:.2f} - Bebida: R$ {valor_bebida:.2f} - Taxa: R$ {taxa:.2f} - Total: R$ {total:.2f}"
 
    pedidos.append(registro)
 
    # Atualização dos contadores e acumuladores
    total_pedidos += 1
    total_marmitas += quantidade
    total_marmitas_g += quantidade_g
    faturamento_total += total
 
    if total > maior_pedido:
        maior_pedido = total
 
    continuar_dia = input("\nDeseja registrar outro pedido? (s/n): ").strip()
 
    while continuar_dia.lower() != "s" and continuar_dia.lower() != "n":
        print("Opção inválida! Digite s ou n.")
        continuar_dia = input("Deseja registrar outro pedido? (s/n): ").strip()
 
# Fechamento do dia
print("\n=========================================")
print("=== FECHAMENTO DO DIA ===")
print("=========================================")
 
if total_pedidos > 0:
 
    media_pedido = faturamento_total / total_pedidos
 
    print(f"Total de pedidos: {total_pedidos}")
    print(f"Total de marmitas vendidas: {total_marmitas}")
    print(f"Total de marmitas G vendidas: {total_marmitas_g}")
    print(f"Faturamento total: R$ {faturamento_total:.2f}")
    print(f"Média por pedido: R$ {media_pedido:.2f}")
    print(f"Maior pedido: R$ {maior_pedido:.2f}")
 
    print("\n-----------------------------------------")
    print("REGISTROS DOS PEDIDOS")
    print("-----------------------------------------")
 
    for registro in pedidos:
        print(registro)
 
else:
    print("Nenhum pedido registrado hoje.")
 
print("\nObrigado por escolher a Divina Marmita!")