# Exercício 09 — Altura e peso de um grupo

**1. Entradas:** nome, sexo (M/m ou F/f), altura e peso de 10 pessoas.

**2. Processamento:**
- repetir 10 vezes, validando o sexo;
- contar homens e mulheres;
- acumular altura e peso separados por sexo;
- médias dos homens e das mulheres ← soma / quantidade (só se a quantidade for maior que zero);
- médias do grupo ← (soma dos homens + soma das mulheres) / 10.

**3. Saídas:** número de homens; número de mulheres; altura média dos homens, das mulheres e do grupo; peso médio dos homens, das mulheres e do grupo.

**4. Pseudocódigo**

```
algoritmo "GrupoDePessoas"
var
   nome, sexo: caractere
   i, homens, mulheres: inteiro
   altura, peso, somaAlturaHomens, somaAlturaMulheres, somaPesoHomens, somaPesoMulheres: real
   mediaAlturaHomens, mediaAlturaMulheres, mediaAlturaGrupo: real
   mediaPesoHomens, mediaPesoMulheres, mediaPesoGrupo: real
inicio
   homens <- 0
   mulheres <- 0
   somaAlturaHomens <- 0
   somaAlturaMulheres <- 0
   somaPesoHomens <- 0
   somaPesoMulheres <- 0
   para i de 1 ate 10 faca
      escreval("===== Pessoa ", i, " =====")
      escreva("Nome: ")
      leia(nome)
      repita
         escreva("Sexo (M ou m - masculino, F ou f - feminino): ")
         leia(sexo)
         se (sexo <> "M") e (sexo <> "m") e (sexo <> "F") e (sexo <> "f") entao
            escreval("Sexo inválido.")
         fimse
      ate (sexo = "M") ou (sexo = "m") ou (sexo = "F") ou (sexo = "f")
      escreva("Altura (m): ")
      leia(altura)
      escreva("Peso (kg): ")
      leia(peso)
      se (sexo = "M") ou (sexo = "m") entao
         homens <- homens + 1
         somaAlturaHomens <- somaAlturaHomens + altura
         somaPesoHomens <- somaPesoHomens + peso
      senao
         mulheres <- mulheres + 1
         somaAlturaMulheres <- somaAlturaMulheres + altura
         somaPesoMulheres <- somaPesoMulheres + peso
      fimse
   fimpara
   escreval("Número de homens: ", homens)
   escreval("Número de mulheres: ", mulheres)
   se homens > 0 entao
      mediaAlturaHomens <- somaAlturaHomens / homens
      mediaPesoHomens <- somaPesoHomens / homens
      escreval("Altura média dos homens: ", mediaAlturaHomens:0:2, " m")
      escreval("Peso médio dos homens: ", mediaPesoHomens:0:2, " kg")
   senao
      escreval("Não há homens no grupo.")
   fimse
   se mulheres > 0 entao
      mediaAlturaMulheres <- somaAlturaMulheres / mulheres
      mediaPesoMulheres <- somaPesoMulheres / mulheres
      escreval("Altura média das mulheres: ", mediaAlturaMulheres:0:2, " m")
      escreval("Peso médio das mulheres: ", mediaPesoMulheres:0:2, " kg")
   senao
      escreval("Não há mulheres no grupo.")
   fimse
   mediaAlturaGrupo <- (somaAlturaHomens + somaAlturaMulheres) / 10
   mediaPesoGrupo <- (somaPesoHomens + somaPesoMulheres) / 10
   escreval("Altura média do grupo: ", mediaAlturaGrupo:0:2, " m")
   escreval("Peso médio do grupo: ", mediaPesoGrupo:0:2, " kg")
fimalgoritmo
```
