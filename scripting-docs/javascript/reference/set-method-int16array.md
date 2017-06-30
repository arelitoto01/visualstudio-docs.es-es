---
title: "set (M&#233;todo, Int16Array) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: e35adfff-7052-4ef9-80be-3abbf8230e88
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# set (M&#233;todo, Int16Array)
Establece un valor o una matriz de valores.  
  
## Sintaxis  
  
```javascript  
int16Array.set(index, value);  
int16Array.set(array, offset);  
  
```  
  
## Parámetros  
 `index`  
 Índice de la ubicación que se va a establecer.  
  
 `value`  
 Valor que se va a establecer.  
  
 `array`  
 Matriz con o sin tipo de valores que se va a establecer.  
  
 `offset`  
 Índice de la matriz actual donde deben escribirse los valores.  
  
## Comentarios  
 Si la matriz de entrada es TypedArray, las dos matrices pueden utilizar el mismo ArrayBuffer subyacente.  En esta situación, los valores se establecen como si todos los datos se copiasen primero en un búfer temporal que no se solapa con ninguna de las matrices y, a continuación, los datos del búfer temporal se copiasen en la matriz actual.  
  
 Si el valor de sumar el desplazamiento más la longitud de la matriz especificada está fuera de intervalo del objeto TypedArray actual, se produce una excepción.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo establecer el primer elemento de la matriz.  
  
```javascript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Int16Array(buffer.byteLength / 2);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## Requisitos  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]