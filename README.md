
# 💸 pix-utils

Uma pequena biblioteca que irá te ajudar a lidar com chaves pix




## Instalação

Instale pix-utils com npm ou yarn

```bash
  npm install pix-utils
  yarn add pix-utils
```
    
## Documentação

#### Identifique uma chave pix

```js
  const { identify } = 'pix-utils'
  const { pix, type } = identify({pix: 'test@gmail.com'}) // {pix: 'test@gmail.com', type: 'email'}
```

| Função   | Parametro       | Retorno                           |
| :---------- | :--------- | :---------------------------------- |
| `identify` | `input: {pix: string}` | Pix `{ pix: string, type: string }` |

#### Validar uma chave pix

```js
  const { validate } = 'pix-utils'
  console.log(validate({pix: 'test@gmail.com'})) // true
  console.log(validate({pix: 'test'})) // false
  ```

| Função   | Parametro       | Retorno                           |
| :---------- | :--------- | :---------------------------------- |
| `validate` | `input: {pix: string}` | boolean |

#### Normalizar uma chave pix

```js
  const { normalize } = 'pix-utils'
  console.log(normalize({pix: '000.000.000-00'})) // {pix: '00000000000', type: 'cpf'}
  console.log(validate({pix: '00.000.000/0000-00'})) // {pix: '00000000000000', type: 'cnpj'}
  ```



## Rodando os testes

Para rodar os testes, rode o seguinte comando

```bash
  npm run test
```
