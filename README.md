# Simple CPF and CNPJ input mask.

![ttystrudio GIF](https://imgur.com/uZoDA6O.gif)

This is an `<input />` wrapper to mask the value (**_which can be either a CPF or CNPJ_**) with the corresponding brazilian format mask, as you type. \
It will apply all the props given to it, to an input field, enabling any customization.
**No dependencies included.**

Este é um componente que encapsula um `<input />`, com o objetivo de adicionar a máscara correspondente no valor (Podendo ser CPF ou CPNJ) do input enquanto você digita.
Os props são copiados diretamente para um `<input />`, permitindo customização.
**Não possui dependendências.**

## Installation

```shell
$ yarn add @react-br-forms/cpf-cnpj-mask
```

## Example

### Basic Example

```JSX
import React, { useState } from "react";
import ReactDOM from "react-dom";
import CpfCnpj from "@react-br-forms/cpf-cnpj-mask";

const App = () => {

  const [cpfCnpj, setCpfCnpj] = useState("");
  const [mask, setMask] = useState("");

  return (
    <div>
      <CpfCnpj
        value={cpfCnpj}
        onChange={(value, type) => {
          setCpfCnpj(value);
          setMask(type === "CPF");
        }}
      />
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById("root"));

```

### With custom props

```JSX
import React, { useState } from "react";
import ReactDOM from "react-dom";
import CpfCnpj from "@react-br-forms/cpf-cnpj-mask";

const App = () => {

  const [cpfCnpj, setCpfCnpj] = useState("");
  const [mask, setMask] = useState("");

  return (
    <div>
      <CpfCnpj
        className="customizedInput"
        placeholder="Digite um CPF ou CNPJ"
        type="tel"
        value={cpfCnpj}
        onChange={(value, type) => {
          setCpfCnpj(value);
          setMask(type === "CPF");
        }}
      />
      <br />
      <h4>Masked value: {cpfCnpj}</h4>
      <h4>Mask: {getDocumentTypeDescription(cpfCnpj, mask)}</h4>
    </div>
  );
};

ReactDOM.render(<App />, document.getElementById("root"));

```

## Component Props

|            Name             |       Type        | DefaultProps | Description                                                                                                                                  |
| :-------------------------: | :---------------: | :----------: | :------------------------------------------------------------------------------------------------------------------------------------------- |
|    **[`value`](#value)**    |     `String`      |     `""`     | Wrapped `<input/>` value. This value will be masked.                                                                                         |  |
| **[`onChange`](#onChange)** | `Function(event)` |  `() => {}`  | Wrapped `onChange` input function. This function will be called after the `<input/>` `onChange` function. The `target.value` will be masked. |
|     **[`type`](#type)**     |     `String`      |    `tel`     | Default input type is `tel`.                                                                                                                 |

## About the repository

> Install the dependencies.
>
> - `npm install` or `yarn install`
>
> To start the example project in dev:
>
> - `npm run start`

## Test

> Install the dependencies.
>
> - `npm install` or `yarn install`
>
> To test the component:
>
> - `npm run test`
>
> To test the component, and watch:
>
> - `npm run test:watch`
>
> To see test coverage:
>
> - `npm run test:coverage`

## License

[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
