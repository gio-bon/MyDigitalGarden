---
title : Computer Science The Mechanization of Abstraction - Aho and Ullman
---
Fonte: [Aho/Ullman Foundations of Computer Science](http://infolab.stanford.edu/~ullman/focs.html)

## Capítulo 1

Though it is a new field, computer science already touches virtually every aspect of human endeavor (esforço humano). Its impact on society is seen in the proliferation of computers, information systems, text editors, spreadsheets, and all of the wonderful application programs that have been developed to make computers easier to use and people more productive. An important part of the field deals with (lida com) how to make programming easier and software more reliable. But fundamentally, computer science is a science of abstraction — creating the right model for thinking about a problem and devising (elaborando) the appropriate mechanizable techniques to solve it.

Every other science deals with the universe as it is. The physicist’s job (físico), for example, is to understand how the world works, not to invent a world in which physical laws would be simpler or more pleasant (agradáveis) to follow. Computer scientists, on the other hand, must create abstractions of real-world problems that can be understood by computer users and, at the same time, that can be represented and manipulated inside a computer.

Sometimes the process of abstraction is simple. For example, we can model the behavior of the electronic circuits used to build computers quite well by an (muito bem por uma) abstraction called “propositional logic.” The modeling of circuits by logical expressions is not exact; it simplifies, or abstracts away, many details — such as (tais como) the time it takes (que leva) for electrons to flow (fluam) through (através dos) circuits and gates. Nevertheless (no entanto), the propositional logic model is good enough to help us design computer circuits well.

The reader may cringe at the word (se encolher com a palavra) “abstraction”, because we all have the intuition that abstract things are hard to understand; for example, abstract algebra (the study of groups, rings, and the like (e afins)) is generally considered harder than the (mais difícil do que a) algebra we learned in high school. However, abstraction in the sense we use it implies simplification, the replacement (substituição) of a complex and detailed real-world situation by an understandable model within which (dentro do qual) we can solve a problem. That is (Ou seja), we “abstract away” (abstraímos) the details whose (cujo) effect on the solution to a problem is minimal or non existent, there by creating a model that lets us deal with (lidar com) the essence of the problem.

Often, finding a good abstraction can be quite difficult because we are forced to confront the fundamental limitations on the tasks computers can perform (realizar) and the speed with which computers can perform those tasks. In the early days (primeiros dias) of computer science, some optimists believed that robots would soon have (em breve teriam) the prodigious capability and versatility of the Star Wars robot C3PO. Since then we have learned that in order to have (a fim de ter) “intelligent” behavior on the part (por parte) of a computer (or robot), we need to provide that computer with a model of the world that is (que é) essentially as detailed as (tão detalhada quanto) that possessed by humans, including not only facts (“Sally’s phone number is 555-1234”), but principles and relationships (“If you drop something, it usually falls downward (para baixo)”).

We have made much progress on this problem of “knowledge representation.” We have devised (desenvolvemos) abstractions that can be used to help build programs that do certain kinds of reasoning (raciocínio).

Another useful abstraction is formal logic, which allows us to manipulate facts by applying rules of inference, such as “If x is a cat and y is the mother of x, then y is a cat.” Nevertheless, progress on modeling, or abstracting, the real world or significant pieces there of (dele) remains a fundamental challenge of computer science, one that is not likely (um que não é provável) to be solved completely in the near future.

~~This book will introduce the reader, who is assumed to have a working knowledge of the programming language ANSI C~~, to the principal ideas and concerns (preocupações) of computer science. The book emphasizes three important problem-solving tools:
- Data models, the abstractions used to describe problems. We have already mentioned two models: logic and graphs. We shall meet many others throughout this book (ao longo deste livro).
- Data structures, the programming-language constructs used to represent data models. For example, C provides built-in abstractions, such as structures and pointers, that allow us to construct data structures to represent complex abstractions such as graphs.
- Algorithms, the techniques used to obtain solutions by manipulating data as represented by the abstractions of a data model, by data structures, or by other means.

An algorithm is a precise and unambiguous specification of a sequence of steps that can be carried out (pode ser realizado) mechanically. The notation in which an algorithm is expressed can be any commonly understood language (linguagem comumente compreendida), but in computer science algorithms are most often expressed formally as programs in a programming language, or in an informal style as a sequence of programming language constructs intermingled with English language statements (ou em um estilo informal como uma seqüência de construções de linguagem de programação entremeadas com declarações em inglês). Most likely, you have already encountered several important algorithms while studying programming. For example, there are a number of algorithms for sorting the elements of an array, that is (ou seja), putting the elements in smallest-first order. There are clever searching algorithms such as binary search, which quickly finds a given element (um dado elemento) in a sorted array by repeatedly dividing in half the portion of the array in which the element could appear.

These, and many other “tricks” for solving common problems, are among (estão entre) the tools the computer scientist uses when designing programs. We shall study many such techniques in this book, including the important methods for sorting and searching. In addition, we shall (nós devemos) learn what makes one algorithm better than another. Frequently, the running time, or time taken by an algorithm measured as a function of the size of its input, is one important aspect of the “quality” of the algorithm.

Other aspects of algorithms are also important, particularly their simplicity. Ideally, an algorithm should be easy to understand and easy to turn into a (transformar-se em um) working program. Also, the resulting program should be understandable by a person reading the code that implements the algorithm. Unfortunately, our desires for a fast algorithm and a simple algorithm are often in conflict, and we must choose our algorithm wisely.

Data Models

Any mathematical concept can be termed (denominado) a data model. In computer science, a data model normally has two aspects:

- The values that objects can assume. For example, many data models contain objects that have integer values. This aspect of the data model is static; it tells us what values objects may take. The static part of a programming language’s data model is often called the type system.
- The operations on the data. For example, we normally apply operations such as addition to integers. This aspect of the model is dynamic; it tells us the ways in which we can change values and create new values.

Programming Language Data Models

Each programming language has its own data model, and these differ from one another, often in quite substantial ways. The basic principle under which most programming languages deal with (lida com) data is that each program has access to “boxes,” which we can think of as regions of storage. Each box has a type, such as int or char. We may store in a box any value of the correct type for that box. We often refer to the values that can be stored in boxes as data objects.

Algorithms and the Design of Programs

The study of data models, their properties, and their appropriate use is one pillar of computer science. A second, equally important pillar is the study of algorithms and their associated data structures. We need to know the best ways to perform common tasks, and we need to learn the principal techniques for designing good algorithms. Further, we need to understand how the use of data structures and algorithms fits into the process of creating useful programs. The themes of data models, algorithms, data structures, and their implementation in programs are interdependent, ~~and each appears many times throughout the book.~~