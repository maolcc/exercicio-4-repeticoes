# Exercício 04 — Elevadores do prédio

**1. Entradas:** para cada um dos 50 moradores, o elevador mais usado (A, B ou C) e o período (M, V ou N).

**2. Processamento:**
- repetir 50 vezes, validando elevador e período;
- contar cada combinação de elevador e período (aM, aV, aN, bM, ...);
- totais por elevador (totA, totB, totC) e por período (totM, totV, totN);
- período mais usado e o elevador com mais uso nesse período;
- elevador mais usado e o período com mais uso nesse elevador;
- diferença percentual ← (maiorPeriodo - menorPeriodo) * 100 / 50;
- uso do elevador de média utilização ← 50 - maiorElevador - menorElevador;
- percentual de média utilização ← mediaElevador * 100 / 50.

**3. Saídas:** período mais usado e seu elevador; elevador mais usado e seu período de maior fluxo; diferença percentual entre o período mais usado e o menos usado; percentual do elevador de média utilização.

Observações:
- os percentuais foram calculados sobre o total de 50 respostas;
- em caso de empate, o algoritmo considera o primeiro na ordem A, B, C (elevadores) e M, V, N (períodos).

**4. Pseudocódigo**

```
algoritmo "Elevadores"
var
   elevador, periodo, nomePeriodo, elevadorDoPeriodo, nomeElevador, periodoDoElevador: caractere
   i, aM, aV, aN, bM, bV, bN, cM, cV, cN: inteiro
   totA, totB, totC, totM, totV, totN: inteiro
   qa, qb, qc, qm, qv, qn: inteiro
   maiorPeriodo, menorPeriodo, maiorElevador, menorElevador, mediaElevador: inteiro
   diferencaPercentual, percentualMedio: real
inicio
   aM <- 0
   aV <- 0
   aN <- 0
   bM <- 0
   bV <- 0
   bN <- 0
   cM <- 0
   cV <- 0
   cN <- 0
   para i de 1 ate 50 faca
      escreval("Morador ", i)
      repita
         escreva("Elevador mais usado (A, B ou C): ")
         leia(elevador)
         se (elevador <> "A") e (elevador <> "B") e (elevador <> "C") entao
            escreval("Elevador inválido.")
         fimse
      ate (elevador = "A") ou (elevador = "B") ou (elevador = "C")
      repita
         escreva("Período (M - matutino, V - vespertino, N - noturno): ")
         leia(periodo)
         se (periodo <> "M") e (periodo <> "V") e (periodo <> "N") entao
            escreval("Período inválido.")
         fimse
      ate (periodo = "M") ou (periodo = "V") ou (periodo = "N")
      se elevador = "A" entao
         se periodo = "M" entao
            aM <- aM + 1
         senao
            se periodo = "V" entao
               aV <- aV + 1
            senao
               aN <- aN + 1
            fimse
         fimse
      senao
         se elevador = "B" entao
            se periodo = "M" entao
               bM <- bM + 1
            senao
               se periodo = "V" entao
                  bV <- bV + 1
               senao
                  bN <- bN + 1
               fimse
            fimse
         senao
            se periodo = "M" entao
               cM <- cM + 1
            senao
               se periodo = "V" entao
                  cV <- cV + 1
               senao
                  cN <- cN + 1
               fimse
            fimse
         fimse
      fimse
   fimpara
   totA <- aM + aV + aN
   totB <- bM + bV + bN
   totC <- cM + cV + cN
   totM <- aM + bM + cM
   totV <- aV + bV + cV
   totN <- aN + bN + cN
   se (totM >= totV) e (totM >= totN) entao
      nomePeriodo <- "Matutino"
      maiorPeriodo <- totM
      qa <- aM
      qb <- bM
      qc <- cM
   senao
      se totV >= totN entao
         nomePeriodo <- "Vespertino"
         maiorPeriodo <- totV
         qa <- aV
         qb <- bV
         qc <- cV
      senao
         nomePeriodo <- "Noturno"
         maiorPeriodo <- totN
         qa <- aN
         qb <- bN
         qc <- cN
      fimse
   fimse
   se (qa >= qb) e (qa >= qc) entao
      elevadorDoPeriodo <- "A"
   senao
      se qb >= qc entao
         elevadorDoPeriodo <- "B"
      senao
         elevadorDoPeriodo <- "C"
      fimse
   fimse
   se (totA >= totB) e (totA >= totC) entao
      nomeElevador <- "A"
      maiorElevador <- totA
      qm <- aM
      qv <- aV
      qn <- aN
   senao
      se totB >= totC entao
         nomeElevador <- "B"
         maiorElevador <- totB
         qm <- bM
         qv <- bV
         qn <- bN
      senao
         nomeElevador <- "C"
         maiorElevador <- totC
         qm <- cM
         qv <- cV
         qn <- cN
      fimse
   fimse
   se (qm >= qv) e (qm >= qn) entao
      periodoDoElevador <- "Matutino"
   senao
      se qv >= qn entao
         periodoDoElevador <- "Vespertino"
      senao
         periodoDoElevador <- "Noturno"
      fimse
   fimse
   se (totM <= totV) e (totM <= totN) entao
      menorPeriodo <- totM
   senao
      se totV <= totN entao
         menorPeriodo <- totV
      senao
         menorPeriodo <- totN
      fimse
   fimse
   se (totA <= totB) e (totA <= totC) entao
      menorElevador <- totA
   senao
      se totB <= totC entao
         menorElevador <- totB
      senao
         menorElevador <- totC
      fimse
   fimse
   diferencaPercentual <- (maiorPeriodo - menorPeriodo) * 100 / 50
   mediaElevador <- 50 - maiorElevador - menorElevador
   percentualMedio <- mediaElevador * 100 / 50
   escreval("Período mais usado: ", nomePeriodo, " - pertence ao elevador ", elevadorDoPeriodo)
   escreval("Elevador mais frequentado: ", nomeElevador, " - maior fluxo no período ", periodoDoElevador)
   escreval("Diferença percentual entre o período mais usado e o menos usado: ", diferencaPercentual:0:2, "%")
   escreval("Percentual do elevador de média utilização: ", percentualMedio:0:2, "%")
fimalgoritmo
```
