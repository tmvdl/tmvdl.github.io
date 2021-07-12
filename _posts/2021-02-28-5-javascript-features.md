---
title: '5 recursos de JavaScript que foram introduzidos no ES2021'
date: 2021-02-28
excerpt: ""
permalink: /posts/2021/02/recursos-javascript-es2021
tags:
  - in portuguese
  - javascript
  - es2021
---

# 5 recursos de JavaScript que foram introduzidos no ES2021

Desde que as especificações EcmaScript foram alteradas para serem lançadas em atualizações anuais, passamos a adorar as atualizações anuais de novos recursos que podemos usar em JavaScript. As atualizações que podemos ver no ES2021 são simples, como Logical assignment operators, Promise.any e Numeric Separators sendo os destaques.

Nesta postagem, veremos alguns dos novos recursos e falaremos sobre como eles podem ajudá você a escrever um código JavaScript melhor e mais sustentável.

## 1. String.prototype.replaceAll

O primeiro novo recurso que quero abordar é o String.prototype.replaceAll() que substitui todas as ocorrências de uma string por outro valor de string.

Antes do .replaceAll(), o método .replace() apenas substituía a primeira instância de uma combinação por outro padrão. Agora, quando usarmos replaceAll(), vemos todas as ocorrências sendo substituídas.

```js
const catPhrase = 'A cat sat on the cat mat';
const dogPhrase = catPhrase.replaceAll('cat', 'dog');
console.log(dogPhrase); // A dog sat on the dog mat
```

## 2. Promise.any

O método Promise.any recebe um array de Promises e retorna assim que a primeira for finalizada com sucesso.

Isso é muito semelhante ao método Promise.race, no entanto, tem uma diferença fundamental. Enquanto Promise.race retornará se alguma das promessas for cumprida (Settled), Promise.any retornará somente se uma das promessas for cumprida (Fulfilled).

A diferença entre Settled e Fulfilled é que para uma promessa ser cumprida (Fulfilled), não deve haver erro, mas para uma promessa a ser cumprida (Settled), ela só precisa retornar, independentemente de a resposta ser um sucesso ou um erro.

Usar o Promise.any é muito simples. Basta passar para ele um array de promessas que você espera resolver como visto aqui:

```js
const promise = (delay) => new Promise((resolve) => {
    setTimeout(() => resolve(`${delay} milliseconds`), delay);
});
const promises = [promise(50), promise(40), promise(30)];
const resolved = await Promise.any(promises);
console.log(resolved); // 30 milliseconds
```

Neste exemplo, a terceira promessa seria resolvida primeiro, pois tem apenas um tempo limite de 30 milissegundos.

## 3. Logical assignment operators

Os Logical assignment operators fornecem uma combinação de operadores lógicos e expressões de atribuição. ES2021 apresenta dois desses novos operadores:

* Logical assignment operators OU
* Logical assignment operators E

### Logical OR assignment

Logical OR assignment fornece um bom atalho para atribuirmos um valor alternativo se o valor inicial estiver vazio. A maneira mais fácil de explicar como isso funciona é fornecer alguns exemplos.

No primeiro exemplo abaixo, como `a` é truthy, `a` permanece igual a "hello".

```js
let a = "hello";
a ||= 10;
console.log(a); // hello
```

No segundo exemplo, encontrado abaixo, como `b` é falsey, o valor é definido como "world".

```js
let b = "";
b ||= "world";
console.log(b); // world
```

### Logical AND assignment

Logical AND assignment fornece um bom atalho para substituirmos um valor se um valor anterior foi definido. A maneira mais fácil de explicar como isso funciona é fornecer alguns exemplos.

No primeiro exemplo abaixo, como `a` é truthy, `a` é então definido como "hello".

```js
let a = true;
a &&= "hello";
console.log(a); hello
```

No segundo exemplo abaixo, como `b` é falsey, `b` permanece igual para o false.

```js
let b = false;
b &&= "world";
console.log(b); false
```

## 4. Numeric Separators

Numeric Separators apresenta os separadores para literais numéricos com o objetivo de torná-los mais fáceis de ler. Antes do ES2021, escreveríamos nosso valor em milhões da seguinte forma:

```js
const billion = 1000000000
```

O problema com isso é que seria muito fácil adicionar um zero extra ou perder um. Com o Numeric Separators, podemos tornar o número muito mais fácil de ler, usando underscores.

```js
const billion = 1_000_000_000
```

## 5. Métodos e campos privados

Quando ES2015 introduziu Classes em JavaScript, fiquei desapontado quando descobri que eles não tinham a capacidade de os autores de bibliotecas definirem métodos privados. Como autor de uma biblioteca JavaScript, gostei da ideia de que, usando Classes, seria capaz de manter meus métodos internos, internos.

ES2021 finalmente corrige esta falta introduzindo métodos privados e campos privados. Para indicar que um método ou campo é privado, você simplesmente precisa usar um hash (#) antes do nome. O exemplo a seguir foi retirado do [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/Private_class_fields).

```js
class ClassWithPrivateField {
  #privateField
}

class ClassWithPrivateMethod {
  #privateMethod() {
    return 'hello world'
  }
}

class ClassWithPrivateStaticField {
  static #PRIVATE_STATIC_FIELD
}
```

## Resumindo

Os recursos que apresentei hoje são aqueles que você provavelmente usará todos os dias.

As melhorias que vimos no JavaScript desde o ES6 têm sido incríveis e eu adoro ver todos esses novos recursos chegando para nos ajudar.
