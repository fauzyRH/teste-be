# TESTE MELHOR ENVIO!

## O Teste

O teste consiste em duas etapas: implementação de transportadora e criação de API.

## Primeira Etapa: Implementação de Transportadora

  Fazer a importação das tabelas de preços dos serviços "Econômico" e "Expresso" da "Melhor Transportadora". As tabelas encontram-se no diretório “melhor-transportadora” no repositório.

### Regras da Transportadora:


|                  | Mínimo | Máximo (Econômico) | Máximo (Expresso) |
|------------------|--------|--------------------|-------------------|
| Altura(cm)       | 2      | 105                | 105               |
| Largura(cm)      | 11     | 105                | 105               |
| Comprimento (cm) | 16     | 105                | 105               |
| Peso (Kg)        | 1      | 30                 | 30                |
| Seguro (R$)      | 17,00  | 3.000,00           | 10.000,00         |


O valor de um frete varia conforme o peso do objeto enviado e o trecho onde ele está sendo enviado. 

Nas tabelas em anexo (serviços econômico e expresso, da Melhor Transportadora), temos a relação de preços para diversas faixas de peso, para todos os trechos nacionais possíveis.
Uma faixa de peso é um intervalo em quilos, por exemplo, de zero a 500 gramas. Ou de 500g a 1kg. Um aumento de peso do objeto apenas altera o preço do seu frete se esse acréscimo de peso fizer com que se passe a usar outra faixa de peso. Por exemplo, se um serviço tem as faixas de peso “0g a 500g” e “500g a 1Kg”, um objeto com 300g, 302g, ou 499g, terá o mesmo custo de frete.

Um trecho é o conjunto de origem e destino. Por exemplo, podemos ter o trecho “origem: 96040760 destino: 12233004”. 
Objetos com pesos diferentes, enviados em um mesmo trecho, podem ter preços de frete diferentes. Objetos enviados no mesmo trecho, com o mesmo peso (e mesmos serviços adicionais), devem ter o preço igual. Objetos de mesmo peso, mas enviados em trechos diferentes, podem ter preços de frete diferentes.

Para calcular um preço usando a tabela da Melhor Transportadora, primeiro se descobre qual a letra do tipo de trecho nós estamos calculando (por exemplo, para trecho local, letra “L”). No campo de instruções da tabela de preços explica como fazer isso. Depois vemos na matriz origem-destino qual o número do trecho que nós temos. Juntando a letra e o número do trecho, podemos ver em qual coluna da tabela de preços está o valor (ex: L1). Depois disso, usando o peso do objeto descobrimos o preço do frete, selecionando a linha da tabela de preços (ex: coluna L1, linha até 1Kg).

Como você já deve ter percebido, para fazer o cálculo do frete será preciso descobrir o estado e cidade de cada cep, bem como se aquela cidade é capital ou não. Para fazer isso, você pode usar a seguinte api: **https://location.melhorenvio.com.br/[cep]**.

## Segunda Etapa: API de cotação de frete

Desenvolver uma API para cotar os serviços da Melhor Transportadora.

### Entrada:  
 * CEP de Origem  
 * CEP de Destino  
 * Largura  
 * Altura  
 * Comprimento
 * Peso  
 * Valor Segurado  
 * Serviços adicionais  
	 * AR
	 * Mão Própria

### Saída:
 * Nome do Serviço  
 * Valor  

**Caso não retorne nenhum serviço informar o motivo.**



## Plus: Calculadora de frete

Utilizando a API desenvolvida na segunda etapa, crie sua calculadora de fretes.

#### Escolha alguma das tecnologias abaixo para desenvolver:  
 * MySql 5.7
 * PHP >= 7
 * Laravel 5.5
 * Node
 * Mongo DB
 * Go Lang

### Fazer a criação de um README.md com a documentação para rodar o projeto desenvolvido e para cotação na API.
