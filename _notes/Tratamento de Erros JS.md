---
title: Tratamento de Erros JS
---

Ao executar o código JavaScript, podem ocorrer erros diferentes. Os erros podem ser erros de codificação cometidos pelo programador, erros devido a entrada incorreta e outras coisas imprevisíveis.

O Ecmascript Error é um tipo de erro em tempo de execução, já o DOM Exception é um erro referente a DOM.
- A composição do Ecmascript Error é => mensagem, nome, linha e call stack

### `try` `catch` `finally`
- `try` permite definir um bloco de código a ser testado quanto a erros enquanto ele está sendo executado.
- `catch` permite definir um bloco de código a ser executado, se ocorrer um erro no bloco `try`.
- `finally` permite executar o código, após tentar e capturar, independentemente do resultado.

``` js
  try {
	tryCode - Block of code to try
	//Requeridos. Bloco de código a ser testado para erros enquanto está sendo executado
  }
  catch(err) { //Especifica uma variável local que se refere ao erro. 
	catchCode - Block of code to handle errors 
	//Opcional. Bloco de código a ser executado, caso ocorra um erro no bloco try. Se nenhum erro ocorrer, este bloco de código nunca é executado
  }
  finally {
	finallyCode - Block of code to be executed regardless of the try / catch result
	//Opcional. Bloco de código a ser executado independentemente do resultado de tentativa / captura
  }
```

### `thow`
A instrução `throw` permite que você crie um erro personalizado.

``` js
if (typeof string != 'string') throw "string inválida";
```

### `error`
- [ ] TODO
``` js
//new Error(message, fileName, lineNumber)
let meuError = new Error('Muitos erros meou!');
throw meuError;
```