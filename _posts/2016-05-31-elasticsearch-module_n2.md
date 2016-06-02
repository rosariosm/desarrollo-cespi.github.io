---
layout: post
title: 4. Optimizando los índices
usernames: [maira1001001, rosariosm]
tags: [elasticsearch, Query DSL, mapping]
---

En este módulo analizaremos los fundamentos en que se basa elasticsearch para realizar las búsquedas con el fin de comprender de qué manera se pueden optimizar los índices mediante la utilización de *mappings*. Luego, veremos varios ejemplos de de búsquedas utilizando el **Query DSL**, un lenguaje basado en JSON que define la forma en que se deben estructurar las consultas, dependiendo de qué se quiere buscar.

## Introducción al formato de las consultas

En el módulo anterior se introdujo una idea de cómo formular las consultas de búsqueda utilizando un JSON estructurado. En particular, vimos la cláusula `match` que permite encontrar documentos que contengan un valor particular en un campo particular. Este tipo de cláusulas, junto con `term` o `range` pertenecen a lo que se denomina **leaf queries** (o consultas hoja). Estas se pueden combinar para formar **compound queries** (consultas compuestas). Estos elementos componen el **Query DSL**, un lenguaje poderoso y flexible para realizar búsquedas estructuradas, que será explicado con más detalle al final del módulo.

La forma en que las consultas son interpretadas depederá del contexto en el que se utilizan, pudiendo diferenciarse dos tipos: en el contexto de **filtro** los resultados deben o no matchear con lo  que se quiere buscar. Responden a la pregunta "¿Este documento concuerda con esta consulta ?", cuya respuesta puede ser *si* o *no*. En cambio, en un contexto de **consulta** los resultados se obtienen al calcular qué tanto se acerca a lo que se quiere buscar, es decir, se calula un *score*  que determina qué tanto se acerca ese resultado a la consulta original. Entender este concepto nos permitirá comprender cómo podemos mapear los indices para obtener mejores resultados de una forma eficiente.

## Scoring y Mapping 

Los resultados dentro del contexto de consulta se ordenan un *score* (número positivo en punto flotante) que representa su relevancia: cuando más grande, mayor será su relevancia. 


We’ve mentioned that, by default, results are returned in descending order of relevance. But what is relevance? How is it calculated?

The relevance score of each document is represented by a positive floating-point number called the _score. The higher the _score, the more relevant the document.

A query clause generates a _score for each document. How that score is calculated depends on the type of query clause. Different query clauses are used for different purposes: a fuzzy query might determine the _score by calculating how similar the spelling of the found word is to the original search term; a terms query would incorporate the percentage of terms that were found. However, what we usually mean by relevance is the algorithm that we use to calculate how similar the contents of a full-text field are to a full-text query string.

*para que sirve el score
* matematica en el score
* a partir de lo anteiorr, introducir mapping. por je: definir titles, que palabras son importantes en el body, sacar tags html o utilizarlos para definir eestructuras, etc.
* hacer consultas con query dsl
