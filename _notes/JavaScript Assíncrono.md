---
title: JavaScript Assíncrono
---

- Como as APIs da Web geralmente fornecem dados de forma assíncrona, aprender como lidar com o resultado de ações assíncronas é uma parte essencial de ser um desenvolvedor de JavaScript.
	- Você deve saber como o ambiente do host usa o loop de eventos (Event Loop) para lidar com a ordem de execução do código com a pilha e a fila.
	- Deve saber das três maneiras de lidar com o sucesso ou a falha de um evento assíncrono, com retornos de chamada (callback), promessas (promises) e funções `async` e sintaxe `await`.
	- Usar a [[Fetch API]] para lidar com ações assíncronas.
- O código JavaScript que não usa APIs da Web assíncronas será executado de maneira síncrona - um de cada vez, sequencialmente.
- Quando uma API da Web assíncrona é usada, as regras se tornam mais complicadas. Uma API integrada com a qual você pode testar isso é `setTimeout`, que define um cronômetro e executa uma ação após um determinado período de tempo. `setTimeout` precisa ser assíncrono, caso contrário, todo o navegador permaneceria congelado durante a espera, o que resultaria em uma experiência do usuário ruim.
- Se você definir o tempo limite para zero segundos ou cinco minutos, não fará diferença pois o console.log chamado pelo código assíncrono será executada após as funções síncronas de nível superior. Isso acontece porque o ambiente de host JavaScript, neste caso o navegador, usa um conceito chamado loop de eventos para lidar com a simultaneidade, ou eventos paralelos. Como o JavaScript só pode executar uma instrução por vez, ele precisa que o loop de eventos seja informado de quando executar cada instrução específica. O loop de eventos lida com isso com os conceitos de **pilha** e **fila**.

## Pilha e Fila
- Como o loop de eventos usa a pilha e a fila para lidar com a ordem de execução do código.
- A pilha, ou pilha de chamadas, mantém o estado de qual função está em execução no momento. Se você não está familiarizado com o conceito de pilha, pode imaginá-la como um array com as propriedades “Último a entrar, primeiro a sair” (LIFO), o que significa que você só pode adicionar ou remover itens do final da pilha.
- A fila , também conhecida como fila de mensagens ou fila de tarefas, é uma área de espera para funções. Sempre que a pilha de chamadas estiver vazia, o loop de eventos verificará se há mensagens em espera na fila, começando pela mensagem mais antiga. Assim que encontrar uma, ele o adicionará à pilha, que executará a função na mensagem.
	- Há também outra fila chamada fila de trabalho ou fila de microtarefa que lida com promessas. Microtarefas como promessas são tratadas com uma prioridade mais alta doque macrotarefas como `setTimeout`.
- Agora você sabe como o loop de eventos usa a pilha e a fila para lidar com a ordem de execução do código. A próxima tarefa é descobrir como controlar a ordem de execução em seu código. Para fazer isso, primeiro você aprenderá sobre a maneira original de garantir que o código assíncrono seja tratado corretamente pelo loop de eventos: funções de retorno de chamada (callback).

## Callback
- Callback é o comportamento de uma função sendo passada como argumento para outra função. Basicamente, é um tipo de função que só é executada após o processamento de outra função. Na linguagem JavaScript, quando uma função é passada como um argumento de outra, ela é, então, chamada de callback.
- Abaixo há um exemplo simples, quando o botão for clickado, então é executado a função ou chamada de retorno.

``` js
const button = document.querySelector("button");
const handleClick = () => {  //lidando com o click
//instruções
}
//handleClick como callback
button.addEventListener("click", handleClick)
```

- Usa-se callbacks para lidar com tarefas assíncronas. As funções de retorno de chamada não têm sintaxe especial; eles são apenas uma função que foi passada como um argumento para outra função.
- As funções de retorno de chamada são uma forma eficaz de garantir a execução atrasada de uma função até que outra seja concluída e retorne com os dados. No entanto, devido à natureza aninhada dos retornos de chamada, o código pode ficar confuso se você tiver muitas solicitações assíncronas consecutivas que dependem umas das outras. Isso foi uma grande frustração para os desenvolvedores de JavaScript no início e, como resultado, o código que contém callbacks aninhados costuma ser chamado de "pirâmide da desgraça" ou "inferno de callback".
- Na prática, com código assíncrono do mundo real, isso pode ficar muito mais complicado. Provavelmente, você precisará fazer o tratamento de erros no código assíncrono e, em seguida, passar alguns dados de cada resposta para a próxima solicitação. Fazer isso com retornos de chamada tornará seu código difícil de ler e manter.
- Essa maneira de lidar com o código assíncrono é difícil de seguir. Como resultado, o conceito de promessas foi introduzido no ES6.

## Promises
- Uma promessa representa a conclusão de uma função assíncrona. É um objeto que pode retornar um valor no futuro. Ela cumpre o mesmo objetivo básico de uma função de retorno de chamada, mas com muitos recursos adicionais e uma sintaxe mais legível.
- Você pode inicializar uma promessa com a sintaxe `new Promise` e deve inicializá-la com uma função. A função que é passada para uma promessa tem parâmetros `resolve` e `reject`. As funções `resolve` e `reject` tratam do sucesso e da falha de uma operação, respectivamente.
	- `const promise = new Promise((resolve, reject) => {})`
- Uma promessa é um objeto que pode retornar um valor. Depois de ser preenchido com sucesso, o `value` passa de `undefined` a ser preenchido com dados.
- Uma promessa pode ter três estados possíveis: pendente, cumprida e rejeitada.
	- Pending - estado inicial antes de ser resolvido ou rejeitado
	- Fulfilled - operação bem-sucedida, promessa resolvida
	- Rejected - operação falhou, promessa foi rejeitada
- Depois de ser cumprida ou rejeitada, uma promessa é cumprida.
- As promessas têm um método chamado `then` que será executado depois que uma promessa for resolvida (`resolve`) no código. `then` retornará o valor da promessa como um parâmetro.
- As promessas também podem ser encadeadas para transmitir dados a mais de uma operação assíncrona. Se um valor for retornado em `then`, outro `then` pode ser adicionado que irá cumprir com o valor de retorno do anterior `then`.
- Como `then` pode ser encadeado, ele permite que o consumo de promessas pareça mais síncrono do que os retornos de chamada, já que não precisam ser aninhados. Isso permitirá um código mais legível que pode ser mantido e verificado com mais facilidade.
- frequentemente, com uma solicitação assíncrona, você também precisa lidar com um erro - se a API estiver inativa ou uma solicitação malformada ou não autorizada for enviada. Uma promessa deve ser capaz de lidar com os dois casos.
- As promessas podem ser confusas, tanto para novos desenvolvedores quanto para programadores experientes que nunca trabalharam em um ambiente assíncrono antes. No entanto, conforme mencionado, é muito mais comum consumir promessas do que criá-las. Normalmente, a API da Web de um navegador ou biblioteca de terceiros fornecerá a promessa e você só precisará consumi-la.
- Uma das APIs da Web mais úteis e freqüentemente usadas que retorna uma promessa é a API Fetch, que permite que você faça uma solicitação de recurso assíncrona em uma rede. `fetch` é um processo de duas partes e, portanto, requer encadeamento `then`.

## Funções `async` e `await`
- Embora usar `then` para lidar com ações assíncronas seja mais fácil de seguir do que a pirâmide de retornos de chamada, alguns desenvolvedores ainda preferem um formato síncrono de escrever código assíncrono. Para atender a essa necessidade, ECMAScript 2016 (ES7) introduziu as funções `async` e a palavra-chave `await` para tornar mais fácil trabalhar com promessas.
- Uma função `async` permite que você trate o código assíncrono de uma maneira que parece síncrona. Funções `async` ainda usam promessas por baixo do capô, mas têm uma sintaxe JavaScript mais tradicional.
- Você pode criar uma função `async` adicionando a palavra-chave `async` antes de uma função:
- Embora essa função ainda não esteja tratando de nada assíncrono, ela se comporta de maneira diferente de uma função tradicional. Se você executar a função, verá que ela retorna uma promessa com um `PromiseStatus` e em `PromiseValue` vez de um valor de retorno.
- Isso significa que você pode lidar com uma função assíncrona com `then` da mesma forma que faria com uma promessa.
- Uma função async pode manipular uma promessa chamada dentro dela usando o `await` operador. `await` pode ser usado dentro de uma função `async` e irá esperar até que uma promessa seja estabelecida antes de executar o código designado.
- O código JavaScript assíncrono moderno é mais frequentemente tratado com a sintaxe `async/await`, mas é importante ter um conhecimento prático de como as promessas funcionam, especialmente porque as promessas são capazes de recursos adicionais que não podem ser tratados com `async/ await`, como combinar promessas com `Promise.all()`.

---

- [Understanding the Event Loop, Callbacks, Promises, and Async/Await in JavaScript | DigitalOcean](https://www.digitalocean.com/community/tutorials/understanding-the-event-loop-callbacks-promises-and-async-await-in-javascript)
- [Entendendo funções callback em JavaScript by Victor F. Dos Santos TOTVS Developers - Medium](https://medium.com/totvsdevelopers/entendendo-fun%C3%A7%C3%B5es-callback-em-javascript-7b500dc7fa22)
- [Callback no JavaScript - YouTube](https://www.youtube.com/watch?v=0haWgdHFuJw)