---
path: qual-a-diferenca-entre-os-operadores-nullish-e-or-em-javascript
date: 2022-02-10T01:06:10.351Z
title: Qual a diferença entre os operadores Nullish (??) e OR (||) em JavaScript?
---
<!--StartFragment-->

Os operadores lógicos ?? e || são operadores que funcionam com condições, onde o operador OR (||) executa uma ação se o valor for verdadeiro, já o Nullish (??) executa apenas se o valor for igual a null ou undefined. Vamos entender isso na prática.

<!--EndFragment-->

<!--StartFragment-->

### Operador OR (||)

<!--EndFragment-->

<!--StartFragment-->

Temos uma variável com o nome valueA que recebe o número 0

<!--EndFragment-->

```javascript
let valueA = 0;
console.log(valueA || 'Usando ||');
```

<!--StartFragment-->

Sabemos que o operador OR (||) executa se o valor for verdadeiro, pensando nisso deixo uma pergunta simples, o valor 0 é true ou false?

<!--EndFragment-->

```javascript
console.log(Boolean(0));
//false
```

<!--StartFragment-->

Temos a resposta, é falso. Com essa informação sabemos que o código anterior exibirá 'Usando ||' e não a variável que recebe à esquerda.

<!--EndFragment-->

<!--StartFragment-->

### Operador Nullish (??)

<!--EndFragment-->

<!--StartFragment-->

Agora para entendermos o operador Nullish (??) fica muito fácil, ele só será executado se o valor à esquerda for null ou undefined.

<!--EndFragment-->

```javascript
let valueA = undefined;
console.log(valueA ?? 'Usando ??'); //Usando ??
```

<!--StartFragment-->

Se a variável valueA receber undefined ou null o valor exibido no log será ‘Usando ??’ caso contrário será o valor da variável, veja outro exemplo pra ficar mais claro:

<!--EndFragment-->

```javascript
let valueA = 'Academia';
```

<!--StartFragment-->

A variável recebe uma string Academia, logo será exibida no log:

<!--EndFragment-->

```javascript
console.log(valueA ?? 'Usando ??');
//Academia
```

<!--EndFragment-->

<!--StartFragment-->

### Qual a diferença entre o operador Nullish (??) e o operador OR (||)?

<!--EndFragment-->

<!--StartFragment-->

O operador Nullish (??) será executado apenas se o valor a esquerda for null ou undefined, enquanto o operador OR (||) será executado quando o valor for true.

<!--EndFragment-->

<!--StartFragment-->

### Quando usar Nullish (??) ou OR (||)?

<!--EndFragment-->

<!--StartFragment-->

Depois que entendemos a diferença entre os dois fica bem tranquilo responder essa pergunta, vamos para o código que é o melhor lugar para entender melhor:

<!--EndFragment-->

```javascript
let valueA = '';
```

<!--EndFragment-->

<!--StartFragment-->

Agora a variável valueA recebe uma string vazia, logo sabemos que uma string vazia é false:

<!--EndFragment-->

```javascript
console.log(Boolean('')) //false
```

```javascript
let valueA = '';
console.log(valueA || 'Usando ||'); // Usando ||
console.log(valueA ?? 'Usando ??'); // Nada será exibido pois é uma string vazia
```

* <!--StartFragment-->

  Use o operador Nullish (??) quando você quiser executar uma ação em que o valor à esquerda for igual a null ou undefined.

  <!--EndFragment-->
* <!--StartFragment--> Use o operador OR (||) quando você quiser executar uma ação em que o valor for igual a true.

  <!--EndFragment-->