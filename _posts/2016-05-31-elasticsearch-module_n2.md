---
layout: post
title: 4. Optimizando los índices
usernames: [maira1001001, rosariosm]
tags: [elasticsearch, Query DSL, mapping]
---

En este módulo analizaremos los fundamentos en que se basa elasticsearch para realizar las búsquedas con el fin de comprender de qué manera se pueden optimizar los índices mediante la utilización de *mappings*. Luego, veremos varios ejemplos de de búsquedas utilizando el **Query DSL**, un lenguaje basado en JSON que define la forma en que se deben estructurar las consultas, dependiendo de qué se quiere buscar.

## Introducción al formato de las consultas

En el módulo anterior se introdujo una idea de cómo formular las consultas de búsqueda utilizando un JSON estructurado. En particular, vimos la cláusula `match` que permite encontrar documentos que contengan un valor particular en un campo particular. Este tipo de cláusulas, junto con `term` o `range` pertenecen a lo que se denomina **leaf queries** (o consultas hoja). Estas se pueden combinar para formar **compound queries** (consultas compuestas) => mejores resultados, flexibles, etc.

El comportamiento que tendrá la consulta dependerá de 

depende del context: con o sin score
*para que sirve el score
* matematica en el score
* a partir de lo anteiorr, introducir mapping. por je: definir titles, que palabras son importantes en el body, sacar tags html o utilizarlos para definir eestructuras, etc.
* hacer consultas con query dsl
