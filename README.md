# Web Scraping de criptomoedas

Mini projeto em Python que lê a página do [CoinMarketCap](https://coinmarketcap.com/) e extrai, em tempo real, os dados das 10 primeiras criptomoedas do ranking.

## O que ele faz

1. Faz a requisição da página com **requests**.
2. Lê o HTML com **BeautifulSoup** e percorre as linhas da tabela de cotações.
3. Para cada moeda, extrai:
   - nome e código (ex: Bitcoin, BTC)
   - preço atual
   - variação em 1 hora, 24 horas e 7 dias (com o sinal negativo quando a moeda caiu)
   - valor de mercado (*market cap*)
   - volume negociado em 24 horas
   - data e hora da coleta
4. Monta um dicionário com todas as moedas, pronto para virar planilha, gráfico ou alerta.

Formato de um item do resultado:

```python
{
  "Bitcoin": {
    "nome": "Bitcoin", "codigo": "BTC", "preco": "$...",
    "var_1h": "...%", "var_24h": "-...%", "var_7d": "...%",
    "market_cap": "$...", "volume": "$...", "data": "AAAA-MM-DD HH:MM:SS"
  }
}
```

## Tecnologias

- **Python 3.12**
- **requests** (requisição HTTP)
- **BeautifulSoup** (leitura do HTML)
- **re** (expressões regulares para achar valores em `$` e `%`)

## Como rodar

```bash
pip install requests beautifulsoup4 jupyter
jupyter notebook Mini_projeto.ipynb
```

> O scraping depende das classes CSS do site. Se o CoinMarketCap mudar o layout, os seletores precisam ser atualizados.

## Estrutura

```
Mini_projeto.ipynb          solução do projeto
Gabarito - Exercicio.ipynb  enunciado e gabarito de referência
```

---

Projeto de estudo de Web Scraping · [Michaell Dantas](https://github.com/michaelldantas)
