---
title: FileReader.onload
slug: Web/API/FileReader/load_event
tags:
  - Archivo
  - Controlador de Eventos
  - Lector de Archivos
  - Propiedad
  - Referencia
translation_of: Web/API/FileReader/onload
original_slug: Web/API/FileReader/onload
---
{{APIRef}}

La propiedad **`FileReader.onload`** contiene un controlador de evento ejecutado cuando {{event('load')}} es ejecutado, cuando el contenido es leído con [readAsArrayBuffer](/es/docs/Web/API/FileReader/readAsArrayBuffer), [readAsBinaryString](/es/docs/Web/API/FileReader/readAsBinaryString), [readAsDataURL](/es/docs/Web/API/FileReader/readAsDataURL) o [readAsText](/es/docs/Web/API/FileReader/readAsText) está habilitado.

## Ejemplo

```js
// Respuest desde un <input type="file" onchange="onChange(event)">
function onChange(event) {
  var file = event.target.files[0];
  var reader = new FileReader();
  reader.onload = function(event) {
    // El texto del archivo se mostrará por consola aquí
    console.log(event.target.result)
  };

  reader.readAsText(file);
}
```
