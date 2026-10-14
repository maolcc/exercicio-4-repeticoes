# Exercício 08 — Dias do mês

**1. Entradas:** mês (1 a 12), ano e a resposta para continuar.

**2. Processamento:**
- validar o mês;
- fevereiro: 29 dias se o ano for bissexto, ((ano mod 4 = 0) e (ano mod 100 ≠ 0)) ou (ano mod 400 = 0); senão, 28 dias;
- abril, junho, setembro e novembro: 30 dias;
- demais meses: 31 dias;
- repetir enquanto a resposta for S.

**3. Saídas:** número de dias do mês/ano e a pergunta "VOCÊ DESEJA OUTRAS ENTRADAS (S/?)?".

Observação: o mês e o ano são lidos separadamente.

**4. Pseudocódigo**

```
algoritmo "DiasDoMes"
var
   mes, ano, dias: inteiro
   resposta: caractere
inicio
   repita
      repita
         escreva("Digite o mês (1 a 12): ")
         leia(mes)
         se (mes < 1) ou (mes > 12) entao
            escreval("Mês inválido.")
         fimse
      ate (mes >= 1) e (mes <= 12)
      escreva("Digite o ano: ")
      leia(ano)
      se mes = 2 entao
         se ((ano mod 4 = 0) e (ano mod 100 <> 0)) ou (ano mod 400 = 0) entao
            dias <- 29
         senao
            dias <- 28
         fimse
      senao
         se (mes = 4) ou (mes = 6) ou (mes = 9) ou (mes = 11) entao
            dias <- 30
         senao
            dias <- 31
         fimse
      fimse
      escreval("O mês ", mes, "/", ano, " tem ", dias, " dias.")
      escreva("VOCÊ DESEJA OUTRAS ENTRADAS (S/?)? ")
      leia(resposta)
   ate resposta <> "S"
fimalgoritmo
```
