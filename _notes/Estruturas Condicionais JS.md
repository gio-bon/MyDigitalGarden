---
title: Estruturas Condicionais JS
---

## `else` `else if` `else`

``` javascript
if (condicao) {
// código para executar caso a condição seja verdadeira
} else if (outraCondicao) {
// senão, executar este código caso outra condição seja verdadeira
} else {
// senão, executar este código
}
```

## `switch` `case`
- Bom para comparações de muitos valores
- Fará comparações de tipo e valor (`===`)
- Sempre precisará de um `default`
- 
``` javascript
  switch (expression) {
  case choice1:
	// código para executar
	break;
	case choice2:
	// código para executar
	break;
  // podem ser incluídos quantos casos precisar.
	default:
  // se não for nenhum caso, executa este caso
  }
```