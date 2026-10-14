# Exercício 03 — Pesquisa do cinema

**1. Entradas:** idade e nota (A, B, C, D ou E) de cada um dos 100 espectadores.

**2. Processamento:**
- repetir 100 vezes, validando a nota;
- contar as respostas de cada nota;
- somar as idades de quem respondeu D (ruim);
- guardar a maior idade de quem respondeu A (ótimo), D (ruim) e E (péssimo);
- como o total é de 100 espectadores, percentual ← quantidade * 100 / 100;
- diferença percentual entre bom e regular ← percentual maior - percentual menor;
- média de idade de quem respondeu ruim ← somaIdadeRuim / ruim;
- diferença de idade ← maior idade entre as duas - menor idade entre as duas.

**3. Saídas:** quantidade de respostas ótimo; diferença percentual entre bom e regular; média de idade de quem respondeu ruim; percentual de respostas péssimo e a maior idade que escolheu péssimo; diferença entre a maior idade que respondeu ótimo e a maior idade que respondeu ruim.

**4. Pseudocódigo**

```
algoritmo "PesquisaCinema"
var
   i, idade, otimo, bom, regular, ruim, pessimo: inteiro
   somaIdadeRuim, maiorIdadeOtimo, maiorIdadeRuim, maiorIdadePessimo, diferencaIdade: inteiro
   nota: caractere
   diferencaPercentual, mediaIdadeRuim, percentualPessimo: real
inicio
   otimo <- 0
   bom <- 0
   regular <- 0
   ruim <- 0
   pessimo <- 0
   somaIdadeRuim <- 0
   maiorIdadeOtimo <- 0
   maiorIdadeRuim <- 0
   maiorIdadePessimo <- 0
   para i de 1 ate 100 faca
      escreval("Espectador ", i)
      escreva("Idade: ")
      leia(idade)
      repita
         escreva("Nota (A - Ótimo, B - Bom, C - Regular, D - Ruim, E - Péssimo): ")
         leia(nota)
         se (nota <> "A") e (nota <> "B") e (nota <> "C") e (nota <> "D") e (nota <> "E") entao
            escreval("Nota inválida.")
         fimse
      ate (nota = "A") ou (nota = "B") ou (nota = "C") ou (nota = "D") ou (nota = "E")
      se nota = "A" entao
         otimo <- otimo + 1
         se idade > maiorIdadeOtimo entao
            maiorIdadeOtimo <- idade
         fimse
      senao
         se nota = "B" entao
            bom <- bom + 1
         senao
            se nota = "C" entao
               regular <- regular + 1
            senao
               se nota = "D" entao
                  ruim <- ruim + 1
                  somaIdadeRuim <- somaIdadeRuim + idade
                  se idade > maiorIdadeRuim entao
                     maiorIdadeRuim <- idade
                  fimse
               senao
                  pessimo <- pessimo + 1
                  se idade > maiorIdadePessimo entao
                     maiorIdadePessimo <- idade
                  fimse
               fimse
            fimse
         fimse
      fimse
   fimpara
   escreval("Quantidade de respostas ótimo: ", otimo)
   se bom >= regular entao
      diferencaPercentual <- (bom - regular) * 100 / 100
   senao
      diferencaPercentual <- (regular - bom) * 100 / 100
   fimse
   escreval("Diferença percentual entre bom e regular: ", diferencaPercentual:0:2, "%")
   se ruim > 0 entao
      mediaIdadeRuim <- somaIdadeRuim / ruim
      escreval("Média de idade de quem respondeu ruim: ", mediaIdadeRuim:0:2)
   senao
      escreval("Ninguém respondeu ruim.")
   fimse
   percentualPessimo <- pessimo * 100 / 100
   escreval("Percentual de respostas péssimo: ", percentualPessimo:0:2, "%")
   se pessimo > 0 entao
      escreval("Maior idade que respondeu péssimo: ", maiorIdadePessimo)
   fimse
   se maiorIdadeOtimo >= maiorIdadeRuim entao
      diferencaIdade <- maiorIdadeOtimo - maiorIdadeRuim
   senao
      diferencaIdade <- maiorIdadeRuim - maiorIdadeOtimo
   fimse
   escreval("Diferença entre a maior idade de ótimo e a maior idade de ruim: ", diferencaIdade, " anos")
fimalgoritmo
```
