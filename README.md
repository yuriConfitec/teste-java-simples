# Teste Prático Java

Desenvolver um aplicação que receba o json abaixo, e responda o resultado baseado nos parâmetros informados.

### modelo de entrada
```json
{
  "valorTotal": "number",
  "quantidadeParcelas": "number",
  "tipoResposata": "ENUM",
  "tipoParcelamento": "ENUM"
}
```
Onde
campo|observação
-----|-----
valorTotal|valor total a ser parcelado
quantidadeParcelas|quantidades de parcelas que o valor será rateado
tipoResposata|enum que varia entre SIMPLES e COMPLETA
tipoParcelamento|enum que varia entre RESTO_PRIMEIRA_PARCELA e RESTO_ULTIMA_PARCELA, RESTO_NAS_PRIMEIRAS_PARCELAS, RESTO_NAS_ULTIMAS_PARCELAS

## Regras
- o tipoParcelamento define a forma que o "resto" do parcelamento deve ser alocado
- o tipoResposta define o modelo de resposta esperado, sendo:
   - SIMPLES: lista com parcelas iguais agrupadas, controlando o intervalo (de parcela X até parcela Y)
   - COMPLETA: lista sem agrupamento, detalhando todas as parcelas
- a saída deve ser ordenada.

### modelos saída
 - modelo saída **simples**
```json
{
  "parcelamento": [{
    "valorParcela": "number",
    "parcelaInicial": "number",
    "parcelaFinal": "number"
  }],
  "entrada": "{} -> modelo de entrada recebido"
}
```

 - modelo saída **completo**
```json
{
  "parcelamento": [{
    "valorParcela": "number",
    "numeroParcela": "number"
  }],
  "entrada": "{} -> modelo de entrada recebido"
}
```
