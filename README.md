# RastroJS

Uma biblioteca JavaScript para rastreamento de encomendas nos Correios.

- [RastroJS](#rastrojs)
  - [Instalação](#instalação)
  - [Exemplos](#exemplos)
    - [Básico](#exemplo-básico)
    - [Com TypeScript](#exemplo-com-typescript)
  - [Contribuição](#constribuição)
  - [Licença](#licença)


## Instalação
```sh
npm install --save rastrojs
```

## Exemplos

### Exemplo Básico

```js
const { rastro } = require('rastrojs');

async function example() {

    const track = await rastro.track('JT124720455BR');

    console.log(track);

};

example();

```

### Exemplo com TypeScript

```typescript
import { RastroJS, Tracking } from 'rastrojs';

class Example extends RastroJS {

    constructor(private codes: string[]) {
        super();
    }

    public get tracks(): Promise<Tracking[]> {
        return this.track(this.codes)
    }

}

const example = new Example(['JT124720455BR', 'JT124720455BC', '123']);

example
    .tracks
    .then(tracks => console.log(tracks));
```

## Contribuição

Este projeto está totalmente aberto à contribuição e quem tiver interesse pode realizar fork e enviar Pull Requests. **Importante: se necessário registre issues.**

> Qualquer dúvida ou sugestão: tales.ferreira.luna@gmail.com

## Licença

RastroJS é totalmente aberta e está sob licença [MIT](./LICENSE), use a vontade.
