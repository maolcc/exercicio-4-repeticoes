# Exercício 07 — Pesquisa da Copa do Mundo Feminina

| Voto | Jogadora |
|---|---|
| 1 | Sam Kerr - Austrália |
| 2 | Alex Morgan - Estados Unidos |
| 3 | Dzsenifer Marozsan - Alemanha |
| 4 | Amandine Henry - França |
| 5 | Marta Vieira - Brasil |

**1. Entradas:** para cada entrevistado, nome, idade (maior que 12), sexo (M ou F) e voto (1 a 5). A partir do 50º entrevistado, a resposta S ou N para encerrar a pesquisa.

**2. Processamento:**
- validar idade, sexo e voto, repetindo a leitura até o valor ser aceito;
- guardar nome, idade, sexo e voto de cada entrevistado em vetores;
- somar 1 ao total de votos da jogadora escolhida;
- contar as mulheres;
- só perguntar se deseja encerrar a partir de 50 entrevistados e encerrar automaticamente ao chegar a 300;
- encontrar o maior número de votos e mostrar todas as jogadoras com esse número (empate);
- percorrer os vetores para montar os relatórios (maior de idade: 18 anos ou mais).

**3. Saídas:** votos de cada jogadora; jogadora(s) mais votada(s); lista de participantes separada por sexo e por maior/menor de idade; nomes dos maiores de idade que votaram na Marta Vieira; quantidade de mulheres.

Observação: como os relatórios só podem ser mostrados depois de todas as entrevistas, os dados de cada pessoa precisam ser guardados. Para isso foram usados vetores.

**4. Pseudocódigo**

```
algoritmo "PesquisaCopaFeminina"
var
   nomes: vetor[1..300] de caractere
   sexos: vetor[1..300] de caractere
   idades: vetor[1..300] de inteiro
   votos: vetor[1..300] de inteiro
   jogadoras: vetor[1..5] de caractere
   totalVotos: vetor[1..5] de inteiro
   nome, sexo, resposta: caractere
   i, j, qtd, idade, voto, maiorVoto, mulheres: inteiro
inicio
   jogadoras[1] <- "Sam Kerr - Austrália"
   jogadoras[2] <- "Alex Morgan - Estados Unidos"
   jogadoras[3] <- "Dzsenifer Marozsan - Alemanha"
   jogadoras[4] <- "Amandine Henry - França"
   jogadoras[5] <- "Marta Vieira - Brasil"
   para j de 1 ate 5 faca
      totalVotos[j] <- 0
   fimpara
   qtd <- 0
   mulheres <- 0
   repita
      qtd <- qtd + 1
      escreval("===== Entrevistado ", qtd, " =====")
      escreva("Nome: ")
      leia(nome)
      repita
         escreva("Idade (maior que 12): ")
         leia(idade)
         se idade <= 12 entao
            escreval("Idade inválida.")
         fimse
      ate idade > 12
      repita
         escreva("Sexo (M - masculino, F - feminino): ")
         leia(sexo)
         se (sexo <> "M") e (sexo <> "F") entao
            escreval("Sexo inválido.")
         fimse
      ate (sexo = "M") ou (sexo = "F")
      para j de 1 ate 5 faca
         escreval(j, " - ", jogadoras[j])
      fimpara
      repita
         escreva("Voto (1 a 5): ")
         leia(voto)
         se (voto < 1) ou (voto > 5) entao
            escreval("Voto inválido.")
         fimse
      ate (voto >= 1) e (voto <= 5)
      nomes[qtd] <- nome
      idades[qtd] <- idade
      sexos[qtd] <- sexo
      votos[qtd] <- voto
      totalVotos[voto] <- totalVotos[voto] + 1
      se sexo = "F" entao
         mulheres <- mulheres + 1
      fimse
      resposta <- "N"
      se (qtd >= 50) e (qtd < 300) entao
         escreva("Deseja encerrar a pesquisa? (S/N): ")
         leia(resposta)
      fimse
   ate (qtd = 300) ou (resposta = "S")
   escreval("===== VOTOS POR JOGADORA =====")
   maiorVoto <- 0
   para j de 1 ate 5 faca
      escreval(jogadoras[j], ": ", totalVotos[j], " voto(s)")
      se totalVotos[j] > maiorVoto entao
         maiorVoto <- totalVotos[j]
      fimse
   fimpara
   escreval("===== JOGADORA(S) MAIS VOTADA(S) =====")
   para j de 1 ate 5 faca
      se totalVotos[j] = maiorVoto entao
         escreval(jogadoras[j], " - ", maiorVoto, " voto(s)")
      fimse
   fimpara
   escreval("===== PARTICIPANTES =====")
   escreval("--- Sexo feminino - maiores de idade ---")
   para i de 1 ate qtd faca
      se (sexos[i] = "F") e (idades[i] >= 18) entao
         escreval(nomes[i], " - ", idades[i], " anos - Feminino")
      fimse
   fimpara
   escreval("--- Sexo feminino - menores de idade ---")
   para i de 1 ate qtd faca
      se (sexos[i] = "F") e (idades[i] < 18) entao
         escreval(nomes[i], " - ", idades[i], " anos - Feminino")
      fimse
   fimpara
   escreval("--- Sexo masculino - maiores de idade ---")
   para i de 1 ate qtd faca
      se (sexos[i] = "M") e (idades[i] >= 18) entao
         escreval(nomes[i], " - ", idades[i], " anos - Masculino")
      fimse
   fimpara
   escreval("--- Sexo masculino - menores de idade ---")
   para i de 1 ate qtd faca
      se (sexos[i] = "M") e (idades[i] < 18) entao
         escreval(nomes[i], " - ", idades[i], " anos - Masculino")
      fimse
   fimpara
   escreval("===== MAIORES DE IDADE QUE VOTARAM NA MARTA VIEIRA =====")
   para i de 1 ate qtd faca
      se (idades[i] >= 18) e (votos[i] = 5) entao
         escreval(nomes[i])
      fimse
   fimpara
   escreval("Quantidade de mulheres que participaram da pesquisa: ", mulheres)
fimalgoritmo
```
