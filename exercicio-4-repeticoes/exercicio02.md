# Exercício 02 — Pesquisa de características físicas

**1. Entradas:** para cada habitante, idade, sexo, cor dos olhos, cor dos cabelos e salário. A idade -1 encerra a pesquisa.

**2. Processamento:**
- validar cada campo, repetindo a leitura até o valor ser aceito:
  - idade entre 10 e 100 (ou -1 para encerrar);
  - sexo: m ou f;
  - olhos: a, v, c ou p;
  - cabelos: l, c, p ou r;
  - salário não negativo;
- totalHabitantes ← totalHabitantes + 1;
- se sexo = f, idade entre 18 e 35, olhos = c e cabelos = c, totalGrupo ← totalGrupo + 1;
- percentual ← totalGrupo * 100 / totalHabitantes.

**3. Saídas:** mensagens de dado inválido e a porcentagem de mulheres de 18 a 35 anos com olhos e cabelos castanhos.

Observação: a idade é lida primeiro. Assim, para encerrar, basta digitar -1, sem precisar preencher os outros dados do habitante fictício.

**4. Pseudocódigo**

```
algoritmo "PesquisaHabitantes"
var
   sexo, olhos, cabelos: caractere
   idade, totalHabitantes, totalGrupo: inteiro
   salario, percentual: real
inicio
   totalHabitantes <- 0
   totalGrupo <- 0
   repita
      repita
         escreva("Idade (10 a 100, ou -1 para encerrar): ")
         leia(idade)
         se (idade <> -1) e ((idade < 10) ou (idade > 100)) entao
            escreval("Idade inválida.")
         fimse
      ate (idade = -1) ou ((idade >= 10) e (idade <= 100))
      se idade <> -1 entao
         repita
            escreva("Sexo (m/f): ")
            leia(sexo)
            se (sexo <> "m") e (sexo <> "f") entao
               escreval("Sexo inválido.")
            fimse
         ate (sexo = "m") ou (sexo = "f")
         repita
            escreva("Cor dos olhos (a - azuis, v - verdes, c - castanhos, p - pretos): ")
            leia(olhos)
            se (olhos <> "a") e (olhos <> "v") e (olhos <> "c") e (olhos <> "p") entao
               escreval("Cor dos olhos inválida.")
            fimse
         ate (olhos = "a") ou (olhos = "v") ou (olhos = "c") ou (olhos = "p")
         repita
            escreva("Cor dos cabelos (l - loiros, c - castanhos, p - pretos, r - ruivos): ")
            leia(cabelos)
            se (cabelos <> "l") e (cabelos <> "c") e (cabelos <> "p") e (cabelos <> "r") entao
               escreval("Cor dos cabelos inválida.")
            fimse
         ate (cabelos = "l") ou (cabelos = "c") ou (cabelos = "p") ou (cabelos = "r")
         repita
            escreva("Salário: R$ ")
            leia(salario)
            se salario < 0 entao
               escreval("O salário não pode ser negativo.")
            fimse
         ate salario >= 0
         totalHabitantes <- totalHabitantes + 1
         se (sexo = "f") e (idade >= 18) e (idade <= 35) e (olhos = "c") e (cabelos = "c") entao
            totalGrupo <- totalGrupo + 1
         fimse
      fimse
   ate idade = -1
   se totalHabitantes > 0 entao
      percentual <- totalGrupo * 100 / totalHabitantes
      escreval("Total de habitantes pesquisados: ", totalHabitantes)
      escreval("Mulheres de 18 a 35 anos com olhos e cabelos castanhos: ", percentual:0:2, "%")
   senao
      escreval("Nenhum habitante foi cadastrado.")
   fimse
fimalgoritmo
```
