---
title: Uso de Markdown para dar formato a Microsoft Flow aprobaciones | Microsoft Docs
description: Aprenda a usar Markdown para dar formato a las solicitudes de aprobación de Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: gcorvera
manager: kfile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/23/2018
ms.author: gcorvera
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b82ac7c53c8c018b5e61011e4c1d8b9cdabe9747
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545320"
---
# <a name="use-markdown-in-microsoft-flow-approval-requests"></a>Uso de Markdown en solicitudes de aprobación de Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

En este artículo se enseña cómo usar la sintaxis de [Markdown](https://en.wikipedia.org/wiki/Markdown) para agregar tablas y formato enriquecido a las solicitudes de aprobación.

## <a name="headers"></a>Encabezados

Estructure sus comentarios con encabezados. Los encabezados segmentan comentarios más largos, lo que facilita su lectura.

Iniciar una línea con un carácter hash `#` para establecer un encabezado. Organice sus comentarios con subtítulos iniciando una línea con caracteres hash adicionales, por ejemplo `####`. Se admiten hasta seis niveles de encabezados.

**Ejemplo**

```Markdown
# This is a H1 header
## This is a H2 header
### This is a H3 header
#### This is a H4 header
##### This is a H5 header
```

**Da**

![Flujo de exportación](./media/approvals-markdown-support/mrkdown-headers.png)

## <a name="paragraphs-and-line-breaks"></a>Párrafos y saltos de línea

Facilite la lectura del texto dividiéndolo con párrafos o saltos de línea. Escriba dos espacios antes del salto de línea para comenzar un párrafo nuevo, o bien escriba dos saltos de línea consecutivamente para comenzar un párrafo nuevo.   
   
**Ejemplo**

Agregue líneas entre el texto con la tecla entrar.
De este modo, el texto se espacia mejor y es más fácil de leer.

**Resultado:**    
Agregue líneas entre el texto con la tecla entrar.      
De este modo, el texto se espacia mejor y es más fácil de leer.


**Ejemplo 2**

Agregue dos espacios antes del final de la línea. (espacio, espacio)     
Esto agrega espacio entre los párrafos.

**Da**  
Agregue dos espacios antes del final de la línea.   

Esto agrega espacio entre los párrafos.
  

## <a name="lists"></a>Coge

Organice los elementos relacionados con listas. Puede Agregar listas ordenadas con números o listas desordenadas con solo viñetas.

Las listas ordenadas comienzan con un número seguido de un punto para cada elemento de la lista. Las listas desordenadas comienzan con un `*`. Comienza cada elemento de la lista en una nueva línea. En un archivo o widget de Markdown, escriba dos espacios antes del salto de línea para comenzar un párrafo nuevo, o bien escriba dos saltos de línea consecutivamente para comenzar un párrafo nuevo.   

### <a name="ordered-or-numbered-lists"></a>Listas ordenadas o numeradas

**Ejemplo**

```Markdown
0. First item.
0. Second item.
0. Third item.
```

**Da**

1. Primer elemento.
2. Segundo elemento.
3. Tercer elemento.

### <a name="bullet-lists"></a>Listas de viñetas

**Ejemplo**

<pre>

- Item 1
- Item 2
- Item 3

</pre>

**Da**

- Elemento 1
- Elemento 2
- Elemento 3

### <a name="nested-lists"></a>Listas anidadas

**Ejemplo**
<pre>

1. First item.
   - Item 1
   - Item 2
   - Item 3
1. Second item.
   - Nested item 1
   - Nested item 2
   - Nested item 3

</pre>

**Da**  

1. Primer elemento.

    - Elemento 1
    - Elemento 2
    - Elemento 3
2. Segundo elemento.
    - Elemento anidado 1
    - Elemento anidado 2
    - Elemento anidado 3


## <a name="links"></a>Vínculos

Las direcciones URL HTTP y HTTPS se formatean automáticamente como vínculos. 

Puede establecer hipervínculos de texto para la dirección URL mediante la sintaxis de vínculo de Markdown estándar:

```Markdown
[Link Text](Link URL)
```

**Ejemplo**
<pre>
&#91;Microsoft Flow](https://flow.microsoft.com)
</pre>

**Da**

[Microsoft Flow](https://flow.microsoft.com)

### <a name="anchor-links"></a>Vínculos delimitadores

Los identificadores de delimitador se asignan a todos los encabezados cuando se representan como HTML. El identificador es el texto del título, con los espacios reemplazados por guiones (-) y todo en minúsculas.

**Ejemplo**

<pre>
###Link to a heading in the page
</pre>

<br/>

**Da**

La sintaxis de un vínculo de delimitador a una sección...

<pre>
[Link to a heading in the page](#link-to-a-heading-in-the-page)
</pre> 
<br/>
El identificador está todo en minúsculas y el vínculo distingue entre mayúsculas y minúsculas, por lo que debe asegurarse de usar minúsculas, aunque el propio encabezado Use mayúsculas.


## <a name="tables"></a>Tablas

Organice los datos estructurados con tablas. 

- Colocar cada fila de la tabla en su propia línea 
- Separe las celdas de la tabla mediante el carácter de barra vertical `|` 
- Las dos primeras líneas de una tabla establecen los encabezados de columna y la alineación de los elementos de la tabla.
- Use dos puntos (`:`) al dividir el encabezado y el cuerpo de las tablas para especificar la alineación de las columnas (izquierda, centro, derecha). 
- Para iniciar una nueva línea, use la etiqueta de salto HTML (`<br/>`) (funciona dentro de un wiki, pero no en otro lugar)  
- Asegúrese de terminar cada fila con un CR o LF. 

**Ejemplo**

```
| Heading 1 | Heading 2 | Heading 3 |  
|-----------|:-----------:|-----------:|  
| Cell A1 | Cell A2 | Cell A3 |  
| Cell B1 | Cell B2 | Cell B3<br/>second line of text |  
```




**Da**  

| Título 1 | Encabezado 2 | Título 3 |  
|-----------|:---------:|-----------:|  
| Celda a1 | Celda a2 | Celda a3 |  
| Celda B1 | Celda B2 | Celda B3<br/>segunda línea de texto |  

 
## <a name="emphasis-bold-italics-strikethrough"></a>Énfasis (negrita, cursiva, tachado)  

Puede resaltar el texto aplicando negrita, cursiva o tachado a los caracteres: 
- Para aplicar cursiva: rodea el texto con un asterisco `*` o un carácter de subrayado `_`   
- Para aplicar negrita: rodee el texto con asteriscos dobles `**`.    
- Para aplicar el tachado: rodee el texto con caracteres de tilde doble `~~`.   

Combine estos elementos para aplicar varios resaltados a texto.    

**Ejemplo**

<pre>
Use _emphasis_ in comments to express **strong** opinions and point out ~~corrections~~ 
**_Bold, italicized text_**  
**~~Bold, strike-through text~~**
</pre>

<br/>

**Da**

Use _comentarios_ para expresar opiniones **sólidas** y señale las <s>correcciones</s>   
**_Negrita,  de texto en cursiva_**  
**~~Negrita, texto tachado~~**  


## <a name="special-characters"></a>Caracteres especiales

<table width="650px">
<tbody valign="top">
<tr>
<th width="300px">Sintáctica</th>
<th width="350px">Ejemplo/notas</th>
</tr>



<tr>
<td>
<p>Para insertar uno de los siguientes caracteres, prefijo con una barra diagonal inversa:</p>

<p style="margin-bottom:2px;">```\   backslash ``` </p>
<p style="margin-bottom:2px;"><code>\`</code>   `backtick`</p>
<p style="margin-bottom:2px;">```_   underscore  ```</p>
<p style="margin-bottom:2px;">```{}  curly braces  ``` </p>
<p style="margin-bottom:2px;">```[]  square brackets ```</p>
<p style="margin-bottom:2px;">```()  parentheses  ```</p>
<p style="margin-bottom:2px;">```#   hash mark  ``` </p>
<p style="margin-bottom:2px;">```+   plus sign  ```</p>
<p style="margin-bottom:2px;">```-   minus sign (hyphen) ```</p>
<p style="margin-bottom:2px;">```.   dot  ``` </p>
<p style="margin-bottom:2px;">```!   exclamation mark ```</p>


</td>
<td>Algunos ejemplos de cómo insertar caracteres especiales
<p>Escriba ```\\``` para obtener \\ </p>
<p>Escriba ```\_``` para obtener _ </p>
<p>Escriba ```\#``` para obtener \# </p>
<p>Escriba ```\(``` para obtener \( </p>
<p>Escriba ```\.``` para obtener \. </p>
<p>Escriba ```\!``` para obtener \! </p>
</td>
</tr>

</tbody>
</table>
