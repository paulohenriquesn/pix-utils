
# 💸 pix-utils-js

![](https://img.shields.io/npm/dw/pix-utils-js)
![](https://img.shields.io/npm/v/pix-utils-js)
![](https://img.shields.io/github/contributors/paulohenriquesn/pix-utils-js)
![](https://img.shields.io/npm/l/pix-utils-js)

Uma pequena biblioteca que irá te ajudar a lidar com chaves pix

Demo https://pix-key-js-demo.vercel.app/


## Instalação

Instale pix-utils-js com npm ou yarn

```bash
  npm install pix-utils-js
  yarn add pix-utils-js
```
    
## Documentação

#### Identifique uma chave pix

```js
  import { identify } from 'pix-utils-js'
  const { pix, type } = identify({pix: 'test@gmail.com'}) // {pix: 'test@gmail.com', type: 'email'}
```

| Função   | Parametro       | Retorno                           |
| :---------- | :--------- | :---------------------------------- |
| `identify` | `input: {pix: string}` | Pix `{ pix: string, type: 'email' \|  'cpf' \| 'cnpj' \|  'random' \|'phone' \| 'qrcode' }` |

#### Validar uma chave pix

```js
  import { validate } from 'pix-utils-js'
  console.log(validate({pix: 'test@gmail.com'})) // true
  console.log(validate({pix: 'test'})) // false
  console.log(validate({pix: 'test@gmail.com', type : 'cpf'})) // false
  console.log(validate({pix: '00020126360014BR.GOV...', type : 'qrcode'})) // true
  ```

| Função   | Parametro       | Retorno                           |
| :---------- | :--------- | :---------------------------------- |
| `validate` | `input: {pix: string}` | boolean |

#### Normalizar uma chave pix

```js
  import { normalize } from 'pix-utils-js'
  console.log(normalize({pix: '000.000.000-00'})) // {pix: '00000000000', type: 'cpf'}
  console.log(normalize({pix: '00.000.000/0000-00'})) // {pix: '00000000000000', type: 'cnpj'}
  console.log(normalize({pix: '+55 (11) 0000-0000'})) // {pix: '551100000000', type: 'phone'}
  console.log(normalize({pix: '00020126360014BR.GOV...'})) // {pix: '00020126360014BR.GOV...', type: 'qrcode'}
  ```

| Função   | Parametro       | Retorno                           |
| :---------- | :--------- | :---------------------------------- |
| `normalize` | `input: {pix: string}` | Pix `{ pix: string, type: 'email' \|  'cpf' \| 'cnpj' \|  'random' \|'phone' \| 'qrcode' }` |



## Rodando os testes

Para rodar os testes, rode o seguinte comando

```bash
  npm run test
```

