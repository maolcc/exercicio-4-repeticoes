# Exercício 01 — Compra de frutas

**1. Entradas:** opção do menu (1, 2, 3 ou 0 para finalizar) e quantidade de cada fruta escolhida.

**2. Processamento:**
- repetir o menu até a opção 0;
- definir o preço de acordo com a fruta: Abacaxi R$ 5,00, Maçã R$ 1,00, Pera R$ 4,00;
- subtotal ← preco * quantidade;
- total ← total + subtotal;
- se a opção não existir, informar opção inválida.

**3. Saídas:** menu de frutas, subtotal de cada escolha e valor total da compra.

**4. Pseudocódigo**

```
algoritmo "CompraDeFrutas"
var
   opcao, quantidade: inteiro
   preco, subtotal, total: real
inicio
   total <- 0
   repita
      escreval("========== FRUTAS ==========")
      escreval("1 - Abacaxi - R$ 5,00 a unidade")
      escreval("2 - Maçã    - R$ 1,00 a unidade")
      escreval("3 - Pera    - R$ 4,00 a unidade")
      escreval("0 - Finalizar compra")
      escreva("Escolha uma opção: ")
      leia(opcao)
      se (opcao >= 1) e (opcao <= 3) entao
         se opcao = 1 entao
            preco <- 5
         senao
            se opcao = 2 entao
               preco <- 1
            senao
               preco <- 4
            fimse
         fimse
         escreva("Quantidade: ")
         leia(quantidade)
         subtotal <- preco * quantidade
         total <- total + subtotal
         escreval("Subtotal: R$ ", subtotal:0:2)
      senao
         se opcao <> 0 entao
            escreval("Opção inválida.")
         fimse
      fimse
   ate opcao = 0
   escreval("Valor total da compra: R$ ", total:0:2)
fimalgoritmo
```
