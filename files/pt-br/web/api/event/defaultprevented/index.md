---
title: Event.defaultPrevented
slug: Web/API/Event/defaultPrevented
---
{{ ApiRef("DOM") }}

### Resumo

Retorna um booleano que indica se ou não {{ domxref("event.preventDefault()") }} foi chamado no evento.

> **Nota:** Você deve usar isso em vez de a não-padrão, método desatualizado `getPreventDefault()` (ver {{ bug(691151) }}).

### Sintaxe

```
bool = event.defaultPrevented
```

### Exemplo

```
 if (e.defaultPrevented) {
   /* o padrão foi impedido */
 }
```

### Compatibilidade do navegador

{{Compat("api.Event.defaultPrevented")}}
