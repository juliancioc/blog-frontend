---
path: como-encontrar-o-maior-valor-em-um-array-de-objetos-com-javascript
date: 2022-03-02T01:18:23.210Z
title: Como encontrar o maior valor em um array de objetos com JavaScript
---
<!--StartFragment-->

Encontrar o maior valor dentro de um array é muito simples, mas e quando é um array de objetos?

Também não tem nenhum segredo, devemos apenas combinar o uso de Math, apply() e map().

Veja um exemplo na dica de hoje.

Em nosso cenário temos o seguinte array de objetos:

```javascript
`const cars = [
 { name: 'Civic LX 2015', value: 89500 },
 { name: 'HRV', value: 119000 },
 { name: 'Onix', value: 54000 }
]`
```

Um array com o nome *car* possui 3 objetos, cada objeto tem 2 propriedades *name* e *value*.

### Encontrando o maior valor

Para filtrar o array e retornar o carro com o maior preço, podemos fazer da seguinte forma:

```javascript
`const maxValue = Math.max.apply(Math, cars.map((item) => item.value))
console.log(maxValue) // 119000`
```

O código acima percorre todo o array e acessa a propriedade *value* dentro de cada objeto, retornando o *value* com maior valor.

### Vamos entender o que exatamente foi feito pra chegar até esse resultado

1. Primeiro usamos o objeto `Math`
2. Dentro do objeto `Math` acessamos a função `Math.max()`, essa função recebe uma sequência de números e retorna o maior valor
3. Agora que descobrimos que `Math.max()` retorna o maior valor, precisamos passar os números que queremos analisar para dentro dessa função
4. Pra chamar uma função a partir de `Math.max()` vamos usar o método `apply()`
5. O método `apply()` espera receber dois parâmetros e no nosso caso passamos `Math` e os valores que queremos analisar.
6. Para percorrer o array de cars e retornar os valores usamos o método `map()`

Em um artigo futuro vamos nos aprofundar mais no método `map()` ele é muito importante e muito usado para percorrer array e retornar um valor

E isso é tudo, até a próxima! :)

<!--EndFragment-->