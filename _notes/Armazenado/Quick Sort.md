---
title : Quick Sort
---

![](https://upload.wikimedia.org/wikipedia/commons/9/9c/Quicksort-example.gif)

Assim como o [[Merge Sort]], o quicksort usa divisão e conquista, portanto ele é um algoritmo recursivo.

- Escolha um elemento para servir como pivô.
- Ordene o array de forma que todos os elementos menores que o pivô fiquem à esquerda e todos os elementos maiores que o pivô fiquem à direita.
- Execute o algoritmo recursivamente, levando em consideração o pivô anterior para subdividir adequadamente os arrays esquerdo e direito. 

Implementação em JavaScript:

```js
const arr = [6, 2, 5, 3, 8, 7, 1, 4];

const quickSort = (arr, start, end) => {

  if(start < end) {
    let pivot = partition(arr, start, end);
    // Estas são as chamadas recursivas do quickSort
    quickSort(arr, start, pivot - 1);
    quickSort(arr, pivot + 1, end);
  } 

}

const partition = (arr, start, end) => { 
  let pivot = end;
  let i = start - 1,
      j = start;

  while (j < pivot) {
    if (arr[j] > arr[pivot]) {
      j++;
    }
    else {
      i++;
      swap(arr, j, i);
      j++;
    }

  }

  swap(arr, i + 1, pivot);
  return i + 1;
}

const swap = (arr, firstIndex, secondIndex) => {
  let temp = arr[firstIndex];
  arr[firstIndex] = arr[secondIndex];
  arr[secondIndex] = temp;
}

quickSort(arr, 0, arr.length - 1);
console.log(arr);
```