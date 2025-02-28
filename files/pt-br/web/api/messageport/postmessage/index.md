---
title: MessagePort.postMessage()
slug: Web/API/MessagePort/postMessage
---
{{APIRef("HTML DOM")}}

O método **`postMessage()`** da interface {{domxref("MessagePort")}} envia uma mensagem da porta e opcionalmente transfere a propriedade do objeto para outros contexto de navegação.

{{AvailableInWorkers}}

## Syntax

```
port.postMessage(message, transferList);
```

### Returns

Vazio.

### Parameters

- message
  - : A mensagem que você quer enviar atravéz do canal. Esta mensagem pode ser de qualquer tipo de dados basico. Multiplos items podem ser enviados com diferentestes tipos de dados como em um [Array](/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array).
- transferList {{optional_inline}}
  - : {{domxref("Transferable")}} objects to be transferred — these objects have their ownership transferred to the receiving browsing context, so are no longer usable by the sending browsing context.

## Example

In the following code block, you can see a new channel being created using the {{domxref("MessageChannel()", "MessageChannel.MessageChannel")}} constructor. When the IFrame has loaded, we pass {{domxref("MessageChannel.port2")}} to the IFrame using {{domxref("window.postMessage")}} along with a message. The `handleMessage` handler then responds to a message being sent back from the IFrame using `onmessage`, putting it into a paragraph — {{domxref("MessageChannel.port1")}} is listened to, to check when the message arrives.

```js
var channel = new MessageChannel();
var para = document.querySelector('p');

var ifr = document.querySelector('iframe');
var otherWindow = ifr.contentWindow;

ifr.addEventListener("load", iframeLoaded, false);

function iframeLoaded() {
  otherWindow.postMessage('Hello from the main page!', '*', [channel.port2]);
}

channel.port1.onmessage = handleMessage;
function handleMessage(e) {
  para.innerHTML = e.data;
}
```

For a full working example, see our [channel messaging basic demo](https://github.com/mdn/dom-examples/tree/master/channel-messaging-basic) on Github ([run it live too](https://mdn.github.io/dom-examples/channel-messaging-basic/)).

## Specifications

| Specification                                                                                                                | Status                           | Comment |
| ---------------------------------------------------------------------------------------------------------------------------- | -------------------------------- | ------- |
| {{SpecName('HTML WHATWG', 'web-messaging.html#dom-messageport-postmessage', 'postMessage()')}} | {{Spec2('HTML WHATWG')}} |         |

## Compatibilidade com navegadores

{{Compat("api.MessagePort.postMessage")}}

## See also

- [Using channel messaging](/pt-BR/docs/Web/API/Channel_Messaging_API/Using_channel_messaging)
