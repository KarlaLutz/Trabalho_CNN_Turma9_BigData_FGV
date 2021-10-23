<img src="https://github.com/KarlaLutz/cripto/blob/main/Funda%C3%A7%C3%A3o%20Get%C3%BAlio%20Vargas.jpg">

### Objetivo

Criar modelo preditivo, para construção de robô para operar criptomoedas, especificamente neste trabalho analisaremos a Bitcoin. Além do dataset fornecido pelo professor, foi utilizada API (https://lunarcrush.com/developers/docs#) com features adicionais de redes sociais, interações, etc.


### Conclusões

Após termos as análises dos modelos e o robô de predição funcionando, notamos que mesmo tendo um dataframe rico em informações de notícias recentes, estatísticas de redes sociais, valores anterioremos, é muito difícil acertar uma predição para encontrarmos o melhor momento de comprar ou vender a moeda Bitcoin. Conseguimos ver isso ao observarmos o R-quadrado do nosso modelo linear simples, temos um valor extremamente baixo apesar de termos métricas de erro como por exemplo o MSE tendo valores razoáveis.
Os valores de criptomoedas em geral são muito instáveis e variam muito principalmente devido a questão fiscais e legais, mas também porque o valor flutua conforme as ações dos vendedores/compradores, sem mencionar que a questão da segurança ainda é muito discutida sendo inclusive um dos principais fatores pela última queda do valor da Bitcoin após declaração da China considerar transações com esse moeda ilegais.
Por isso em uma situação real, a utilização deste robô não seria a mais ideial podendo ocasionar perca de valores da carteira.
