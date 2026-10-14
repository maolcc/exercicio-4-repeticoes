# Exercício 05 — Sequência de Fibonacci

**1. Entradas:** um número inteiro n, maior ou igual a zero.

**2. Processamento:**
- validar se n ≥ 0;
- se n = 0, o termo é 0;
- senão, começar com anterior ← 0 e atual ← 1 e repetir de 2 até n: proximo ← anterior + atual; anterior ← atual; atual ← proximo.

**3. Saídas:** o enésimo termo da sequência de Fibonacci.

**4. Pseudocódigo**

```
algoritmo "Fibonacci"
var
   n, i, anterior, atual, proximo: inteiro
inicio
   repita
      escreva("Digite um número inteiro maior ou igual a zero: ")
      leia(n)
      se n < 0 entao
         escreval("Número inválido.")
      fimse
   ate n >= 0
   se n = 0 entao
      escreval("O termo de ordem 0 da sequência de Fibonacci é: 0")
   senao
      anterior <- 0
      atual <- 1
      para i de 2 ate n faca
         proximo <- anterior + atual
         anterior <- atual
         atual <- proximo
      fimpara
      escreval("O termo de ordem ", n, " da sequência de Fibonacci é: ", atual)
   fimse
fimalgoritmo
```
