# Exercício 06 — Divisores de um número

**1. Entradas:** um número inteiro positivo.

**2. Processamento:** repetir i de 1 até o número; se numero mod i = 0, i é divisor.

**3. Saídas:** os divisores do número.

**4. Pseudocódigo**

```
algoritmo "Divisores"
var
   numero, i: inteiro
inicio
   repita
      escreva("Digite um número positivo: ")
      leia(numero)
      se numero <= 0 entao
         escreval("Número inválido.")
      fimse
   ate numero > 0
   escreva("Os divisores do número ", numero, " são: ")
   para i de 1 ate numero faca
      se numero mod i = 0 entao
         se i = numero entao
            escreval(i)
         senao
            escreva(i, ", ")
         fimse
      fimse
   fimpara
fimalgoritmo
```
